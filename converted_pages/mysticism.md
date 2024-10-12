<code>

#Mysticism Trainer v1.0 by FrankC
#
# What you need:
#
#
# 1) A suit with Lower Reagent Cost 100%
#
# 2) Full Mysticism Spellbook
#
# 3) Over 30.0 Mysticism. Buy it up if you do not have it.
#
#
# Once you have those Press Play. 
#
#

while True:
    Mysticism = Player.GetSkillValue('Mysticism')
    if Mysticism < 63 and Player.Mana > 20:
        Spells.CastMysticism('Stone Form')
        Misc.Pause(4500)
        
    elif Mysticism >= 63 and Mysticism < 80 and Player.Mana > 30:
        Spells.CastMysticism('Cleansing Winds')
        Target.WaitForTarget(4000,False)
        Target.Self()
        Misc.Pause(2000)   
   
    elif Mysticism >= 80 and Mysticism < 95  and Player.Mana > 40:
        Spells.CastMysticism('Hail Storm')
        Target.WaitForTarget(4000,False)
        Target.Self()
        Misc.Pause(3000)  

    elif Mysticism >= 95 and Mysticism != Player.GetSkillCap('Mysticism') and Player.Mana > 60:
        Spells.CastMysticism('Nether Cyclone')
        Target.WaitForTarget(4000,False)
        Target.Self()
        Misc.Pause(3000)         
   
    elif Mysticism == Player.GetSkillCap('Mysticism'):
        Misc.ScriptStop('Mysticism Trainer.py')
        
</code>        
