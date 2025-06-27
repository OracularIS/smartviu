# Architectural Overview
SmartViu follows a modular, three-tier architecture designed for flexibility and scalability:

## User Interface (UI) Layer

Built on Ext JS 4.2, consisting of:
- **OSSI - LES Command Maintenance Screen:** A maintenance screen providing basic functionalities such as adding reports, deleting, and unassigning a role from a report.
- **SmartViu Screen:** Displays a list of reports added via the LES Command screen, allowing users to view detailed information and perform actions on the data grids.

## Application Layer

- **Business Logic & Report Management:** handles creation, editing, and assignment of screens.
- **Report Viewer & Actions:** enables users to view data grids and execute tasks.
- **Security Module:** Manages user authorization and role-based access control.

## Data Layer

- **Database:** Stores user data, screen configurations, reports, and application settings.
- **Data Access Layer:** Manages database interactions and ensures data integrity and security.