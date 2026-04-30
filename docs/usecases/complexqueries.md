# Scripts to Handle Complex Queries

When working with complex queries such as those involving multiple joins, large datasets, or dynamic filters, performance can quickly become a concern. These queries get executed twice thus tend to consume more resources, and if not optimized properly, they can lead to delays, timeouts, or even errors in SmartViu screens.

To handle such cases efficiently, SmartViu provides two effective methods that simplify execution while improving performance:

1. Using @getcolclause
2. Using SmartViu Policies

##  Method 1: Use `@getcolclause` for Dynamic Queries

When you run a SmartViu report with a complex query, SmartViu needs to first identify the column structure before displaying any data. If this isn’t handled properly, the system may execute the query twice, once to get the headers, and again to fetch the data which can cause performance issues for complex or large datasets.

To optimize this, you can use the @getcolclause directive.

### **What does @getcolclause actually do?**

Internally, SmartViu replaces @getcolclause with different filters during different phases of execution:

- **Phase 1:** Fetch column headers only
  
  SmartViu substitutes @getcolclause with `and 1 = 2` so the query returns no data, but still provides column metadata.

- **Phase 2:** Fetch actual data for the grid

  SmartViu then re-runs the query with @getcolclause replaced by `and 1 = 1`, allowing it to fetch all the matching records.

### Example Script

Here’s how the logic looks:

```moca
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
[
  select * 
  from ord 
  where @+ordnum 
    and wh_id = @wh_id @getcolclause 
] 
```

## Method 2: Use Policies for Static Column Definition

In some cases, your query logic might be too complex to dynamically determine columns. For example, queries with:

- Subqueries
- Conditional logic
- Runtime joins or unions

To handle these scenarios, SmartViu allows you to define policies that explicitly control how data is displayed, without relying on SmartViu to infer the column structure. These policies allow you to define the structure and display of your report data manually, avoiding the need for multiple query executions.

### Policies to Configure

Following are the policies you need to set up for handling complex queries:
    
- **Step 1:** Enable Static Grid for the Command

  First activate the policy for a specific command by setting polval to `ENABLED`.

  | `polcod` | `polvar`                     | `polval` | `rtstr1`       |
  |----------|------------------------------|----------|----------------|
  | USR-SMARTBASE  | UC-STATIC-GRID | ENABLED     | create_order   |

- **Step 2:** Define the Original Columns

  This policy allows you to define the exact columns you want to include in the report by specifying a comma-separated list of original column names in `rtstr2`.

  | `polcod`       | `polvar`              | `polval`  | `rtstr1`       | `rtstr2`                                                 |
  |----------------|------------------------|-----------|----------------|----------------------------------------------------------|
  | USR-SMARTBASE  | UC-STATIC-GRID         | ORG-COL   | create_order   | client_id, ordnum, wh_id, btcust, stcust, rtcust, brcust |

- **Step 3:** Define Columns Description

  This policy provides user-friendly display names for the columns, aligned in the same order as ORG-COL in `rtstr2`.   

  | `polcod`       | `polvar`              | `polval`  | `rtstr1`       | `rtstr2`                                                 |
  |----------------|------------------------|-----------|----------------|----------------------------------------------------------|
  | USR-SMARTBASE  | UC-STATIC-GRID         | DSP-COL   | create_order   | Client ID,Outbound Order Number,Warehouse ID,Bill-To Customer Ship-To Customer,Route-To Customer,Broker Customer |

---

<br><br>
