# Policies for Error Codes 

The Error Codes policy provides centralized management of Smart Viu application exceptions and error messages.

Rather than hard-coding error messages within the application, each exception is configured as a policy entry under ERROR-CODES.

## Configured Exceptions

| # | polcod | polvar | polval (Exception)  | Description |
|---|---------|---------|-----------|-------------|
| 1 | **USR-SMARTVIU** | **ERROR-CODES** | **EUSR_SMARTVIU_CHECK_UC_APP_CONG_POL** | Raised when a required Smart Viu application configuration policy is missing or invalid. |
| 2 | **USR-SMARTVIU** | **ERROR-CODES** | **EUSR_SMARTVIU_CHECK_UC_STATIC_GRID_POL** | Raised when the required static grid configuration policy is missing or incorrectly configured. |
| 3 | **USR-SMARTVIU** | **ERROR-CODES** | **EUSR_SMARTVIU_EXECUTION_BLOCKED** | Raised when execution of an operation is blocked due to a validation, configuration, or security restriction. |
| 4 | **USR-SMARTVIU** | **ERROR-CODES** | **EUSR_SMARTVIU_RECORD_ALREADY_EXIST** | Raised when an attempt is made to create a record that already exists. |
| 5 | **USR-SMARTVIU** | **ERROR-CODES** | **EUSR_SMARTVIU_USER_NOT_AUTHORIZED** | Raised when the current user does not have permission to perform the requested action. |

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

> **Note:** The complete error message is formed by concatenating **RTSTR1** and **RTSTR2**

1. **Invalid Application Configuration**

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_CHECK_UC_APP_CONG_POL            | Configure Error, Please check UC-APP-CONG Policy. Thank You!   |   |97504   |

2. **Record Already Exist Policy**

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_RECORD_ALREADY_EXIST            | Same Record Already Exist   |   |97503   |

3. **Static Grid Configuration Policy**

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_CHECK_UC_STATIC_GRID_POL            | Please check again UC-STATIC-GRID policy   |   |97502   |

4. **Execution Block Policy**

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_EXECUTION_BLOCKED            | The execution is blocked.� Please review detailed status in OSSI LES Command Maintenance.   |   |97500   |

5. **User not Authorized Error Policy**

| polcod                  | polvar       | polval       | rtstr1                       |rtstr2                       |rtnum1                     |
|-------------------------|--------------|--------------|---------------------------------|---------------------------------|---------------------------------|
| USR-SMARTVIU     | ERROR-CODES   | EUSR_SMARTVIU_USER_NOT_AUTHORIZED            | User ID : ^usr_id^ not Authorized to Perform Operation OR no LES command is defined   |   |97501   |

---