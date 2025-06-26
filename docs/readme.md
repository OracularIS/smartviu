# Introduction

## What is SmartViu?

SmartViu is a customized web-based solution designed for Blue Yonder (BY) WMS users. It is designed to simplify screen development for users with no experience in Page Builder, DDAs, and Web screens. SmartViu is a no-code/low-code solution specifically tailored for Blue Yonder WMS users, making the process of screen creation effortless and efficient.

SmartViu streamlines the creation and management of screens, allowing you to focus on optimizing your operations and achieving your business goals.

### Key Features

- Easy screen development with no coding required.
- Maintenance screen for managing LES commands.
- SmartViu screen for viewing and interacting with reports.
- Role-based access control for report visibility.
- Enhanced data visualization with grid coloring features based on criteria provided by the user.

### Core Technologies

| Component           | Technology         |
|---------------------|--------------------|
| Front-End           | Ext JS 4.2         |
| Server-Side Language| MOCA (LES scripting) |
| Database            | SQL Server or Oracle |

### LES Commands (Main, Detail, and Action)

- **Main Command:** This component defines the primary commands available in SmartViu, such as adding, updating, and deleting LES commands. Developers can customize these commands to meet specific business needs.
- **Detail Command:** Provides additional details and configurations for each main command. Developers can extend these details to capture more granular information.
- **Action Command:** Defines the actions that can be performed on the data within SmartViu, such as running specific reports or executing tasks. Developers can add new actions or modify existing ones to enhance functionality.

### Security

Security in SmartViu is managed through role-based access control. Each LES command can be assigned specific roles, ensuring that only authorized users can access certain reports and functionalities. Users can define new roles from standard Blue Yonder configuration, assign permissions, and manage user access to maintain a secure environment.

