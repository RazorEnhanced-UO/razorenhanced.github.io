<code>
#Tailoring Trainer by Frank Castle
#
#What you need:
# 1 - 30.0+ Tinkering Skill. If you do not have it buy it up. 
# 1 - 30.0+ Tailoring Skill. If you do not have it buy it up.
# 2 - a player made Tinker Tools
# 3 - a chest with plenty of iron ingots and cloth
#     Cloth NOT bolts.  This will not cut bolts into cloth currently. And only have one color of cloth. 
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
        
    countTwo = Items.BackpackCount(0x0F9D,-1)
    while countTwo < 3:
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(1100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 14)
        Misc.Pause(1500)
        countTwo = Items.BackpackCount(0x0F9D,-1)
        Misc.SendMessage('I have {} sewing kits in my bag'.format(countTwo),48)

def scissorsCheck(): 
    scissorsCount = Items.BackpackCount(0x0F9E,-1)
    if scissorsCount < 1:
        checkTools()
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 8)
        Misc.Pause(500)
        Misc.SendMessage('I now have scissors',48)
        Misc.Pause(4000)

scissorsCheck()

Player.UseSkill('Hiding')
Misc.Pause(11000)


def makeLast(skill, item, itemName):
    Tailoring = Player.GetSkillValue('Tailoring')
    sewingKit = Items.FindByID(0x0F9D,-1,Player.Backpack.Serial)
    Items.UseItem(sewingKit)
    while Tailoring < skill and Tailoring != Player.GetSkillCap('Tailoring'):
        Tailoring = Player.GetSkillValue('Tailoring')
        checkCloth()
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        Misc.SendMessage('Making {}'.format(itemName),48)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            Misc.Pause(100)
            sewingKit = Items.FindByID(0x0F9D,-1,Player.Backpack.Serial)
            Items.UseItem(sewingKit)
           
        if Items.BackpackCount(item,-1) > 0:
            craft = Items.FindByID(item,-1,Player.Backpack.Serial)
            scissors = Items.FindByID(0x0F9E,-1,Player.Backpack.Serial)
            Items.UseItem(scissors)
            Target.WaitForTarget(1500,False)
            Target.TargetExecute(craft)
            Misc.Pause(1100)
            Misc.SendMessage('Cutting',48)
            
        if Items.BackpackCount(0x0E21,-1) > 300:
            bandaid = Items.FindByID(0x0E21,-1,Player.Backpack.Serial)
            Misc.Pause(100)
            Items.Move(bandaid, stoCont, 0)
            Misc.Pause(1100)
            Misc.SendMessage('Moving bandages',48)
            
def checkCloth():
    if Items.BackpackCount(0x1766,0x0000) < 25:
        global stoCont
        Misc.SendMessage('Getting Cloth',48)
        Misc.Pause(1100)
        cloth = Items.FindByID(0x1766,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(cloth,Player.Backpack.Serial,1000)
        Misc.Pause(1100)
        

        
def scissorsCheck(): 
    scissorsCount = Items.BackpackCount(0x0F9E,-1)
    if scissorsCount < 1:
        checkTools()
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 8)
        Misc.Pause(500)
        Misc.SendMessage('I now have scissors',48)
        Misc.Pause(4000)

        
def selectCraft():
    Misc.Pause(2000)
    Tailoring = Player.GetSkillValue('Tailoring')
    if Tailoring < 35:
        makeFirst(0x152E, 'shortpants', 37, 0x152E, 35)
        
    if Tailoring >= 35 and Tailoring < 41.4:
        makeFirst(0x152E, 'fur cape', 28, 0x2309, 41.4)    

    if Tailoring >= 41.4 and Tailoring < 50:
        makeFirst(0x2309, 'cloak', 25, 0x1515, 50) 
        
    if Tailoring >= 50 and Tailoring < 54:
        makeFirst(0x1515, 'fur boots', 601, 0x2307, 54) 
        
    if Tailoring >= 54 and Tailoring < 65:
        makeFirst(0x2307, 'robe', 26, 0x1F03, 65) 
 
    if Tailoring >= 65 and Tailoring < 72:
        makeFirst(0x1F03, 'kasa', 17, 0x2798, 72)

    if Tailoring >= 72 and Tailoring < 78:
        makeFirst(0x2798, 'ninja tabi', 602, 0x2797, 78) 
 
    if Tailoring >= 78 and Tailoring < 90:
        makeFirst(0x2797, 'oil cloth', 500, 0x175D, 90)  
   
    if Tailoring >= 90 and Tailoring < 110 and Tailoring != Player.GetSkillCap('Tailoring'):
        makeFirst(0x175D, 'elven shirt', 70, 0x3175, 110)         
        
    if Tailoring >= 110 and Tailoring < 117 and Tailoring != Player.GetSkillCap('Tailoring'):
        makeFirst(0x3175, 'gargish cloth kilt', 203, 0x4063, 117)

    if Tailoring >= 117 and Tailoring < 120 and Tailoring != Player.GetSkillCap('Tailoring'):
        makeFirst(0x4063, 'gargish cloth arms', 200, 0x405F, 120)        

    if Tailoring == Player.GetSkillCap('Tailoring'):
        lastCraft = Items.FindByID(0x405F, -1, Player.Backpack.Serial)
        if lastCraft:
            scissors = Items.FindByID(0x0F9E,-1,Player.Backpack.Serial)
            Items.UseItem(scissors)
            Target.WaitForTarget(1500,False)
            Target.TargetExecute(lastCraft)
            Misc.Pause(500)
        Misc.SendMessage('You have reached your skill cap.',48)    
        Misc.ScriptStopAll()
        
    Misc.Pause(1100)
        
def makeFirst(lastcraft, itemName, gumpButton, itemID, maxSkill):
    lastCraft = Items.FindByID(lastcraft, -1, Player.Backpack.Serial)
    if lastCraft:
        scissors = Items.FindByID(0x0F9E,-1,Player.Backpack.Serial)
        Items.UseItem(scissors)
        Target.WaitForTarget(1500,False)
        Target.TargetExecute(lastCraft)
        Misc.Pause(500)
    checkCloth()
    checkTools()
    Misc.SendMessage('Making {}'.format(itemName),48)
    sewingKit = Items.FindByID(0x0F9D,-1,Player.Backpack.Serial)
    Items.UseItem(sewingKit)
    Gumps.WaitForGump(460, 10000)
    Gumps.SendAction(460, gumpButton)   
    makeLast(maxSkill, itemID, itemName)
    Misc.Pause(100)        


while True:
    selectCraft()
</code>