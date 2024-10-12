#  Scripting - Sound data and function 
Here can find some information about Enhanced Scripting function and data misc!

##  Debug 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Sound Logging**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Sound.Log(bool)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Log a message to sysmessage every time a sound is played.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Sound
|- style="background-color:#f0f0f0;"
|**Parameters:**
|bool True/False True - Enable logging False - Disable logging

|}


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Wait For Sound**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Sound.WaitForSound(List[Int32] soundIds, timeout=-1)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Wait for a sound to be played that the id is in the list of soundIds provided
|- style="background-color:#f0f0f0;"
|**Returns**
| True - Sound played, False timeout occurred
|-
|**In Object:**
|Sound
|- style="background-color:#f0f0f0;"
|**Parameters:**
|List[Int32] soundIds, int timeout

|}

