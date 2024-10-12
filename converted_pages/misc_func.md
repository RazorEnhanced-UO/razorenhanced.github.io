#  Scripting - Misc data and function 
Here can find some infomation about Enhanced Scripting function and data misc!

##  Message 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Sysmessage**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.SendMessage(string or int or bool)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Send a sysmessage.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string Message, int Value, bool Status

|}


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Sysmessage colored**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.SendMessage(string or int or bool, color)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Send a sysmessage whit specific color
|- style="background-color:#f0f0f0;"
|**Returns**
| none
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string Message or int Value or bool Status, int color

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player SendToClient**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.SendToClient(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Send a string to the UO client window. Can contain control characters by prefixing the character with ^ (e.g. ctrl-u is "^u")
|- style="background-color:#f0f0f0;"
|**Returns**
| none
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string to send to client window

|}

##  File 

The file operations are limited, because I am paranoid of bad actors.
The file to be written to MUST be in the RE directory tree, or if your running CUO it can be in the CUO directory tree. Further, the file suffix has to be one of {data, xml, map, csv}. The file suffixes list could be extended, but the main thing I didn't want someone to do damage to files needed for execution. 


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Append a line to a file**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.AppendToFile(string FileName, string LineToAppend)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Appends a single line to a file.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool True - success False - Fail
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string FileName, string LineToInsert

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Append a line to a file IF it doesn't already exist**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.AppendNotDupToFile(string FileName, string LineToAppend)
|-
|colspan="2" |**Description:**
|-
|colspan="2" | Appends a single line to a file if that line does not already exist in the file.
use in your code like:
<code>
#
result = Misc.AppendNotDupToFile("C:/CUO/Data/Client/TreasureMaps.csv", "1111, 2222, map,desc,I forget")
#
</code>
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string FileName, string LineToInsert


|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Remove a line from a file**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.DeleteFile(string FileName)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Deletes a file
|- style="background-color:#f0f0f0;"
|**Returns**
|bool True - success False - Fail
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string FileName

|}


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Remove a line from a file**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.RemoveLineInFile(string FileName, string LineToAppend)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Removes a single line from a file if it exists
|- style="background-color:#f0f0f0;"
|**Returns**
|bool True - success False - Fail
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string FileName, string LineToInsert

|}

##  System 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Resync Game Data**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Resync( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Resync game data.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Pause on Script**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Pause(int)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Pause script for X millisecond.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|MSpause

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Focus on UoClient window**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.FocusUOWindow()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Set UoClient window in focus or restore if minimized.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Screen Capture the UoClient window**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.CaptureNow()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Creates a snapshot of the current UO window
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}
##  Misc 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Beep**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Beep( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Play beep system sound.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Shard Name**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ShardName( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Get string with shard name you play.
|- style="background-color:#f0f0f0;"
|**Returns**
|string
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Inspect Items**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Inspect( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Prompts for a target, then displays info for that item
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **NextContPosition**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.NextContPosition(x, y)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Sets the x,y co-ordinates of where the next gump will be openned. You must have cascading containers enabled 
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|int x, int y window position

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **GetContPosition**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.GetContPosition()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Returns the x,y co-ordinates of where the current gumpis positioned. 
|- style="background-color:#f0f0f0;"
|**Returns**
|point(x, y)
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|

|}
##  Mouse 
{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Get Current Mouse Location**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.MouseLocation()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Returns a point with the X and Y coordinates of the mouse relative to the UO Window
|- style="background-color:#f0f0f0;"
|**Returns**
|point
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none
|-
|colspan="2" |Example:
<code>
p = Misc.MouseLocation()
</code>
|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Set Mouse Location**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.MouseMove()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Moves the mouse pointer to the position X,Y relative to the UO window
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|int X, int Y
|-
|colspan="2" |Example:
<code>
Misc.MouseMove(p.X+10, p.Y+20)
</code>
|}

##  Disconnect 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Disconnect**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Disconnect( )
|-
|colspan="2" |**Description: Immediate logout**
|-
|colspan="2" |Force client to disconnect.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

##  Context Menu 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Wait Context Menu**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.WaitForContext(int or mobile or item, int)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Wait server response a context menu request.
|- style="background-color:#f0f0f0;"
|**Returns**
|List < Context > - Context { int reply, string text in menu }
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|timeout

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Context Menu Reply**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ContextReply(int or mobile or item, int or string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Respond to a context menu on mobile or item. Menu ID is base zero, or can use string of menu text
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|Menuname

|}

