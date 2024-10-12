<code>
#Fletching Trainer by Frank Castle
#
#What you need:
# 1 - 30.0+ Tinkering Skill. If you do not have it buy it up. 
# 1 - 30.0+ Fletching Skill. If you do not have it buy it up.
# 2 - a player made Tinker Tools
# 3 - a chest with plenty of iron ingots and wood
# 4 - a trash barrel nearby. Secure it.
# 
# Written and tested on OSI. 

from System.Collections.Generic import List

global stoCont



    

stoCont = Target.PromptTarget('Target your resource chest')
Misc.Pause(100)
Items.UseItem(stoCont)
Misc.Pause(1100)

GFilter = Items.Filter()
GFilter.RangeMax = 5
GFilter.OnGround = True
GFilter.Enabled = True
GFilter.Movable = True
garbagecan = List[int]((0x0E77, 0x0E77))  
GFilter.Graphics = garbagecan

Player.UseSkill('Hiding')
Misc.Pause(11000)


def makeLast(skill, item):
    Fletching = Player.GetSkillValue('Fletching')
    fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
    Items.UseItem(fTool)
    while Fletching < skill and Fletching != Player.GetSkillCap('Fletching'):
        Fletching = Player.GetSkillValue('Fletching')
        checkBoards()
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        Misc.SendMessage('Crafting Last',48)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
            Items.UseItem(fTool)
           
        if Items.BackpackCount(item,-1) > 0:
            craft = Items.FindByID(item,-1,Player.Backpack.Serial)
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(craft,garbagecan,0)
            Misc.Pause(1100)
    
def makeLast2(skill, item):
    Fletching = Player.GetSkillValue('Fletching')
    fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
    Items.UseItem(fTool)
    while Fletching < skill and Fletching != Player.GetSkillCap('Fletching'):
        Fletching = Player.GetSkillValue('Fletching')
        global stoCont
        Misc.SendMessage('Getting Boards',48)
        Misc.Pause(1100)
        board = Items.FindByID(0x1BD7,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(board,Player.Backpack.Serial,1)
        Misc.Pause(1100)
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        Misc.SendMessage('Crafting Last',48)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
            Items.UseItem(fTool)
           
        if Items.BackpackCount(item,-1) > 20:
            move = Items.FindByID(item,-1,Player.Backpack.Serial)
            Misc.Pause(500)
            Items.Move(move,stoCont,0)
            Misc.Pause(1100)        

def makeLast3(skill, item):
    Fletching = Player.GetSkillValue('Fletching')
    fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
    Items.UseItem(fTool)
    while Fletching < skill and Fletching != Player.GetSkillCap('Fletching'):
        Fletching = Player.GetSkillValue('Fletching')
        global stoCont
        Misc.SendMessage('Getting Boards',48)
        Misc.Pause(1100)
        board = Items.FindByID(0x1BD7,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(board,Player.Backpack.Serial,1)
        Misc.Pause(1100)
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 1999)
        Misc.Pause(500)
        Misc.SendMessage('Crafting Last',48)
        
        if Journal.Search('You have worn out') == True:
            Journal.Clear()
            checkTools()
            fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
            Items.UseItem(fTool)
           
        if Items.BackpackCount(item,-1) > 0:
            craft = Items.FindByID(item,-1,Player.Backpack.Serial)
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(craft,garbagecan,0)
            Misc.Pause(1100)

def checkBoards():
    if Items.BackpackCount(0x1BD7,0x0000) < 25:
        global stoCont
        Misc.SendMessage('Getting Boards',48)
        Misc.Pause(1100)
        board = Items.FindByID(0x1BD7,0x0000,stoCont)
        Misc.Pause(100)
        Items.Move(board,Player.Backpack.Serial,200)
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
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 11)
        Misc.Pause(1500)
        countOne = Items.BackpackCount(0x1EB9,-1)
        Misc.SendMessage('I have {} tinker tools in my bag'.format(countOne),48)
        
    countTwo = Items.BackpackCount(0x1022,-1)
    while countTwo < 3:
        tinkerTool = Items.FindByID(0x1EB9,-1,Player.Backpack.Serial)
        Misc.Pause(100)
        Items.UseItem(tinkerTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 28)
        Misc.Pause(1500)
        countTwo = Items.BackpackCount(0x1022,-1)
        Misc.SendMessage('I have {} fletchers tools in my bag'.format(countTwo),48)
        
