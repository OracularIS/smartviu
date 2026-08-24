# SmartViu Email Setup Configuration

## Overview

SmartViu email configuration policies are created automatically during rollout. Customers only need to maintain the configuration values for their warehouse or provide them through environment variables where applicable.

### Important Notes

* `rtnum1` **must be enabled and set to `1`** for all email configuration policies.
* Actual configuration values must be maintained in **`rtstr1`**.
* Email functionality will only be available when `FEATURE_ENABLED` is set appropriately.

## Policy Configuration

| # | polcod                | polvar           | polval            | Description                                                                   |
| - | --------------------- | ---------------- | ----------------- | ----------------------------------------------------------------------------- |
| 1 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_SERVER`     | Specifies the SMTP server host used for sending emails.                       |
| 2 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_PORT`       | Specifies the SMTP server port used for email communication.                  |
| 3 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_TLS`        | Controls whether TLS is enabled (`1`) or disabled (`0`) for SMTP connections. |
| 4 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_USER`       | Specifies the username used to authenticate with the SMTP server.             |
| 5 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_PASSWORD`   | Specifies the password used to authenticate with the SMTP server.             |
| 6 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_SENDER`     | Specifies the sender email address used in outgoing emails.                   |
| 7 | `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `FEATURE_ENABLED` | Controls whether the email feature is enabled (`1`) or disabled (`0`).        |

## Example Configuration

| polcod                | polvar           | polval            | rtstr1 (Example Value)      | rtnum1 |
| --------------------- | ---------------- | ----------------- | --------------------------- | ------ |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `FEATURE_ENABLED` |                          | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_SERVER`     | `smtp.office365.com`        | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_PORT`       | `587`                       | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_TLS`        | `1`                         | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_USER`       | `notifications@company.com` | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_PASSWORD`   | `********`                  | `1`    |
| `USR_SMARTBASE_EMAIL` | `DEFAULT-CONFIG` | `MAIL_SENDER`     | `notifications@company.com` | `1`    |

---

