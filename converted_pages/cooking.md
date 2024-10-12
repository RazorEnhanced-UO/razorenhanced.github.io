<code>
#Cooking Trainer by Frank Castle
#
#What you need:
# 1 - 30.0+ Tinkering Skill. If you do not have it buy it up. 
# 1 - 30.0+ Cooking Skill. If you do not have it buy it up.
# 2 - a player made Tinker Tools
# 3 - a chest with plenty of iron ingots, flour and fish steaks
# 4 - an Endless Decanter of Water. 
# 5 - A nearby Oven and a Nearby watersource that your decanter is linked to 
# Written and tested on OSI. 



from System.Collections.Generic import List

global stoCont

stoCont = Target.PromptTarget('Target your resource chest')
Misc.Pause(100)
Items.UseItem(stoCont)
Misc.Pause(1100)

def checkIngots():
    if Items.BackpackCount(0x1BF2,0x0000) < 15:
        global stoCont
        Misc.SendMessage('Getting Ingots',48)
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
        Misc.Pause(1100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 11)
        Misc.Pause(1500)
        countOne = Items.BackpackCount(0x1EB9,-1)
        Misc.SendMessage('I have {} tinker tools in my bag'.format(countOne),48)
        
    countTwo = Items.BackpackCount(0x097F,-1)
    while countTwo < 3:
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(1100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 26)
        Misc.Pause(1500)
        countTwo = Items.BackpackCount(0x097F,-1)
        Misc.SendMessage('I have {} skillets in my bag'.format(countTwo),48)

Player.UseSkill('Hiding')
Misc.Pause(11000)


def makeLast(skill, item, itemName):
    Cooking = Player.GetSkillValue('Cooking')
    skillet = Items.FindByID(0x097F,-1,Player.Backpack.Serial)
    Items.UseItem(skillet)
    while Cooking < skill and Cooking != Player.GetSkillCap('Cooking'):
        Cooking = Player.GetSkillValue('Cooking')
        if Cooking < 75:
            checkFlour()
        if Cooking >= 75:
            checkFish()
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        Misc.SendMessage('Making {}'.format(itemName),48)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            Misc.Pause(100)
            skillet = Items.FindByID(0x097F,-1,Player.Backpack.Serial)
            Items.UseItem(skillet)
           
        if Items.BackpackCount(item,-1) > 20:
            craft = Items.FindByID(item,-1,Player.Backpack.Serial)
            Items.Move(craft,stoCont,0)
            Misc.Pause(1100)
            Misc.SendMessage('Moving',48)
            
def checkFlour():
    if Items.BackpackCount(0x103A,0x0000) < 1:
        global stoCont
        Misc.SendMessage('Getting Resources',48)
        Misc.Pause(1100)
        resource = Items.FindByID(0x1039,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(resource,Player.Backpack.Serial,5)
        Misc.Pause(1100)
        while Items.BackpackCount(0x1039,-1) > 0:
            unopenBag = Items.FindByID(0x1039,-1,Player.Backpack.Serial)
            Misc.Pause(100)
            Items.UseItem(unopenBag)
            Misc.Pause(1000)
        
def checkFish():
    if Items.BackpackCount(0x097A,0x0000) < 10:
        global stoCont
        Misc.SendMessage('I like fishes 'cause they're so delicious!!',48)
        Misc.Pause(1100)
        resource = Items.FindByID(0x097A,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(resource,Player.Backpack.Serial,500)
        Misc.Pause(1100)        
                
def selectCraft():
    Misc.Pause(2000)
    Cooking = Player.GetSkillValue('Cooking')
    if Cooking < 75:
        makeFirst(0x103D, 'dough', 2, 0x103D, 75)
        
    if Cooking >= 75 and Cooking < 100:
        makeFirst(0x103D, 'miso soup', 32, 0x284D, 100)    

    if Cooking == Player.GetSkillCap('Cooking'):
        lastCraft = Items.FindByID(0x284D,-1,Player.Backpack.Serial)
        if lastCraft:
            Items.Move(lastCraft,stoCont,0)
            Misc.Pause(1100)
            Misc.SendMessage('Moving',48)
            Misc.Pause(500)
        Misc.SendMessage('You have reached your skill cap.',48)    
        Misc.ScriptStopAll()
        
    Misc.Pause(1100)
        
def makeFirst(lastcraft, itemName, gumpButton, itemID, maxSkill):
    lastCraft = Items.FindByID(lastcraft, -1, Player.Backpack.Serial)
    if lastCraft:
        Items.Move(lastCraft,stoCont,0)
        Misc.Pause(1100)
        Misc.SendMessage('Moving',48)
        Misc.Pause(500)
    Cooking = Player.GetSkillValue('Cooking')
    if Cooking < 75:
        checkFlour()
    if Cooking >= 75:
        checkFish()
    checkTools()
    Misc.SendMessage('Making {}'.format(itemName),48)
    skillet = Items.FindByID(0x097F,-1,Player.Backpack.Serial)
    Items.UseItem(skillet)
    Gumps.WaitForGump(460, 10000)
    Gumps.SendAction(460, gumpButton)   
    makeLast(maxSkill, itemID, itemName)
    Misc.Pause(100)        


while True:
    selectCraft()
</code>