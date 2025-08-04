# Snowflake Integration in SmartViu

SmartViu now supports direct integration with Snowflake to allow seamless access to archived or historical data without impacting production systems.

## Overview

Traditionally, accessing archived data in Snowflake required specialized BI tools, additional licenses, or technical support from IT teams to generate one-off reports. This creates delays, increases dependency, and limits visibility for end users.

SmartViu’s native Snowflake integration solves this problem by allowing users to query and visualize archived data directly from within the SmartViu interface. Whether you’re viewing live data or years-old transactions, the experience remains consistent, fast, and intuitive.

### Key Benefits

- Run historical reports without switching tools
- Compare current and past performance in the same grid
- Use powerful SmartViu features like filters, sorting, and exports on Snowflake data
- Eliminate performance risks tied to querying large archives from production

With this integration, SmartViu becomes a single, unified platform for both operational and archival reporting, making it easier for teams to make informed decisions with full data visibility.

## How to Enable Snowflake Access?

To enable Snowflake integration in a SmartViu screen, use the smart snowflake query command in your report configuration script.

```sql
execute smart snowflake query
    where uc_snowflake_query = 'select top 10 * from aremst'
    and uc_use_snowflake_views = 1
 ```   

### Required Parameters

| **Parameter**             | **Description**                                                        | **Value** |
|---------------------------|------------------------------------------------------------------------|-----------|
| `uc_snowflake_query`      | The SQL query to be executed on Snowflake                             | Any valid SQL query (e.g. `SELECT * FROM table_name`) |
| `uc_use_snowflake_views`  | Enables SmartViu to use the default Snowflake views schema            | `1` to enable, `0` to disable |

When uc_use_snowflake_views = 1, SmartViu automatically connects to the appropriate Snowflake schema.

## Managing Snowflake Views in Smart MOCA Client

While SmartViu allows you to query Snowflake data seamlessly within your smartviu screen, the creation and maintenance of Snowflake views is performed separately in Smart MOCA Client using the **Snowflake** add-on feature.

### Key Features:

1. **Create View(s)**: Automatically generate views in Snowflake for selected WMS tables. This ensures consistent data structures and makes querying simpler.

2. **Drop View(s)**: Easily remove outdated or unnecessary views without leaving the Smart MOCA Client.

3. **Missing MLS Text**: Fill in missing multilingual descriptions (MLS) for columns so that views are clearly labeled for reporting and end users.

These capabilities ensure that your Snowflake environment is set up properly for use in SmartViu.