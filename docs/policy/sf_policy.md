# Policies for Snowflake

The Snowflake policies provide configuration parameters required to connect Smart VIU with a Snowflake database.

By configuring the Snowflake policy, Smart VIU can retrieve data directly from Snowflake based on the specified database, views, schema, URL, drivers, users, and warehouse configuration.

## Configured Policies

The following policies are configured under the **USR-SNOWFLAKE-QUERY** policy code:

| polcod                  | polvar         | Description                                                           |
| ----------------------- | -------------- | --------------------------------------------------------------------- |
| **USR-SNOWFLAKE-QUERY** | **CONNECTION** | Configures the Snowflake database connection parameters.              |
| **USR-SNOWFLAKE-QUERY** | **DB-VIEWS**   | Configures the Snowflake database views to be accessed by Smart VIU.  |
| **USR-SNOWFLAKE-QUERY** | **URL**        | Configures the URL required to connect to the Snowflake environment.  |
| **USR-SNOWFLAKE-QUERY** | **SCHEMA**     | Configures the Snowflake schema used for data retrieval.              |
| **USR-SNOWFLAKE-QUERY** | **DRIVERS**    | Configures the driver required for the Snowflake database connection. |
| **USR-SNOWFLAKE-QUERY** | **USERS**      | Configures the Snowflake user or users used for database access.      |
| **USR-SNOWFLAKE-QUERY** | **WH**         | Configures the warehouse used for query execution.          |

## Policy Structure

| **polcod**          | **polvar**      | **polval**  | **rtstr1**                 | **rtnum1**          |
| ------------------- | --------------- | ----------- | -------------------------- | ------------------- |
| USR-SNOWFLAKE-QUERY | Policy Variable | Policy Name | Policy Configuration Value | Enable/Disable Flag |

### Policy Fields

| **Field**  | **Description**                                                          |
| ---------- | ------------------------------------------------------------------------ |
| **POLCOD** | Identifies the Snowflake policy using the value **USR-SNOWFLAKE-QUERY**. |
| **POLVAR** | Identifies the type of Snowflake configuration being defined.            |
| **POLVAL** | Specifies the parameter or policy name being configured.                 |
| **RTSTR1** | Stores the configuration value associated with the Snowflake policy.     |
| **RTNUM1** | Controls whether the policy is enabled or disabled.                      |



### Enable / Disable Policy

The **RTNUM1** field determines whether a Snowflake policy configuration is active.

* `rtnum1=1` → **Enabled (ON)**
* `rtnum1=0` → **Disabled (OFF)**

A policy configuration is active only when **RTNUM1 is set to `1`**.


## Configured Snowflake Policies

**1. Database Connection Policy**

The CONNECTION policy is used to configure the Snowflake database connection.

| polcod                  | polvar         | polval | rtstr1               | rtnum1 |
| ----------------------- | -------------- | ------ | -------------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **CONNECTION** | **DB** | Name of the database | **1**  |

**2. Database Views Policy**

The DB-VIEWS policy is used to configure the database views that Smart VIU can access.

| polcod                  | polvar       | polval   | rtstr1                    | rtnum1 |
| ----------------------- | ------------ | -------- | ------------------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **DB-VIEWS** | **View** | Name of the database view | **1**  |

**3. URL Policy**

The URL policy is used to configure the URL required to connect to the Snowflake environment.

| polcod                  | polvar  | polval  | rtstr1                   | rtnum1 |
| ----------------------- | ------- | ------- | ------------------------ | ------ |
| **USR-SNOWFLAKE-QUERY** | **URL** | **URL** | Snowflake connection URL | **1**  |

**4. Schema Policy**

The SCHEMA policy is used to configure the Snowflake schema from which Smart VIU retrieves data.

| polcod                  | polvar     | polval     | rtstr1                       | rtnum1 |
| ----------------------- | ---------- | ---------- | ---------------------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **SCHEMA** | **Schema** | Name of the Snowflake schema | **1**  |

**5. Drivers Policy**

The DRIVERS policy is used to configure the database driver required for the Snowflake connection.

| polcod                  | polvar      | polval     | rtstr1                    | rtnum1 |
| ----------------------- | ----------- | ---------- | ------------------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **DRIVERS** | **Driver** | Snowflake database driver | **1**  |

**6. Users Policy**

The USERS policy is used to configure the Snowflake user or users that are authorized to access the database.

| polcod                  | polvar    | polval   | rtstr1            | rtnum1 |
| ----------------------- | --------- | -------- | ----------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **USERS** | **User** | Snowflake user ID | **1**  |

**7. Warehouse Policy**

The WH policy is used to configure the Snowflake warehouse used for query execution.

| polcod                  | polvar | polval        | rtstr1                          | rtnum1 |
| ----------------------- | ------ | ------------- | ------------------------------- | ------ |
| **USR-SNOWFLAKE-QUERY** | **WH** | **Warehouse** | Name of the Snowflake warehouse | **1**  |

> **Note:** The values shown in `rtstr1` are examples of the parameters that can be configured. The actual values should be provided according to the Snowflake environment being connected to Smart VIU.

---
