# Introduction

### What is SmartViu?

SmartViu is a customized web-based solution designed for Blue Yonder (BY) WMS users. It is designed to simplify screen development for users with no experience in Page Builder, DDAs, and Web screens. SmartViu is a no-code/low-code solution specifically tailored for Blue Yonder WMS users, making the process of screen creation effortless and efficient.

SmartViu streamlines the creation and management of screens, allowing you to focus on optimizing your operations and achieving your business goals.

### Key Features

- Easy screen development with no coding required.
- Maintenance screen for managing LES commands.
- SmartViu screen for viewing and interacting with reports.
- Role-based access control for report visibility.
- Enhanced data visualization with grid coloring features based on criteria provided by the user.

## Architectural Overview

### High-Level Structure

SmartViu is composed of several integrated components that work together to provide a seamless user experience. These components include the user interface (UI) built with Ext JS 4.2, the backend services for handling business logic, and the database for storing and retrieving data. The architecture ensures flexibility and scalability, allowing developers to influence and customize various aspects of the solution.

The architecture includes several key components.

### User Interface (UI) Layer

- **Front-End Framework:** Built using EXT JS 4.2 for creating rich, interactive web applications.
- **LES Command Screen:** A maintenance screen providing basic functionalities such as adding reports, deleting, and unassigning a role from a report.
- **SmartViu Screen:** Displays a list of reports added via the LES Command screen, allowing users to view detailed information and perform actions on the data grids.

### Application Layer

- **Business Logic:** Contains the core functionality and rules of SmartViu.
- **Report Management Module:** Manages the addition, deletion, and assignment of reports.
- **Report Viewing and Action Module:** Handles the display and interaction with reports in the SmartViu screen.
- **Security Module:** Manages user authorization and role-based access control.

### Data Layer

- **Database:** Stores user data, screen configurations, reports, and application settings.
- **Data Access Layer:** Manages database interactions and ensures data integrity and security.

### Key Technologies

- **Front-End:** EXT JS 4.2 for building dynamic and responsive user interfaces.
- **Database:** SQL Server or Oracle for reliable data storage and management.
- **Language:** MOCA language is used to create scripts for LES commands.

### LES Commands (Main, Detail, and Action)

- **Main Command:** This component defines the primary commands available in SmartViu, such as adding, updating, and deleting LES commands. Developers can customize these commands to meet specific business needs.
- **Detail Command:** Provides additional details and configurations for each main command. Developers can extend these details to capture more granular information.
- **Action Command:** Defines the actions that can be performed on the data within SmartViu, such as running specific reports or executing tasks. Developers can add new actions or modify existing ones to enhance functionality.

### Security

Security in SmartViu is managed through role-based access control. Each LES command can be assigned specific roles, ensuring that only authorized users can access certain reports and functionalities. Users can define new roles from standard Blue Yonder configuration, assign permissions, and manage user access to maintain a secure environment.

