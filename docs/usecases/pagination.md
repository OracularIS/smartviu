# Scripts to Handle Pagination

SmartViu previously supported multiple custom methods to handle pagination using `offset` and `limit`.

Below is a summary of the common legacy methods:


### **Method 1: Internal Table Handling**

This method uses internal tables to apply offset and limit dynamically:

```moca
publish data 
  where wh_id = nvl(@wh_id,@@wh_id) 
    and offset = nvl(@offset, 0) 
    and limit = nvl(@limit, 100000000000)
```


- **Followed by Moca Query**

```moca
if(rowcount(@res_all_int)>0) 
{
  release internal tables 
}
else 
{
  create internal table 
    where table_name = 'uc_all_int' 
      and res = @res_all_int 
}
select 
  from internal table 
 where select_stmt = 'select *' 
   and table_name = 'uc_all_int' 
   and where_clause = 'ORDER BY 1 OFFSET ' || @offset || ' ROWS FETCH NEXT ' || @limit || ' ROWS ONLY' 
```
For lower environments, the where_clause format changes to:

```moca
'ORDER BY 1 LIMIT ' || @limit || ' OFFSET ' || @offset
```

### **Method 2: Inline Pagination Directive**
Pagination logic was embedded using MOCA's inline directive:

```moca
[
/*#limit=@offset,@limit,true*/ 
select *  
from ord  
where @+ordnum  
and @+wh_id  
@getcolclause:raw 
]catch (-1403,510)
```
### **Method 3: Using Command**

This command was a built-in option but lacked reliability in some cases:
```moca
get paged results 
  where mocaRes = @mocaRes 
    and totalRowCount = @totalRowCount 
    and offset = @offset 
    and limit = @limit 
```

> **Note:**  
> SmartViu now automatically manages `LIMIT` and `OFFSET`, so there's no need to handle pagination manually.  
> New users should avoid using custom pagination logic in reports, as the tool takes care of it in the background.  
> Existing users using manual approaches are encouraged to switch to the built-in handling for a more efficient and streamlined experience.

---

<br><br>
