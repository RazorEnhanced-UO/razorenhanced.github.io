<code>
#Alchemy Trainer by Frank Castle
#
#What you need:
# 1 - 30.0+ Tinkering Skill. If you do not have it buy it up. 
# 1 - 30.0+ Alchemy Skill. If you do not have it buy it up.
# 2 - a player made Tinker Tools
# 3 - a chest with plenty of iron ingots, reagents, and bottles
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

mandrakeroot = 0x0F86
bloodmoss = 0x0F7B
sulphurousash = 0x0F8C
nightshade = 0x0F88
blackpearl = 0x0F7A
spidersilk = 0x0F86
ginseng = 0x0F85
garlic = 0x0F84
gravedust = 0x0F8F


def makeLast(skill, item, reg1):
    Alchemy = Player.GetSkillValue('Alchemy')
    mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
    Items.UseItem(mortar)
    while Alchemy < skill and Alchemy != Player.GetSkillCap('Alchemy'):
        Alchemy = Player.GetSkillValue('Alchemy')
        checkRegs(reg1)
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
            Items.UseItem(mortar)
           
        if Items.BackpackCount(item,-1) > 20:
            potion = Items.FindByID(item,-1,Player.Backpack.Serial)
            Misc.Pause(100)
            Items.Move(potion,stoCont,0)
            Misc.Pause(300)     
        


def checkRegs(reg1):
    if Items.BackpackCount(reg1,0x0000) < 15:
        global stoCont
        Misc.Pause(1100)
        Reg = Items.FindByID(reg1,-1,stoCont)
        Misc.Pause(100)
        Items.Move(Reg,Player.Backpack.Serial,500)
        Misc.Pause(1100)
        
    if Items.BackpackCount(0x0F0E,0x0000) < 5: #bottles
        global stoCont
        Misc.Pause(1100)
        bottle = Items.FindByID(0x0F0E,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(bottle ,Player.Backpack.Serial,100)
        Misc.Pause(1100)        
        
def checkIngots():
    if Items.BackpackCount(0x1BF2,0x0000) < 15:
        global stoCont
        Misc.Pause(1100)
        ingot = Items.FindByID(0x1BF2,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(ingot,Player.Backpack.Serial,40)
        Misc.Pause(1100)
        
def checkTools():
    checkIngots()
    countOne = Items.BackpackCount(0x1EB9,-1)
    while countOne < 3:
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 11)
        Misc.Pause(1500)
        countOne = Items.BackpackCount(0x1EB9,-1)
        Misc.SendMessage('I have {} tinker tools in my bag'.format(countOne),48)
        
    countTwo = Items.BackpackCount(0x0E9B,-1)
    while countTwo < 3:
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 9)
        Misc.Pause(1500)
        countTwo = Items.BackpackCount(0x0E9B,-1)
        Misc.SendMessage('I have {} morter and pestle in my bag'.format(countOne),48)

        
def selectCraft():        
    Alchemy = Player.GetSkillValue('Alchemy')
    if Alchemy < 45:
        checkRegs(bloodmoss)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 20)   #MAKE AGILITY
        makeLast(45, 0x0F08, bloodmoss)
        Misc.Pause(100)


    if Alchemy >= 45 and Alchemy < 55 :
        lastPot = Items.FindByID(0x0F08, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F7B, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)
        checkRegs(mandrakeroot)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 50)   #MAKE STRENGTH
        makeLast(55, 0x0F09, mandrakeroot)
        Misc.Pause(100)        
        
    if Alchemy >= 55 and Alchemy < 65 :
        lastPot = Items.FindByID(0x0F09, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F86, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)
        checkRegs(bloodmoss)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 21)   #MAKE GREATER AGILITY
        makeLast(65, 0x0F08, bloodmoss)
        Misc.Pause(100)
        
    if Alchemy >= 65 and Alchemy < 75 :
        lastPot = Items.FindByID(0x0F08, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F7B, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)    
        checkRegs(mandrakeroot)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 51)   #MAKE GREATER STRENGTH
        makeLast(75, 0x0F09, mandrakeroot)
        Misc.Pause(100)
        
    if Alchemy >= 75 and Alchemy < 85 :
        lastPot = Items.FindByID(0x0F09, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F86, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)    
        checkRegs(ginseng)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 42)   #MAKE GREATER HEAL
        makeLast(85, 0x0F0C, ginseng)
        Misc.Pause(100)       
        
    if Alchemy >= 85 and Alchemy < 95 :
        lastPot = Items.FindByID(0x0F0C, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F85, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)    
        checkRegs(garlic)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 72)   #MAKE GREATER CURE
        makeLast(95 ,0x0F07, garlic)
        Misc.Pause(100) 
        
    if Alchemy >= 95 and Alchemy < 100 :
        lastPot = Items.FindByID(0x0F07, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F84, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)    
        checkRegs(gravedust)
        checkTools()
        mortar = Items.FindByID(0x0E9B,-1,Player.Backpack.Serial)
        Items.UseItem(mortar)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 102)   #MAKE GREATER CONFLAGRATION
        makeLast(100 ,0x0F06, gravedust)
        Misc.Pause(100)        

        
    if Alchemy == Player.GetSkillCap('Alchemy'):
        lastPot = Items.FindByID(0x0F06, -1, Player.Backpack.Serial)
        if lastPot:
            Items.Move(lastPot,stoCont,0)
            Misc.Pause(1100)
        lastreg = Items.FindByID(0x0F8F, -1, Player.Backpack.Serial) 
        if lastreg:
            Items.Move(lastreg,stoCont,0)
            Misc.Pause(1100)    
        Misc.ScriptStopAll()
        
    Misc.Pause(1100)

while True:
    selectCraft()
</code>