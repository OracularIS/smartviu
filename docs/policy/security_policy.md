# Policies for Security

The Security Policies provide configurable controls for validating and securing user-defined local syntax.

These policies help prevent the execution of unauthorized or potentially unsafe operations by enforcing static syntax validation, whitelist/blacklist checks, and save/execution restrictions.

Security behavior can be managed through policy configuration without requiring application code changes.

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

## Security Policy Descriptions

| Policy Name                           | Description                                                                                           |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **UC_SMARTVIU_WHITE_LIST_TOKEN_LIST** | Defines the list of approved tokens or patterns that are permitted during local syntax validation.    |
| **UC_SMARTVIU_BLACK_LIST_TOKEN_LIST** | Defines the list of restricted tokens or patterns that are prohibited during local syntax validation. |
| **UC_SMARTVIU_VALIDATE_SAVE**         | Controls whether local syntax is validated before it can be saved.                                    |
| **UC_SMARTVIU_PREVENT_INVALID_SAVE**  | Controls whether users are allowed to save syntax that fails validation checks.                       |
| **UC_SMARTVIU_VALIDATE_EACH_EXEC**    | Controls whether syntax validation is performed each time local syntax is executed.                   |

## Syntax Validation

The Smart Viu static analysis process evaluates submitted local syntax against the configured whitelist and blacklist policies. If a token matches a blacklist entry, validation fails. If a token matches a whitelist entry, it is considered an approved pattern. These checks help prevent the execution of unauthorized or potentially unsafe operations.

## Example Configured Policies

### Example 1: Blacklist Token Policy

| polcod       | polvar   | polval                            | rtstr1                  | rtnum1 |
| ------------ | -------- | --------------------------------- | ----------------------- | ------ |
| USR-SMARTVIU | SECURITY | UC_SMARTVIU_BLACK_LIST_TOKEN_LIST | SQL_DDL / OS_CMD / DYN_MOCA | 1      |

**Description:** Blocks SQL DDL statements, operating system commands, and dynamic MOCA execution during syntax validation.

### Example 2: Validate on Every Execution

| polcod       | polvar   | polval                         | rtstr1 | rtnum1 |
| ------------ | -------- | ------------------------------ | ------ | ------ |
| USR-SMARTVIU | SECURITY | UC_SMARTVIU_VALIDATE_EACH_EXEC | TRUE   | 1      |

**Description:** Performs syntax validation each time local syntax is executed.

### Example 3: Prevent Invalid Syntax Save

| polcod       | polvar   | polval                           | rtstr1 | rtnum1 |
| ------------ | -------- | -------------------------------- | ------ | ------ |
| USR-SMARTVIU | SECURITY | UC_SMARTVIU_PREVENT_INVALID_SAVE | TRUE   | 1      |

**Description:** Prevents users from saving syntax that fails validation checks.

---
