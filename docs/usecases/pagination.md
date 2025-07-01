# Pagination 

SmartViu now automatically manages `LIMIT` and `OFFSET`, so there's no need to handle pagination manually. 

New users should avoid using custom pagination logic in reports, as the tool takes care of it in the background. Existing users using manual approaches are encouraged to switch to the built-in handling for a more efficient and streamlined experience.

## Old Pagination Methods in SmartViu

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
if (@ordnum is null)
{
  hide stack variable 
    where name = 'ordnum' 
}
|
[select * 
   from ord 
  where @+ordnum 
    and wh_id = @wh_id @getcolclause 
] 
```

> **Note:**  
> If `@getcolclause` is not used, the query may run more than once, once to retrieve the column headers and again to fetch the actual data.  
> To avoid this, it's recommended to use `@getcolclause` or configure the relevant SmartViu policies to manage recursion effectively.

### Handling Complex Queries

In cases where you’re working with complex queries or prefer not to use `@getcolclause`, SmartViu provides a flexible alternative through predefined policies.

These policies allow you to define the structure and display of your report data manually, avoiding the need for multiple query executions.

- **Policies to Set Up**

    Following are the policies you need to set up for handling complex queries:
    
    - First activate the policY for a specific command by setting polval to `ENABLED`.

        | `polcod` | `polvar`                     | `polval` | `rtstr1`       |
        |----------|------------------------------|----------|----------------|
        | USR-SMARTBASE  | UC-STATIC-GRID | ENABLED     | create_order   |

        In this case, the above mentioned policy will be enabled specifically for the `create_order` command.

    - **ORG-COL** policy allows you to define the exact columns you want to include in the report by specifying a comma-separated list of original column names.

        | `polcod`       | `polvar`              | `polval`  | `rtstr1`       | `rtstr2`                                                 |
        |----------------|------------------------|-----------|----------------|----------------------------------------------------------|
        | USR-SMARTBASE  | UC-STATIC-GRID         | ORG-COL   | create_order   | client_id, ordnum, wh_id, btcust, stcust, rtcust, brcust |


        This policy will apply only to the columns listed in `rtstr2`.
        
         You can control which columns appear in the report by specifying them as a comma-separated list here. 

    - **DSP-COL** this policy provides user-friendly display names for the columns, aligned in the same order as ORG-COL.   

        | `polcod`       | `polvar`              | `polval`  | `rtstr1`       | `rtstr2`                                                 |
        |----------------|------------------------|-----------|----------------|----------------------------------------------------------|
        | USR-SMARTBASE  | UC-STATIC-GRID         | DSP-COL   | create_order   | Client ID,Outbound Order Number,Warehouse ID,Bill-To Customer,Ship-To Customer,Route-To Customer,Broker Customer |

  




---

<br><br>
