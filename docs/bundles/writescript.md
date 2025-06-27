# LES Commands

LES command scripts are categorized into four types:
1. **Main Commands** – Define the core structure of a report, including its query and layout.
2. **Action Commands** – Trigger specific operations or backend processes directly from the data grid (e.g., update status, call a MOCA command).
3. **Detail Commands** – Display additional, related information in expandable detail grids linked to the main data.
4. **hyperlink Commands** – Enable navigation to other screens or drill-down reports by linking rows or columns to new views.

## How to Write Script?

Following the correct format for these commands ensures optimal performance and seamless integration within SmartViu.

<img src="./Attachments/LES_Cmd_Script.png" alt="undirectedmenu" style="height:height: 350px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">

### Main Commands

Main commands are the primary instructions used to manage LES commands within SmartViu. Users must define the main command with the above-mentioned format. Users also follow the format for defining each main command ID such as `<Main-CMD>`.

<img src="./Attachments/Main_Command.png" alt="undirectedmenu" style="height: 300px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

**LES Main Command To Display Inventory**

```sql
publish data 
where wh_id = @wh_id
and stoloc = @stoloc
and arecod = @arecod
and prtnum = @prtnum
and lotnum = @lotnum
and getcolclause = @getcolclause
|
publish data
where wh_id = nvl(@wh_id,@@wh_id)
and offset = nvl(@offset,0) 
and limit = nvl(@limit,100000000000)
|
{
    if(@wh_id is null)
    { hide stack variable where name = 'wh_id'}
    |
    if(@stoloc is null)
    { hide stack variable where name = 'stoloc'}
    |
    if(@arecod is null)
    { hide stack variable where name = 'arecod'}
    |
    if(@prtnum is null)
    { hide stack variable where name = 'prtnum'}
    |
    if(@lotnum is null)
    { hide stack variable where name = 'lotnum'}
    |
    if(!@getcolclause)
    { 
      publish data 
      where getcolclause= 'and 1 = 2'
    }
    |
    [
    select locmst.wh_id,
           locmst.stoloc,
           supnum,
           lodnum,
           dtlnum,
           subnum,
           prtnum,
           prt_client_id,
           ftpcod,
           orgcod,
           revlvl,
           invsts,
           untqty,
           fifdte,
           mandte,
           expire_dte
    from inventory_view
    join locmst
    on locmst.stoloc = inventory_view.stoloc
    and locmst.wh_id = inventory_view.wh_id 
    where @+locmst.wh_id
    and @+locmst.stoloc
    and @+arecod
    and @+prtnum
    and @+lotnum
    @getcolclause:raw
    ]catch (-1403,510)
}  
```
### Action Commands

Action commands are specific instructions associated with main commands. They define the actions that can be performed on the data. The format for an action command ID is typically `<Main-CMD>-A-1`, `<Main-CMD>-A-2`.

<img src="./Attachments/Action_Command.png" alt="undirectedmenu" style="height: 300px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

**LES Action Command**

```sql
publish data 
where wh_id = nvl(@wh_id,@@wh_id)
and stoloc = @stoloc
and lodnum = @lodnum
and subnum = @subnum
and dtlnum = @dtlnum
and dstloc = @dstloc
and dstlod = @dstlod
|
validate stack variable not null 
where name = 'wh_id'
|
validate stack variable not null 
where name = 'stoloc'
|
validate stack variable not null 
where name = 'lodnum'
|
validate stack variable not null 
where name = 'subnum'
|
validate stack variable not null 
where name = 'dtlnum'
|
validate stack variable not null 
where name = 'dstloc'
|
if (@dstloc is not null)
{
    [
    select count(*) dstcnt
    from dual
    where exists( 
                select 'X' 
                from locmst 
                where stoloc = @dstloc 
                and wh_id = @wh_id
                )
    ]
    |
    if ( @dstcnt = 0 )
    {
        set return status 
        where status = '8585858585858'
    }
}
```
### Detail Commands

Detail commands provide additional configuration and details for each main command. They extend the functionality and customization of main commands. The format for a detail command ID is typically `<Main-CMD>-D-1`, `<Main-CMD>-D-2`.

<img src="./Attachments/Dtl_Command.png" alt="undirectedmenu" style="height: 300px; width :500px ;margin:auto;display:block; cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

**LES Detail Command**

``` sql
publish data 
where wh_id = nvl(@wh_id,@@wh_id)
and stoloc= @stoloc
and getcolclause = @getcolclause
|
if(@wh_id is null)
{ hide stack variable where name = 'wh_id'}
|
if(@arecod is null)
{ hide stack variable where name = 'arecod'}
|
if(!@getcolclause)
{ 
  publish data 
  where getcolclause= 'and 1 = 2'
}
|
[/*#limit=@offset,@limit,true*/
select locmst.wh_id,
       locmst.stoloc,
       lodnum,
       dtlnum,
       subnum,
       prtnum,
       prt_client_id,
       ftpcod,
       orgcod,
       revlvl,
       invsts,
       untqty 
from inventory_view
join locmst
on locmst.stoloc = inventory_view.stoloc
and locmst.wh_id = inventory_view.wh_id 
where @+locmst.wh_id
and @+locmst.stoloc
@getcolclause:raw
]catch (-1403,510)
``` 

### HyperLink Commands
Hyperlink is used to allow users to easily navigate from main grid to another popup screen based on a column name.  
The format for a Hyperlink is typically <COLUMN1-Main-CMD>-H-1, < COLUMN2-Main-CMD>-H-2 

For example: 
LES Command ID = ordnum-usr_ossi_test_ord_new-H-1 

Ordnum: Column name is used for hyperlink 

usr_ossi_test_ord_newn: Main LES Command ID 

H-1: It represents the first Hyperlink  
<img src="./Attachments/HyperLink_Command.png" alt="undirectedmenu" style="height: 300px; width :500px ; width :px ;margin:auto;display:block;cursor: zoom-in; 
border: 2px solid #000000; border-radius: 4px;"
onclick="this.style.height='400px'; this.style.cursor='zoom-out';" 
ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
</br>

**LES HyperLink Command**

```sql
publish data 
  where btcust = @btcust 
    and wh_id = @wh_id
    and getcolclause = @getcolclause 
|
if(!@getcolclause)
{ 
  publish data 
  where getcolclause= 'and 1 = 2'
}
|
[
/*#limit=@offset,@limit,true*/
select * 
from cstmst 
where @+cstnum^btcust
@getcolclause:raw
]catch(-1403,510) 
|
filter data where moca_filter_level = '1' 
and btcust = @cstnum
;
