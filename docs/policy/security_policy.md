# Policies for Security

The Security Policies provide configurable controls for validating and securing user-defined local syntax.

These policies help prevent the execution of unauthorized or potentially unsafe operations by enforcing static syntax validation, whitelist/blacklist checks, and save/execution restrictions.

## Security Policies 

| # | polcod | polvar | Policy Name | Description |
|---|---------|---------|-------------|-------------|
| 1 | **USR-SMARTVIU** | **SECURITY** | **UC_SMARTVIU_WHITE_LIST_TOKEN_LIST** | Defines the list of approved tokens or patterns that are permitted during local syntax validation. |
| 2 | **USR-SMARTVIU** | **SECURITY** | **UC_SMARTVIU_BLACK_LIST_TOKEN_LIST** | Defines the list of restricted tokens or patterns that are prohibited during local syntax validation. |
| 3 | **USR-SMARTVIU** | **SECURITY** | **UC_SMARTVIU_VALIDATE_SAVE** | Controls whether local syntax is validated before it can be saved. |
| 4 | **USR-SMARTVIU** | **SECURITY** | **UC_SMARTVIU_PREVENT_INVALID_SAVE** | Controls whether users are allowed to save syntax that fails validation checks. |
| 5 | **USR-SMARTVIU** | **SECURITY** | **UC_SMARTVIU_VALIDATE_EACH_EXEC** | Controls whether syntax validation is performed each time local syntax is executed. |


## Policy Structure

| polcod       | polvar   | polval        | rtstr1                     | rtnum1              |
| ------------ | -------- | ------------- | -------------------------- | ------------------- |
| USR-SMARTVIU | SECURITY | Policy Name | Policy Configuration Value | Enable/Disable Flag |

### Policy Fields

| Field      | Description                                                         |
| ---------- | ------------------------------------------------------------------- |
| **RTSTR1** | Stores the configuration value associated with the security policy. |
| **RTNUM1** | Controls whether the policy is enabled or disabled.                 |

> **RTNUM1 Values**
>
> * `1` = Enabled
> * `0` = Disabled


1. **Blacklist token Policy**

    | polcod       | polvar   | polval                            | rtstr1                  | rtnum1 |
    | ------------ | -------- | --------------------------------- | ----------------------- | ------ |
    | USR-SMARTVIU | SECURITY | UC_SMARTVIU_BLACK_LIST_TOKEN_LIST | SQL_DDL / OS_CMD / DYN_MOCA | 1      |

2. **Validate on Every Execution Policy**

    | polcod       | polvar   | polval                         | rtstr1 | rtnum1 |
    | ------------ | -------- | ------------------------------ | ------ | ------ |
    | USR-SMARTVIU | SECURITY | UC_SMARTVIU_VALIDATE_EACH_EXEC | TRUE   | 1      |

3. **Prevent Invalid Syntax Save Policy**

    | polcod       | polvar   | polval                           | rtstr1 | rtnum1 |
    | ------------ | -------- | -------------------------------- | ------ | ------ |
    | USR-SMARTVIU | SECURITY | UC_SMARTVIU_PREVENT_INVALID_SAVE | TRUE   | 1      |

4. **Validate Save Policy**

    | polcod       | polvar   | polval                           | rtstr1 | rtnum1 |
    | ------------ | -------- | -------------------------------- | ------ | ------ |
    | USR-SMARTVIU | SECURITY | UC_SMARTVIU_VALIDATE_SAVE | 1   | 1      |


## Security Policy Retrieval

Smart Viu security settings are retrieved using the following function:

```moca
smart usr_get_security_setting
```

### Input Parameters

| Parameter    | Description                |
| ------------ | -------------------------- |
| `moca_farg1` | Policy Code (`polcod`)     |
| `moca_farg2` | Policy Variable (`polvar`) |
| `moca_farg3` | Policy Value (`polval`)    |
---
