<code>
#Runic Atlas Crafter by Frank Castle
#
# Instructions:
#
# Have plenty of Exceptional Scribes Pens with makers mark on them
# Have GM Inscription.  It just makes it easier.
# Have a resource container with plenty of scrolls and regs
# Have at least 100 mana
# Have a trash can within reach
# This will move all Runic Atlases you have in your backpack to your storage container before it starts.
# Buy a bunch of blank runes.  This will make Atlases until you run out of runes. 
# This will use existing gate and recall scrolls if you have them in your storage container. 
#   Otherwise it will make gate and recall scrolls

 
from System.Collections.Generic import List

stoCont = Target.PromptTarget('Target your Storage Container')
Items.UseItem(stoCont)
Misc.Pause(2000)

bookBag = Target.PromptTarget('Target your BookBag')
Items.UseItem(stoCont)
Misc.Pause(2000)

GFilter = Items.Filter()
GFilter.RangeMax = 5
GFilter.OnGround = True
GFilter.Enabled = True
GFilter.Movable = True
garbagecan = List[int]((0x0E77, 0x0E77))  
GFilter.Graphics = garbagecan

global pen
pen = Items.FindByID(0x0FBF,-1,Player.Backpack.Serial)

def checkRunes():
    runeAmt = Items.ContainerCount(Player.Backpack.Serial,0x1F14,0x0000)
    Misc.SendMessage('I have {} runes in my backpack'.format(runeAmt),44)
    if runeAmt < 3:
        Misc.SendMessage('I need more runes.  Stopping script.')
        Misc.ScriptStopAll()
        
def getMats():
    rScroll = Items.FindByID(0x1F4C,-1,stoCont)
    gScroll = Items.FindByID(0x1F60,-1,stoCont)
    bScroll = Items.FindByID(0x0EF3,-1,stoCont)
    gMats = [0x0F7A,0x0F86,0x0F8C]
    rMats = [0x0F7A,0x0F86,0x0F7B]
    checkRunes()
    if Items.ContainerCount(stoCont,0x1F4C,0x0000) > 3:
        Items.Move(rScroll, Player.Backpack.Serial, 3)
        Misc.Pause(1100)
    else:
        makeRecalls()
        
    if Items.ContainerCount(stoCont,0x1F60,0x0000) > 3:
        Items.Move(gScroll, Player.Backpack.Serial, 3)
        Misc.Pause(1100)
    else:
        makeGates()
    
    Items.Move(bScroll, Player.Backpack.Serial, 24)
    Misc.Pause(1100)

def makeGates():
    while Items.ContainerCount(Player.Backpack.Serial,0x1F60,-1) < 3:
        checkPen()
        checkgMats()
        checkMana(50)
        Items.UseItem(pen)
        Misc.Pause(1100)
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 52)
        Misc.Pause(2000)

def makeRecalls():
    while Items.ContainerCount(Player.Backpack.Serial,0x1F4C,-1) < 3:
        checkPen()
        checkrMats()
        checkMana(50)
        Items.UseItem(pen)
        Misc.Pause(1100)
        Gumps.WaitForGump(460, 1500)
        Gumps.SendAction(460, 32)
        Misc.Pause(2000)        
        
def checkgMats():
    scroll = Items.FindByID(0x0EF3,-1,Player.Backpack.Serial)
    gMats = [0x0F7A,0x0F86,0x0F8C]
    if Items.ContainerCount(Player.Backpack.Serial,0x0EF3,-1) < 1:
        bScroll = Items.FindByID(0x0EF3,-1,stoCont)
        Items.Move(bScroll,Player.Backpack.Serial,3)
        Misc.Pause(1100)
    for g in gMats:
        if Items.ContainerCount(Player.Backpack.Serial,g,-1) < 1:
            mat = Items.FindByID(g,-1,stoCont)
            Items.Move(mat,Player.Backpack.Serial,3)
            Misc.Pause(1100)

def checkrMats():
    scroll = Items.FindByID(0x0EF3,-1,Player.Backpack.Serial)
    rMats = [0x0F7A,0x0F86,0x0F7B]
    if Items.ContainerCount(Player.Backpack.Serial,0x0EF3,0x0000) < 1:
        bScroll = Items.FindByID(0x0EF3,-1,stoCont)
        Items.Move(bScroll,Player.Backpack.Serial,3)
        Misc.Pause(1100)
    for m in rMats:
        if Items.ContainerCount(Player.Backpack.Serial,m,0x0000) < 1:
            mat = Items.FindByID(m,-1,stoCont)
            Items.Move(mat,Player.Backpack.Serial,3)
            Misc.Pause(1100)
            
def checkPen():
    curCharges = Items.FindByID(0x0FBF,-1,Player.Backpack.Serial)
    Items.WaitForProps(curCharges,2000)
    props = Items.GetPropStringList(curCharges.Serial)
    Misc.Pause(500)
    prop = props[3].split(' ')[2]
    Misc.SendMessage(prop)
    Misc.Pause(500)
    if int(prop) < 2:
        global pen
        garbagecans = Items.ApplyFilter(GFilter)
        Misc.Pause(500)
        garbagecan = Items.Select(garbagecans, 'Nearest')
        Misc.Pause(500)
        Items.Move(pen,garbagecan,0)
        Misc.Pause(1100)
        checkPen()
        pen = Items.FindByID(0x0FBF,-1,Player.Backpack.Serial)
        
def checkMana(mana):
    while Player.Mana < mana:
        Player.UseSkill('Meditation')
        Misc.Pause(11500)
        
def makeAtlas():
    while Items.ContainerCount(Player.Backpack.Serial,0x1F14,0x0000): 
        getMats()
        checkPen()
        Items.UseItem(pen)
        Gumps.WaitForGump(460, 10000)
        Gumps.SendAction(460, 694)
        Misc.Pause(2000)
        Atlas = Items.FindByID(0x9C16,-1,Player.Backpack.Serial)
        Items.Move(Atlas,bookBag,0)
        Misc.Pause(1100)

def moveOldRunebooks():
    for items in Items.FindBySerial(Player.Backpack.Serial).Contains:
        if items.ItemID == 0x9C16:
            Atlas = Items.FindBySerial(items.Serial)
            Items.Move(Atlas, stoCont, 0)
            Misc.Pause(1100)
            
moveOldRunebooks()            
makeAtlas()
</code>