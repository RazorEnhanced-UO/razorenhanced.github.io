<code>
# Chivalry Trainer v1.0 by FrankC
#
# What you need:
#
#
# 1) Tithing Points. Don't be cheap. Buy the max.
#
# 2) Chivalry Spellbook
#
# 3) Over 30.0 Chivalry. Buy it up if you do not have it.
#
# 4) A weapon in your hand.
#
# Once you have those Press Play. 
#
#

while True:
    Chivalry = Player.GetSkillValue('Chivalry')
    if Chivalry < 45 and Player.Mana > 10:
        Spells.CastChivalry('Consecrate Weapon')
        Misc.Pause(4500)
        
    elif Chivalry >= 45 and Chivalry < 60 and Player.Mana > 15:
        Spells.CastChivalry('Divine Fury')
        Misc.Pause(2000)   
   
    elif Chivalry >= 60 and Chivalry < 70  and Player.Mana > 20:
        Spells.CastChivalry('Enemy Of One')
        Misc.Pause(3000)  

    elif Chivalry >= 70 and Chivalry < 90  and Player.Mana > 10:
        Spells.CastChivalry('Holy Light')
        Misc.Pause(3000) 
        
    elif Chivalry >= 90 and Chivalry != Player.GetSkillCap('Chivalry') and Player.Mana > 20:
        Spells.CastChivalry('Noble Sacrifice')
        Misc.Pause(6000)         
   
    elif Chivalry == Player.GetSkillCap('Chivalry'):
        Misc.ScriptStop('Chivalry Trainer.py')
        
</code>        