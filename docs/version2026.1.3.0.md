# Version 2026.1.3.0 – SmartViu & Command Maintenance Stability Fixes

## Release Notes

- **Grid Date Display Fixes** – Resolved issue where dates in the grid displayed with corrupted/incorrect years.
- **Action Popup and Item Number Fixes** – Resolved issue where the **Item Number** field appeared twice in action popups.
- **Grid Pagination and Hyperlink Fixes** – Resolved issue where opening a hyperlink could reset an unrelated grid's pagination.
- **Clear Button and Screen Reset Fixes** – Resolved issue where the **Clear** button caused a full page reload, and fixed a case where it could cause the screen to error out.
- **Command Maintenance Details Grid Fixes** – Fixed the details grid hiding after deleting a record in Command Maintenance.
- **Command Maintenance Item Number Field Fix** – Fixed the Item Number field remaining visually locked after deselecting a record.
- **Syntax Editor and SQL Formatter Fixes** – Fixed the syntax editor and SQL formatter failing to load in Command Maintenance.
- **Send Email Feature** – Resolved issue where email sending failed when SMTP server policies weren't configured; it now automatically falls back to the default mail configuration instead of blocking the send.
- **Outbound Request Security Fixes** – Improved security of outbound request handling.
- **General Bug Fixes** – Minor code and bug fixes with improved code quality and refactoring.
