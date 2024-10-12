<code>
#Blacksmithing Trainer by Frank Castle
#
#What you need:
# 1 - 30.0+ Blacksmith Skill. If you do not have it buy it up. 
# 2 - a player made Tinker Tools
# 3 - a chest with plenty of iron ingots
# 
# Written and tested on OSI. 

from System.Collections.Generic import List

global stoCont

stoCont = Target.PromptTarget('Target your resource chest')
Misc.Pause(100)
Items.UseItem(stoCont)
Misc.Pause(1100)

Player.UseSkill('Hiding')
Misc.Pause(11000)

def makeLast(skill, item):
    Blacksmith = Player.GetSkillValue('Blacksmith')
    tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
    Items.UseItem(tongs)
    while Blacksmith < skill and Blacksmith != Player.GetSkillCap('Blacksmith'):
        Blacksmith = Player.GetSkillValue('Blacksmith')
        checkIngots()
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
            Items.UseItem(tongs)
           
        if Items.BackpackCount(item,-1) > 0:
                smelts = Items.FindByID(item,-1,Player.Backpack.Serial)
                Misc.Pause(100)
                Gumps.WaitForGump(460, 1500)
                Gumps.SendAction(460, 7000)
                Target.WaitForTarget(1500, False)
                Target.TargetExecute(smelts)
                Misc.Pause(300)     
        


def checkIngots():
    if Items.BackpackCount(0x1BF2,0x0000) < 50:
        global stoCont
        Misc.Pause(1100)
        ingot = Items.FindByID(0x1BF2,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(ingot,Player.Backpack.Serial,500)
        Misc.Pause(1100)

def checkTools():
    countOne = Items.BackpackCount(0x1EB9,-1)
    while countOne < 3:
        Misc.Pause(1100)
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 11)
        Misc.Pause(1500)
        countOne = Items.BackpackCount(0x1EB9,-1)
        Misc.SendMessage('I have {} tinker tools in my bag'.format(countOne),48)
        
    countTwo = Items.BackpackCount(0x0FBC,-1)
    while countTwo < 3:
        Misc.Pause(1100)
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 20)
        Misc.Pause(1500)
        countTwo = Items.BackpackCount(0x0FBC,-1)
        Misc.SendMessage('I have {} tongs in my bag'.format(countOne),48)
        
def selectCraft():        
    Blacksmith = Player.GetSkillValue('Blacksmith')
    if Blacksmith < 35:
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 45)   #MAKE DAGGERS
        makeLast(35, 0x0F51)
        Misc.Pause(100)


    if Blacksmith >= 35 and Blacksmith < 45 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 77)   #MAKE MACES
        makeLast(45, 0x0F5C)
        Misc.Pause(100)        
        
    if Blacksmith >= 45 and Blacksmith < 50 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 78)   #MAKE MAULS
        makeLast(50, 0x143B)
        Misc.Pause(100)
        
    if Blacksmith >= 50 and Blacksmith < 55 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 44)   #MAKE CUTLASSES
        makeLast(55, 0x1441)
        Misc.Pause(100)
        
    if Blacksmith >= 55 and Blacksmith < 59 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 48)   #MAKE LONGSWORDS
        makeLast(59, 0x0F61)
        Misc.Pause(100)       
        
    if Blacksmith >= 59 and Blacksmith < 61 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 75)   #MAKE WARFORK
        makeLast(61,0x1405)
        Misc.Pause(100) 

    if Blacksmith >= 61 and Blacksmith < 70 :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 74)   #MAKE SPEARS
        makeLast(70, 0x0F62)
        Misc.Pause(100)         
        
    if Blacksmith >= 70 and Blacksmith < 106 and Blacksmith != Player.GetSkillCap('Blacksmith') :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 10)   #MAKE PLATE GORGETS
        makeLast(106, 0x1413)
        Misc.Pause(100)         
        
    if Blacksmith >= 106 and Blacksmith < 108 and Blacksmith != Player.GetSkillCap('Blacksmith') :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 9)   #MAKE PLATE GLOVES
        makeLast(108, 0x1414)
        Misc.Pause(100)         

    if Blacksmith >= 108 and Blacksmith < 116 and Blacksmith != Player.GetSkillCap('Blacksmith') :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 8)   #MAKE PLATE ARMS
        makeLast(116, 0x1410)
        Misc.Pause(100)         
                
    if Blacksmith >= 116 and Blacksmith < 118 and Blacksmith != Player.GetSkillCap('Blacksmith') :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 11)   #MAKE PLATE LEGS
        makeLast(118, 0x1411)
        Misc.Pause(100)        

    if Blacksmith >= 118 and Blacksmith < 120 and Blacksmith != Player.GetSkillCap('Blacksmith') :
        checkIngots()
        checkTools()
        tongs = Items.FindByID(0x0FBC,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tongs)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 12)   #MAKE PLATE CHEST
        makeLast(120, 0x1415)
        Misc.Pause(100)   
        
    if Blacksmith == Player.GetSkillCap('Blacksmith'):
        Misc.ScriptStopAll()
        
    Misc.Pause(1100)

while True:
    selectCraft()
    
</code>    