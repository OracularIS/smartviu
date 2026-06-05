# Execution Workflow

Smart Viu access is controlled through a role-based authorization model. 

User permissions are not assigned directly; instead, access is granted through roles and options.

## Workflow Overview

1. A Smart Viu role is defined in the system.
2. The role is associated with one or more options.
3. Users are assigned the appropriate role.
4. When a user is assigned a role, they automatically inherit access to all options associated with that role.
5. Through the assigned options, the user gains access to the corresponding Smart Viu functionality and actions.

## Configuration Tables

### Role Definition

The Smart Viu role is configured in the `sys_dsc_mst` table.

| Column    | Value        |
| --------- | ------------ |
| colnam    | role_id      |
| colval    | USR_SMARTVIU |
| lngdsc    | Smart Viu    |
| short_dsc | Smart Viu    |

### Option Definition

The Smart Viu option is configured in the `les_mnu_opt` table.

| Column  | Value          |
| ------- | -------------- |
| opt_nam | optUsrSmartViu |

The option description is maintained in the `sys_dsc_mst` table.

| Column   | Value                        |
| -------- | ---------------------------- |
| colnam   | opt_nam                      |
| colval   | optUsrSmartViu               |
| mls_text | Smart Viu Option Description |

### Role-to-Option Assignment

The relationship between the Smart Viu role and option is maintained in the `les_opt_ath` table.

| Option         | Role         |
| -------------- | ------------ |
| optUsrSmartViu | USR_SMARTVIU |


### Example

If User A is assigned the `USR_SMARTVIU` role:

* User A inherits access to the `optUsrSmartViu` option.
* Any Smart Viu actions associated with that option become available to User A.

If User B is not assigned the `USR_SMARTVIU` role:

* User B will not receive the `optUsrSmartViu` option.
* Smart Viu functionality will not be accessible.
---