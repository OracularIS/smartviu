# Version 2026.1.3.5 – Report Title, Clear Button & Security Fixes

## Release Notes

- **Report Title** – The open report's name now shows at the top left of the toolbar, shortened on narrow screens so it never overlaps the buttons.
- **Clear Button Fix** – The **Clear** button now returns to the welcome screen in one step and reloads the **Reports** and **Favourites** lists so new reports appear.
- **Reports List Fix** – Resolved issue where the **Reports** list could show empty after a reload.
- **Safe Text Display** – Report data, labels and menu text are now always shown as plain text, so HTML in the data is never run.
- **CSV Export Security Fix** – Exported values starting with `=`, `+`, `-` or `@` are now saved as text, so spreadsheets don't run them as formulas.
- **Command Maintenance Request Fix** – The device code is now removed only from Command Maintenance's own requests, leaving other screens untouched.
- **Special Fields Fix** – Resolved issue where special fields were not validated because of an incorrect form name.
- **Base Records Update** – Added the **Multi Select** flag to the SmartViu command records, and fixed the modified date and user on load.
- **General Bug Fixes** – Minor fixes and code cleanup.
