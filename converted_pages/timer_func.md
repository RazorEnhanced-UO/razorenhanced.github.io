#  Scripting - Timer control function 

## Timer Create

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Create a Named Timer**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Timer.Create(string TimerName, int ms_timer )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Create a timer with the provided name that will expire in ms_timer time (in milliseconds)
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Timer
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none
|-
|colspan="2" |Example:
<code>
Timer.Create("Test", 5000)
</code>
|}

## Timer Check

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Get remaining time for a named timer**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Timer.Remaining(string TimerName)
|-
|colspan="2" |**Description:**
|-
|colspan="2" | Returns the milliseconds remaining for a timer
|- style="background-color:#f0f0f0;"
|**Returns**
| int ms_time 
|-
|**In Object:**
|Timer
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string TimerName
|-
|colspan="2" |Example:
<code>
Timer.Create("Test", 5000)
#
while Timer.Check("Test"):
    remain = Timer.Remaining("Test")
    Misc.SendMessage("TimeLeft: {}".format(remain))
    Misc.Pause(500
</code>
|}


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Check if a timer is expired or not**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Timer.Check(string TimerName)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Check if a timer object is expired or not, 
|- style="background-color:#f0f0f0;"
|**Returns**
|bool - True if not expired, false if expired
|-
|**In Object:**
|Timer
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string TimerName

|}
