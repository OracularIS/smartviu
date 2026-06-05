# Policies for Error Codes 

The Error Codes policy provides centralized management of Smart Viu application exceptions and error messages.

Rather than hard-coding error messages within the application, each exception is configured as a policy entry under ERROR-CODES.

This allows error codes and messages to be maintained through configuration and ensures consistent error handling across the application.


## Policy Structure

| polcod       | polvar      | polval           |
| ------------ | ----------- | ---------------- |
| USR-SMARTVIU | ERROR-CODES | Exception Name |

### Policy Fields

| Field      | Description                                                 |
| ---------- | ----------------------------------------------------------- |
| **RTNUM1** | Stores the unique error code associated with the exception. |
| **RTSTR1** | Stores the first part of the error message.                 |
| **RTSTR2** | Stores the second part of the error message.                |

> **Note:** The complete error message is formed by concatenating **RTSTR1** and **RTSTR2**.

## Configured Exceptions

| Exception                                  | Description                                                                                                   |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| **EUSR_SMARTVIU_CHECK_UC_APP_CONG_POL**    | Raised when a required Smart Viu application configuration policy is missing or invalid.                      |
| **EUSR_SMARTVIU_CHECK_UC_STATIC_GRID_POL** | Raised when the required static grid configuration policy is missing or incorrectly configured.               |
| **EUSR_SMARTVIU_EXECUTION_BLOCKED**        | Raised when execution of an operation is blocked due to a validation, configuration, or security restriction. |
| **EUSR_SMARTVIU_RECORD_ALREADY_EXIST**     | Raised when an attempt is made to create a record that already exists.                                        |
| **EUSR_SMARTVIU_USER_NOT_AUTHORIZED**      | Raised when the current user does not have permission to perform the requested action.                        |

## Example 

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_RECORD_ALREADY_EXIST            | Same Record Already Exist   |   |97503   |

---