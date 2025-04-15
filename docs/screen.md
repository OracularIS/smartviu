# SmartViu Screen

## Overview

The SmartViu screen is designed for end-users to easily view and work with the reports created in the Maintenance Screen. It has a simple and user-friendly layout that lets you view report lists, interact with grid data, visualize main grid details, and use enhanced data visualization features like grid coloring functionalities.

## View Report List and Report Data

To view the report list in SmartViu:

1. Click on the Reports Filter drop-down or Reports Tree that will show the available reports. 
2. Users can only view those reports which they are authorized to see. For example, if an LES command is assigned a SUPER role, the user can see the report in the Reports Filter drop-down field or Reports Tree only if the user has the SUPER role assigned.

<img src="./Attachments/Screen/Reports_Tree.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>



3. Select a report from the available report list, and input fields will be drawn dynamically for that report.

<img src="./Attachments/Screen/Report_List.png"
alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block;cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

*Note: These input fields are created for each LES command based on the publish statement at the top of the MOCA script.*

<img src="./Attachments/Screen/Input_Field_Publish_command.png" alt="undirectedmenu" style="height: 250px; width 500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

4. Click on the "Find" button to load the report data in the grid, or you can fill out input fields to find data based on the given input parameters.


<img src="./Attachments/Screen/Report_Data_Grid.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

Users can also add frequently used reports to favorite reports, by clicking the star button. Those reports will show in favorite reports after clearing the data. 

<img src="./Attachments/Screen/Fvrt_Report1.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

<img src="./Attachments/Screen/Fvrt_Report2.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

## View and Process Detailed Actions

To view and process detailed actions for a record:

1. Navigate to the main grid and select the record you wish to view details for by clicking on it.
2. After selecting the record, choose the detail report from the "Select Detail Action" lookup field. A popup window will appear; select any detail report from the list, and it will display the detail/child grid of the selected record.

<img src="./Attachments/Screen/Dtl_Cmd_field.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

Choose an action: By default, the first action in the Detail Action lookup is selected. If you wish to perform a different action, select it from the action lookup available list.

<img src="./Attachments/Screen/Dtl_Cmd_Field2.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

## View and Process Grid Actions

The Grid Action Lookup allows you to perform various actions on selected data from the main grid. Follow these steps to use this feature:

1. Navigate to the main grid and select the record you wish to perform an action on by clicking on them.
2. The area below the grid is used for action buttons. If the selected record needs to be processed as a move inventory action, click the 'Move Inventory Process' button. To delete the record, click the 'Purge WMS Inventory' button.

<img src="./Attachments/Screen/Action_Fields1.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

A new pop-up window will open. Here, you need to provide the required input parameters to perform the selected action. For example, if you want to move inventory, you will need to provide the destination load and destination location where the inventory will be moved.

<img src="./Attachments/Screen/Action_Fields2.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>
After providing the necessary information, confirm and execute the action by clicking on the "OK" button.

## View and Process Hyperlink

1. Select and open the report for which Hyperlink is created. Click on Find button to show the data.

<img src="./Attachments/Screen/Hyperlink_Grid1.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';" >
</br>

2. If click on any value, it will show another popup page containing a grid with data.

<img src="./Attachments/Screen/Hyperlink_grid2.png" alt="undirectedmenu" style="height: 240px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

## Grid Coloring Functionality

The grid coloring functionality in the SmartViu screen helps you visualize report data more effectively. Coloring is applied based on specific criteria for each column or row in the main grid, allowing you to quickly identify important information.

To apply grid coloring:

1. Select a record from the main grid.
2. Click on the “Color Config Window” button.

<img src="./Attachments/Screen/Color_Config_window1.png" alt="undirectedmenu" style="height: 150px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

A new pop-up window will open where you can define the criteria for applying color coding to the grid.

<img src="./Attachments/Screen/Color_Config_window2.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

In the pop-up window, you can add, update, or delete criteria for grid coloring using the respective buttons:

