# Scripts to Handle Complex Queries
You can now handle complex queries in SmartViu using two simple methods, both explained below for easy implementation.

##  Method 1: Use @getcolclause

Including `@getcolclause` ensures the system fetches column headers without executing the full query twice. 

SmartViu eliminates the need for manual use of OFFSET and LIMIT in queries.

This improves performance and prevents unnecessary load on the system. Especially helpful when working with complex or large datasets.

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

## Method 2: Use Policies

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