def selectCraft():
    Misc.Pause(2000)
    Fletching = Player.GetSkillValue('Fletching')
    if Fletching < 35:
        board = Items.FindByID(0x1BD7,0x0000,Player.Backpack.Serial)
        if board:
            Items.Move(board,stoCont,0)
            Misc.Pause(1100)
        checkTools()
        boards = Items.FindByID(0x1BD7,0x0000,stoCont)
        Items.Move(boards,Player.Backpack.Serial,1)
        Misc.Pause(1100)
        Misc.SendMessage('Making Shafts',48)
        Misc.Pause(1000)
        Fletching = Player.GetSkillValue('Fletching')
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 2)
        Misc.Pause(2000)
        Misc.SendMessage('Making Shafts',48)   
        makeLast2(35, 0x1BD4)
        Misc.Pause(100)


    if Fletching >= 35 and Fletching < 55 :
        lastCraft = Items.FindByID(0x1BD4, -1, Player.Backpack.Serial)
        if lastCraft:
            Misc.Pause(500)
            Items.Move(lastCraft,stoCont,0)
            Misc.Pause(1100)
        checkBoards()
        checkTools()
        Misc.SendMessage('Making Bows',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 6)   
        makeLast(55, 0x13B2)
        Misc.Pause(100)        
        
    if Fletching >= 55 and Fletching < 60 :
        lastCraft = Items.FindByID(0x13B2, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        checkBoards()    
        checkTools()
        Misc.SendMessage('Making Fukiya Darts',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 5)   
        makeLast3(60, 0x2806)
        Misc.Pause(100)
        
    if Fletching >= 60 and Fletching < 70 :
        lastCraft = Items.FindByID(0x2806, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        checkBoards()
        checkTools()
        Misc.SendMessage('Making Crossbows',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 7)   
        makeLast(70, 0x0F4F)
        Misc.Pause(100)
        
    if Fletching >= 70 and Fletching < 80 :
        lastCraft = Items.FindByID(0x0F4F, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        checkBoards()
        checkTools()
        Misc.SendMessage('Making Composite Bows',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 9)   
        makeLast(80, 0x26C2)
        Misc.Pause(100)       
        
    if Fletching >= 80 and Fletching < 90 :
        lastCraft = Items.FindByID(0x26C2, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        checkBoards()
        checkTools()
        Misc.SendMessage('Making Heavy Crossbows',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 8)   
        makeLast(90 ,0x13FD)
        Misc.Pause(100) 
        
    if Fletching >= 90 and Fletching < 100 :
        lastCraft = Items.FindByID(0x13FD, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        checkBoards()
        checkTools()
        Misc.SendMessage('Making Repeating Crossbows',48)
        fTool = Items.FindByID(0x1022,-1,Player.Backpack.Serial)
        Items.UseItem(fTool)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 10)   
        makeLast(100 ,0x26C3)
        Misc.Pause(100) 
 
        
    if Fletching == Player.GetSkillCap('Fletching'):
        lastCraft = Items.FindByID(0x26C3, -1, Player.Backpack.Serial)
        if lastCraft:
            garbagecans = Items.ApplyFilter(GFilter)
            Misc.Pause(500)
            garbagecan = Items.Select(garbagecans, 'Nearest')
            Misc.Pause(500)
            Items.Move(lastCraft,garbagecan,0)
            Misc.Pause(1100)
        Misc.SendMessage('You have reached Grandmaster',48)    
        Misc.ScriptStopAll()
        
    Misc.Pause(1100)

while True:
    selectCraft()
</code>