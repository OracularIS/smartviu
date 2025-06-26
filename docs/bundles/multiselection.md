# Multi Selection
Multi-selection is supported in SmartViu for drop-down fields. If a user wants to add a report that includes multiple selections, some changes need to be made in the LES Command script. Below is an example of multi-selection.

<img src="./Attachments/Bundles/Multi_Selection.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

In the below screenshot multi selection is shown on Smart Viu. Click on Find button.

<img src="./Attachments/Bundles/Multi_Selection_Grid_view.png" alt="undirectedmenu" style="height: 250px; width:500px;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>
There are some changes need to be made in LES Command script for Multi Selection. 

 ```sql
 publish data
 where trlr_stat = @trlr_stat
   and trlr_typ = @trlr_typ
   and trlr_cond = @trlr_cond
   and trlr_num = @trlr_num
   and trailer_use = @trailer_use
   and Location = @Location
   and loc_typ_cat = @loc_typ_cat
   and carcod = @carcod
   and prtfam = @prtfam
   and getcolclause = @getcolclause
   and getcolclause = @getcolclause
   and prtnum = @prtnum
   and sos_flg = @sos_flg
   and outofstock_flg = @outofstock_flg
   and emptytrlr_flg = @emptytrlr_flg
  and live_load_flg = @live_load_flg
   and stock_flg = @stock_flg
   
|
if (@trlr_stat is null)
{
    publish data where trlr_stat_clause = 'and 1=1'
}
else if(instr(@trlr_stat,','))
{publish data where trlr_stat_clause = 'and trlr_stat in('||@trlr_stat||')'

}