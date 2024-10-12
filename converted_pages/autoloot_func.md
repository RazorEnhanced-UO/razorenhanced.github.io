# Scripting - Autoloot control function
Here can find some information about Enhanced Scripting function to control autoloot engine by script!

## Get Loot List Contents

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Get AutoLoot List Contents**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.GetList( string LootListName, getMinusOneItems=False )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Get a list of autoloot items, Graphics of -1 are only returned if getMinusOneItems is set to True
|- style="background-color:#f0f0f0;"
|**Returns**
|List < AutoLootItem >
|-
|**In Object:**
|AutoLoot { Name, Graphics, Color }
|- style="background-color:#f0f0f0;"
|**Parameters:**
|string NameOfLootList 
|- style="background-color:#f0f0f0;"
|**Example**
|<code>
items = AutoLoot.GetList("default")
for autoItem in items:
    Misc.SendMessage("id: 0X{:x}".format(autoItem.Graphics))
</code>
|}

## Check Status

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Check AutoLoot Status**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.Status( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Get a bool value of autoloot engine status, if running or not
|- style="background-color:#f0f0f0;"
|**Returns**
|bool
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}
## Start

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Start AutoLoot**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.Start( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Start autoloot engine.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

##  Stop 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Stop AutoLoot**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.Stop( )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Stop autoloot engine.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|none

|}

## Change List

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Change AutoLoot item list**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.ChangeList(string)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Change list of autoloot item, List must be exist in autoloot GUI configuration
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|ListName

|}

## Custom List

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Start Autoloot whit custom parameters**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.RunOnce(AutoLootItem, int, Filter)
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Start autoloot with specific parameters: AutoLootItem is a list type for item, delay in second for grab and filter for search on ground
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|AutoLootItem ItemList, double DelayGrabInMilliSecond, Filter FilterForSearch

|}

##  SetNoOpenCorpse 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Temporarily change NoOpenCorpse setting**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | AutoLoot.SetNoOpenCorpse( bool )
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Temporarily set the NoOpenCorpse flag on the AutoLooter. Change not persisted.
|- style="background-color:#f0f0f0;"
|**Returns**
|bool - the previous setting
|-
|**In Object:**
|AutoLoot
|- style="background-color:#f0f0f0;"
|**Parameters:**
|bool True / False 
|- style="background-color:#f0f0f0;"
|**Example**
|<code>
oldValue = AutoLoot.SetNoOpenCorpse(True)
</code>
|}


