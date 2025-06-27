# Add New Fields

If there a new field needed to be added in any LES Command Maintenance screen, It’s data must be added in the below tables. A field’s type must be specified i.e Combo Box, Date/Time or Flag.
 - les_var_config
 - les_lkp
 - les_var_vp

1. In les_var_config table a field name, description and its type must be defined. If a field with the name “tray_box” is required, its data must be added in the “les_var_config” table like given below.

    <img src="./Attachments/LES_Cmd_Tbl1.png" alt="undirectedmenu" style="height: 70px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

2.	In les_var_vp table a Lookup ID is created in lkp_id column.  User has to insert record in les_var_vp table manually as shown in the below screenshot.

    <img src="./Attachments/LES_Cmd_Tbl2.png" alt="undirectedmenu" style="height: 70px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

3. In les_lkp table a command or SQL statement must be created for that field in lkp_cmd column against relevant lkp_id as given below.

    <img src="./Attachments/LES_Cmd_Tbl3.png" alt="undirectedmenu" style="height: 70px; width:500px;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

4. Below is the SQL statement which has been added in “lkp_cmd” column of “les_lkp” table.

    <img src="./Attachments/Lkp_Cmd_SQL.png" alt="undirectedmenu" style="height: 120px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

5. Lookup Field is shown in Smart Viu.

    <img src="./Attachments/Lkp_Fields.png" alt="undirectedmenu" style="height: 160px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
    border: 2px solid #000000; border-radius: 4px;"
    onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
    ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">