##  Share Data for Script 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Read Shared Value**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ReadSharedValue(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Read a shared value, if value not exist return null.
|- style="background-color:#f0f0f0;"
|**Returns**
|obj
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|nameofvalue

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Remove Shared Value**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.RemoveSharedValue(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Remove a shared value,
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|nameofvalue

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Check Shared Value**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.CheckSharedValue(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Get a true o flase if value exist.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|nameofvalue

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Set Shared Value**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.SetSharedValue(string, obj)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Set a value by specific name, if value exist he repalce value.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|value

|}

##  Old Menu 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Has Menu**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.HasMenu()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Return bool if have or not a menu opened.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Close Menu**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.CloseMenu()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Close opened menu.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Menu Contain**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.MenuContain(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Search in opened menu if contains a specific string, return true or false.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|texttosearch

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Menu Title**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.GetMenuTitile()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Return a string of title for opene menu.
|- style="background-color:#f0f0f0;"
|**Returns**
|string
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Wait For Menu**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.WaitForMenu(int)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Pause script until server send menu, delay is in ms.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|delayinms

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Menu Response**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.MenuResponse(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Perform a menu response by subitem name. If item not exist close menu
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|subitemname

|}

##  Query String 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Has Has QueryString**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.HasQueryString( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Check if a have a query string menu opened, return true or false.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Wait For Query String**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.WaitForQueryString(int)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Pause script until server send query string request, delay is in ms.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|delayinms

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Query String Response**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.QueryStringResponse(bool, string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Perform a query string response by ok or cancel button and specific response string.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|stringtoresponse

|}

##  Script Function 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Run a Script**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ScriptRun(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Run a script by file name, Script must be present in script grid.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|scriptfilename

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Stop a Script**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ScriptStop(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Stop a script by file name, Script must be present in script grid.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|scriptfilename

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Stop all Script**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ScriptStopAll( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Stop all script running.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Script Status**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ScriptStatus(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Get status of script if running or not, Script must be present in script grid.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|scriptfilename

|}

##  Maps 
{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Co-Ordinates of a Decoded Map**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.GetMapInfo(serial)
|-
|colspan="2" |**Description:**
|-
|colspan="2" | Retrieve the co-ordinates of a decoded t-map. Your code would look like:
<code>
#
mapInfo = Misc.GetMapInfo(0x400BFD6C)
print("Treasure at ({}, {}), Origin ({}, {}), pin at ({}, {})"
    .format(mapInfo.MapOrigin.X+mapInfo.PinPosition.X, mapInfo.MapOrigin.Y+mapInfo.PinPosition.Y,
            mapInfo.MapOrigin.X, mapInfo.MapOrigin.Y, mapInfo.PinPosition.X, mapInfo.PinPosition.Y))
#
</code>

|- style="background-color:#f0f0f0;"
|**Note:**
|The pin position is an offset from the origin, so you have to add them to get absolute location

|- style="background-color:#f0f0f0;"
|**Returns**
|MapInfo{ PinPosition, MapOrigin, MapEnd }
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|serial - Serial of the t-map

|}

##  Pets 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Rename Pet**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.PetRename(int or mobile, string )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Rename a specific pet.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|newname

|}

##  String Prompt Response 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Reset Prompt response**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ResetPrompt()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Reset a prompt response.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Reset Prompt response**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.HasPrompt()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Check if have a prompt request.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Wait Prompt**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.WaitForPrompt(int)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Wait a prompt response.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|delaytowait

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Cancel Prompt**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.CancelPrompt()
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Cancel a prompt request.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Prompt Response**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ResponsePrompt( string )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Response a prompt request.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|reponsetosend

|}

##  Ignore List 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Add object to Ignore List**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.IgnoreObject( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Add an object to ignore list. Can add serial, items or mobiles
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|mobtoignore

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Remove object from Ignore List**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.UnIgnoreObject( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Remove object from ignore list. Can remove serial, items or mobiles
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|mobtounignore

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Check object if present in Ignore List**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.CheckIgnoreObject( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Check object from ignore list, return true if present. Can check serial, items or mobiles
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|mobtocheck

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Clear ignore list**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ClearIgnore( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Clear ignore list from all object
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Change the current active profile**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.ChangeProfile(profileName )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |CHanges the current active profile
use in your code like:
<code>
#
Misc.ChangeProfile("profileName")
#
</code>
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|newProfileName

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Distance between 2 places using UO algorithm**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Misc.Distance(X1, Y1, X2, Y2)
|-
|colspan="2" |**Description:**
|-
|colspan="2" | Compute the distance between 2 places using UO algorithm for distance
use in your code like:
<code>
#
d = Misc.Distance(10, 10, 20, 20)
#
</code>
|- style="background-color:#f0f0f0;"
|**Returns**
|int
|-
|**In Object:**
|Misc
|- style="background-color:#f0f0f0;"
|**Parameters:**
|X1 - x origin
|Y1 - y origin
|X2 - x dest
|Y2 - y dest

|}

