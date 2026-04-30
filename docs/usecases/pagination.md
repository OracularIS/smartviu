# Pagination in SmartViu

When datasets grew too large to display all at once, developers had to write custom logic to load and display data page by page. In current version of SmartViu, pagination is handled automatically by the system, without the need for custom scripting or additional logic. This makes the user experience more seamless and ensures that large datasets are loaded efficiently, with consistent performance and fewer errors.

However, in earlier version of SmartViu, pagination was not built-in, so this functionality had to be manually implemented using MOCA scripting. For this, various techniques were used, such as `internal tables`, `inline pagination directives` and `command` to manage and control the data flow across pages.

## Legacy Methods for Pagination

 Below are the three primary techniques that were commonly used in older versions of SmartViu:

1. Internal Table Handling
2. Inline Pagination Directive
3. Using Command

### Method 1: Internal Table Handling

This method involved manually managing pagination by publishing data into internal tables and then querying that data with applied limits and offsets.

1. Step 1: Publishing Data

    Data was filtered and limited at the time of publishing, using default or provided offset and limit values:

    ```moca
    publish data 
    where wh_id = nvl(@wh_id,@@wh_id) 
      and offset = nvl(@offset, 0) 
      and limit = nvl(@limit, 100000000000)
    ```

2. Step 2: Creating or Releasing Internal Tables

    Based on whether results already existed in the internal table, SmartViu would either release the table or create a new one:

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
    ```
3. Step 3: Fetching Paginated Data

    Data was fetched from the internal table using SQL pagination syntax:
    
    ```moca
    select 
    from internal table 
    where select_stmt = 'select *' 
      and table_name = 'uc_all_int' 
      and where_clause = 'ORDER BY 1 OFFSET ' || @offset || ' ROWS FETCH NEXT ' || @limit || ' ROWS ONLY' 
    ```
   **Note:** For lower environments, the where_clause format changes to:

    ```moca
    'ORDER BY 1 LIMIT ' || @limit || ' OFFSET ' || @offset
    ```

This method offered flexibility but was complex to maintain, and prone to errors if not handled carefully—especially with large datasets or nested queries.

### Method 2: Inline Pagination Directive
MOCA provided a built-in way to define pagination directly within a query using an inline directive.

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
### Method 3: Using `get paged results` Command

This MOCA command was designed to simplify pagination by applying offset and limit directly to a result set:

```moca
get paged results 
where mocaRes = @mocaRes 
  and totalRowCount = @totalRowCount 
  and offset = @offset 
  and limit = @limit 
```

> **Best Practice:**  
> SmartViu now automatically manages `LIMIT` and `OFFSET`, so there's no need to handle pagination manually in latest release of smartViu.  
> Existing users using manual approaches are encouraged to switch to the built-in handling for a more efficient and streamlined experience.

---

<br><br>