- To add a new criterion, first fill out all the required fields and click on the "Add" button.
  - **Grid Field Name**: This dropdown field contains all the grid columns where you want to apply the color coding. e.g., Item Number
  - **Select Operation**: This dropdown field contains comparison operators. Choose an operation from the dropdown menu. Select “=” for string comparison. e.g., "="
  - **Compare Fields**: Enter the value to compare against the selected grid field name. e.g., "CHIPS"
  - **Set User Level Or LES Level**: Choose between "User Level" or "LES Level".
    - **User Level**: Check the "User Level" checkbox to enable coloring only for the user who added the criteria (e.g., a super user).
    - **LES / Instance Level**: Check the "LES Level" checkbox to enable coloring for all users.
  - **Back Color**: Choose the color for the grid coloring rule. By default, it is black.
  - **Foreground Color**: This filed is used to choose the Foreground Color for grid coloring rule.
  - **Apply to Entire Row**: Check this checkbox to apply the grid coloring to the entire row. If unchecked, coloring will be applied only to the specified column.

 <img src="./Attachments/Screen/Color_Config_window3.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

For example, in the above screenshot, grid coloring is applied to the entire row that has item number "1000660616", and this rule is set at the User Level (e.g., only the SUPER user will see this grid rule).

Now, check the grid coloring applied to the main grid.

 <img src="./Attachments/Screen/Color_Config_window4.png" alt="undirectedmenu" style="height: 120px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 


- **Update**: This button is used to modify an existing rule.
- **Delete**: Click the "Delete" button to remove the selected grid rule.

*Note: Ensure that you have defined clear and specific criteria for each column or row to make the grid coloring meaningful and helpful.*

Using this grid coloring functionality enhances the readability of your data reports and allows you to quickly identify critical information based on the criteria you set.



## Top Bar Menu

Some action buttons are available on the top menu of the SmartViu screen.


- **Clear Grid Data**  
  The **"Clear Grid Data"** button clears the current grid data and makes the input fields for search criteria visible.

- **Grid Refresh**  
  The **"Grid Refresh"** button reloads the grid data.

- **Grid Settings**  
  The **"Grid Settings"** action button works similarly to the bottom bar’s Color Configuration Window button.  
  It allows you to set criteria for grid coloring based on specific conditions, enhancing the visualization of report data and making it easier to identify important information.

- **Find**  
  The **"Find"** button loads the main report data into the grid, enabling you to view data for the selected report.

- **Clear**  
  The **"Clear"** button removes all data from the SmartViu screen and reloads the entire interface.  
  This functionality helps reset the view for a fresh start.

- **Export All**  
  The **"Export"** button exports data from the main grid into a CSV file, making it easy to save, share, or analyze the data in other applications.

- **Help**  
  The **"Help"** button opens the user guide.

- **Grid Coloring Functionality**  
  The grid coloring functionality in the SmartViu screen helps visualize report data more effectively.  
  Colors are applied based on specific criteria for each column or row in the main grid, allowing quick identification of key information.

- **Apply Aggregate Function**  
  The **"Apply Aggregate Function"** button is used to apply aggregate functions to the data displayed in the grid.
1. Select a report from the list and load the data in grid, navigate to Apply Aggregate Function button.

     <img src="./Attachments/Screen/Aggregate_Func_Btn.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

2. In this case aggregate function is going to be created on Order Quantity column. The below screen is shown.

    <img src="./Attachments/Screen/Aggregate_Func_Fields.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

3. Select an integer field from the drop down to get the stats against the selected field. e.g.  Order Quantity

     <img src="./Attachments/Screen/Aggregate_Func_Fields2.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

4. Select any aggregate function from Group Function drop down menu.

     <img src="./Attachments/Screen/Aggregate_Func_Fields3.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

5. Click on Add Criteria button.

     <img src="./Attachments/Screen/Aggregate_Func_Criteria1.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

6. Criteria is created in the below screen. Click on Confirm button to apply the criteria.

     <img src="./Attachments/Screen/Aggregate_Func_Criteria2..png" alt="undirectedmenu" style="height: 200px;width: 500px; margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

7. When Confirm button is clicked. Criteria will be applied. In Gid Total the count and total is calculated.

     <img src="./Attachments/Screen/Aggregate_Total.png" alt="undirectedmenu" style="height: 200px;width: 500px;margin:auto;display:block; cursor: zoom-in; 
              border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br> 

