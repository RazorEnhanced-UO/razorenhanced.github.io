** Get Random Integer From Range **
<code>
from System import Random

variable = Random().Next(0, 60000)    # range 0 - 60000
Misc.SendMessage(variable)
</code>

** Rail Example **
<code>
from System.Collections.Generic import List 

def gotoLocation(x1, y1):
    Coords = PathFinding.Route() 
    Coords.X = x1
    Coords.Y = y1
    Coords.MaxRetry = -1
    PathFinding.Go(Coords)
    Misc.Pause(200)
    
railCoords1 = [[3676, 2271],[3676, 2290],[3675, 2296],[3649, 2296]]      
railCoords2 = [[3631, 2376],[3631, 2402],[3631, 2448],[3631, 2488]]

def gosomewhere():              
    for coords in railCoords1:
        gotoLocation(coords[0],coords[1])
        
def gosomewhereelse():
    for coords in railCoords2:
        gotoLocation(coords[0],coords[1])
        
def dosomething():
    pass # filler till you code something
    #what to do

gosomewhere()
dosomething()    
gosomewhereelse()
dosomething()    
</code>
** Send Message to Discord Webhook **
<code>
URI = 'https://discordapp.com/...'# your webhook url string 
alert = 'Testing'  ####WHAT TO ALERT
report = "username=" + Player.Name + "&content=" + alert
PARAMETERS=report
from System.Net import WebRequest
request = WebRequest.Create(URI)
request.ContentType = "application/x-www-form-urlencoded"
request.Method = "POST"
from System.Text import Encoding
bytes = Encoding.ASCII.GetBytes(PARAMETERS)
request.ContentLength = bytes.Length
reqStream = request.GetRequestStream()
reqStream.Write(bytes, 0, bytes.Length)
reqStream.Close()
response = request.GetResponse()
from System.IO import StreamReader
result = StreamReader(response.GetResponseStream()).ReadToEnd().replace('\r', '\n')
</code>
** Train Skill by Skill Level Example (Magery by Casting)**
<code>
def medcheck():
    if Player.Mana < 24:
        if Timer.Check('med') == False:
            Player.UseSkill('Meditation')
            Misc.Pause(500)
            Timer.Create('med', 5000)
            if Player.BuffsExist('Meditation'):
                while Player.Mana != Player.ManaMax:
                    Misc.Pause(2000)


def Magery():
    if Player.GetSkillValue('Magery') >= 0 and Player.GetSkillValue('Magery') < 30:
        Spells.CastMagery('Cure')
        Target.WaitForTarget(2000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 30 and Player.GetSkillValue('Magery') < 45:
        Spells.CastMagery('Bless')
        Target.WaitForTarget(2000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 45 and Player.GetSkillValue('Magery') < 56:
        Spells.CastMagery('Greater Heal')
        Target.WaitForTarget(4000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 56 and Player.GetSkillValue('Magery') < 66:
        Spells.CastMagery('Dispel Field')
        Target.WaitForTarget(5000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 66 and Player.GetSkillValue('Magery') < 75:
        Spells.CastMagery('Reveal')
        Target.WaitForTarget(5000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 75 and Player.GetSkillValue('Magery') < 90:
        Spells.CastMagery('Mass Dispel')
        Target.WaitForTarget(5000,False)
        Target.Self()
    elif Player.GetSkillValue('Magery') >= 90 and Player.GetSkillValue('Magery') < 120:
        Spells.CastMagery('Earthquake')
        Misc.Pause(4000)
    Misc.Pause(500)
while True:
    Magery()
    if Player.GetSkillValue('Meditation') >= 70:
        medcheck()
 </code>  

** Constant Monitor Player Status Example (if poisoned drink cure potion) ** 
<code>
curePot = 0x0F07
while True:
    if Player.Poisoned:
        Items.UseItemByID(curePot)
    else:
        Misc.Pause(400)        
</code>

** Train Ninja / Hiding / Stealth **
<code>
# MUST HAVE REQUIRED NINJA TO ATTEMPT SHADOWJUMP
# best to start in an area between north south trees with visible tiles between

while not Player.IsGhost:   
    if Player.Visible:
        Target.Cancel()        
        Player.UseSkill("Hiding")
        Misc.Pause(3000)
        
    elif not Player.Visible: 
        Spells.CastNinjitsu("Shadowjump")
        Target.WaitForTarget(3000, False)
        Target.TargetExecuteRelative(Player.Serial,-1)
        
    if not Player.Visible:
        Player.Walk("North")
        Player.Walk("North")
  
    if not Player.Visible:    
        Player.Walk("South")
        Player.Walk("South")
        
    Misc.Pause(400)
</code>    