# Pagination 

SmartViu now automatically manages `LIMIT` and `OFFSET`, so there's no need to handle pagination manually. 

New users should avoid using custom pagination logic in reports, as the tool takes care of it in the background. Existing users using manual approaches are encouraged to switch to the built-in handling for a more efficient and streamlined experience.

## Previous Pagination Methods in SmartViu

SmartViu previously supported multiple custom methods to handle pagination using `offset` and `limit`.

While these approaches worked, they required manual setup and were often inconsistent across environments. Below is a summary of the common legacy methods:


### **Method 1: Internal Table Handling**

This method uses internal tables to apply offset and limit dynamically:

```sql
publish data where wh_id = nvl(@wh_id,@@wh_id)
and offset = nvl(@offset, 0)
and limit = nvl(@limit, 100000000000)
```


- **Follwed by Moca Query**

```sql
if(rowcount(@res_all_int)>0) {
  release internal tables
} else {
  create internal table where table_name = 'uc_all_int' and res = @res_all_int
}

select from internal table 
where select_stmt = 'select *'
and table_name = 'uc_all_int'
and where_clause = 'ORDER BY 1 OFFSET ' || @offset || ' ROWS FETCH NEXT ' || @limit || ' ROWS ONLY'
```
For lower environments, the where_clause format changes to:

```sql
'ORDER BY 1 LIMIT ' || @limit || ' OFFSET ' || @offset
```

### **Method 2: Inline Pagination Directive**
Pagination logic was embedded using MOCA's inline directive:

```sql
[/*#limit=@offset,@limit,true*/ 
select *  
from ord  
where @+ordnum  
and @+wh_id  
@getcolclause:raw 
]catch (-1403,510)
```
### **Method 3: `get paged results` Command**

This command was a built-in option but lacked reliability in some cases:
```sql
get paged results 
where mocaRes = @mocaRes 
  and totalRowCount = @totalRowCount 
  and offset = @offset 
  and limit = @limit
```
With the new SmartViu updates, these manual methods are no longer needed.

## New Pagination Method in SmartViu


Pagination is now handled automatically by the system, making your reports cleaner, faster, and easier to maintain.

- SmartViu eliminates the need for manual use of OFFSET and LIMIT in queries. 
- Including `@getcolclause` ensures the system fetches column headers without executing the full query twice.
- This improves performance and prevents unnecessary load on the system.
- Especially helpful when working with complex or large datasets.

Here’s how the logic looks:

```sql
publish data  
where ordnum = @ordnum  
and wh_id = nvl(@wh_id, @@wh_id)  
|  
if (@ordnum is null) {  
    hide stack variable  
    where name = 'ordnum'  
}  
|  
[select * from ord where @+ordnum and wh_id = @wh_id @getcolclause]
```

> **Note:**  
> If `@getcolclause` is not used, the query may run more than once, once to retrieve the column headers and again to fetch the actual data.  
> To avoid this, it's recommended to use `@getcolclause` or configure the relevant SmartViu policies to manage recursion effectively.

---

<br><br>
