## Policy for Snowflake

- ### USR-SNOWFLAKE-QUERY Policy 

    The usr-snowflake-query policy is configured in Smart VIU to enable 
    data retrieval from a Snowflake database. By setting up this policy, 
    Smart VIU can query and fetch data directly from Snowflake.

    Here is a generic format to enable a policy 

    | polcod                  | polvar       | polval       | rtstr1                          | rtnum1 |
    |-------------------------|--------------|--------------|---------------------------------|--------|
    | POLICY-NAME     | POLICY VARIABLE   | parameter being configured           | Value assigned to parameter  | Enabled      |

    To configure the database configure the policy like described below:

    | polcod                  | polvar       | polval       | rtstr1                          | rtnum1 |
    |-------------------------|--------------|--------------|---------------------------------|--------|
    | USR-SNOWFLAKE-QUERY     | CONNECTION   |  DB           | Name of the database  | 1      |

    The rtnum1 field controls whether the policy is enabled or not.
    -  `rtnum1=1` → enabled (ON)
    -  `rtnum=0` → disabled (OFF)

    Similarly you can configure this policy for **DB Views, URL, Schema, Drivers, URL, Users and WH** .

    ---
