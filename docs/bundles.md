# SmartViu Bundles

## Overview

SmartViu consists of two main screens: the Maintenance Screen and the SmartViu Screen.

### LES Command Maintenance Screen

This screen is used primarily by administrators or users with the appropriate roles to manage LES commands. It allows for the creation, updating, deletion, and assignment of roles to LES commands. This is the backbone of how reports are managed within SmartViu.

### SmartViu Screen

This screen is used by end-users to view and interact with the reports that have been set up in the Maintenance Screen. It provides a user-friendly interface for viewing report lists, performing actions on grid data, and visualizing report details with enhanced data visualization features such as grid coloring.

These two screens work together to provide a comprehensive solution for managing and interacting with reports in a Blue Yonder WMS environment.

## LES Command Maintenance Screen

In the Maintenance Screen, LES commands are defined and managed. These commands control various aspects of report management, including creation, updating, and role assignments to LES Commands.

### LES CMD Script Format

#### How to Write Scripts

Users need to follow the below format when writing for all three main, action, and detail LES Commands.

![](Images/fig1.png)

#### Main Commands

Main commands are the primary instructions used to manage LES commands within SmartViu. Users must define the main command with the above-mentioned format. Users also follow the format for defining each main command ID such as `<Main-CMD>`.

![](Images/fig2.png)

#### Detail Commands

Detail commands provide additional configuration and details for each main command. They extend the functionality and customization of main commands. The format for a detail command ID is typically `<Main-CMD>-D-1`, `<Main-CMD>-D-2`.

![](Images/fig3.png)

#### Action Commands

Action commands are specific instructions associated with main commands. They define the actions that can be performed on the data. The format for an action command ID is typically `<Main-CMD>-A-1`, `<Main-CMD>-A-2`.

![](Images/fig4.png)

## CRUD Functionalities

### Add New LES Command

1. Click on the "New" button to add a new LES Command.
2. Enter the required information for the new LES command like LES command ID, description, etc.
3. Assign a role to the LES Command from the dropdown menu. Users can add multiple roles to a single LES Command.
4. Write the MOCA Script in the local syntax field and make sure you follow the format for writing the script for LES Commands.
5. Click on the "Save" button to add the LES Command.

![](Images/fig5.png)

![](Images/fig6.png)

### Delete LES Command

1. Click on the "Find" button to load the LES command record in the grid.
2. Select a record from the grid.
3. Click on the "Delete" button to delete this command.
4. This will delete the LES command as well as the role assigned to the LES command.

### Update LES Command

1. Click on the "Find" button and select a record from the grid which you want to update.
2. Edit the required fields like local syntax or descriptions.
3. Click on the "Save" button and the data will be updated.

### Unassign Role for LES Command

1. Click on the "Find" button to load the LES command record in the grid.
2. Select a record from the grid.
3. Click on the "Unassign" button to unassign the roles from the selected LES command.
4. Now, the role for the selected LES command is removed.
