<code>

#Necromancy Trainer v1.0 by FrankC
#
# What you need:
#
#
# 1) A suit with Lower Reagent Cost 100%
#
# 2) Full Necromancy Spellbook
#
# 3) A weapon Equipped(If under 20 Necro)
#
# Once you have those Press Play  
#
#






while True:
    Necro = Player.GetSkillValue('Necromancy')
    if Necro < 35 and Player.Mana > 7:
        Spells.CastNecro('Curse Weapon')
        Misc.Pause(2000)
        
    elif Necro >= 35 and Necro < 50 and Player.Mana > 5:
        Spells.CastNecro('Pain Spike')
        Target.WaitForTarget(4000,False)
        Target.Self()
        Misc.Pause(2000)   
   
    elif Necro >= 50 and Necro < 65  and Player.Mana > 11:
        Spells.CastNecro('Horrific Beast')
        Misc.Pause(3500)  
       
    elif Necro >= 65 and Necro < 85  and Player.Mana > 23:
        if Player.BuffsExist('Horrific Beast'):      
            Misc.Pause (400)
            Spells.CastChivalry("Horrific Beast")
            Misc.Pause(3500)
        else:    
            Spells.CastNecro('Wither')
            Misc.Pause(4000)

    elif Necro >= 85 and Necro < 100  and Player.Mana > 23:
        Spells.CastNecro('Lich Form')
        Misc.Pause(4000) 

    elif Necro >= 100 and Necro != Player.GetSkillCap('Necromancy') and Player.Mana > 23:
        Spells.CastNecro('Vampiric Embrace')
        Misc.Pause(8000)         
   
    elif Necro == Player.GetSkillCap('Necromancy'):
        Misc.ScriptStop('Necromancy Trainer.py')
        
</code>        
    