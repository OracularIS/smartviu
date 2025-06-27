# Grid Coloring Functionality

The grid coloring functionality in the SmartViu screen helps you visualize report data more effectively. Coloring is applied based on specific criteria for each column or row in the main grid, allowing you to quickly identify important information.

To apply grid coloring:

1. Select a record from the main grid.

2. Click on the **“Color Config Window”** button.

    <img src="./Attachments/Color_Config_window1.png" alt="undirectedmenu" style="height: 150px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

3. A new pop-up window will open where you can define the criteria for applying color coding to the grid.

    <img src="./Attachments/Color_Config_window2.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

4. In the pop-up window, you can add, update, or delete criteria for grid coloring using the respective buttons:

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
    - **Update**: This button is used to modify an existing rule.
    - **Delete**: Click the "Delete" button to remove the selected grid rule.

    <img src="./Attachments/Color_Config_window3.png" alt="undirectedmenu" style="height: 200px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

    For example, in the above screenshot, grid coloring is applied to the entire row that has item number "1000660616", and this rule is set at the User Level (e.g., only the SUPER user will see this grid rule).

5. Now, check the grid coloring applied to the main grid.

    <img src="./Attachments/Color_Config_window4.png" alt="undirectedmenu" style="height: 120px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

    *Note: Ensure that you have defined clear and specific criteria for each column or row to make the grid coloring meaningful and helpful.*

Using this grid coloring functionality enhances the readability of your data reports and allows you to quickly identify critical information based on the criteria you set.