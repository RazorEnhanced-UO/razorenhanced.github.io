<code>

#Spellweaving Trainer v1.0 by Frank Castle
#
# What you need:
#
# 1) Spellweaving Spellbook with Arcane Circle, Immolating Weapon, Reaper Form, Essence of Wind, Wildfire, and Word of Death
#
# 2) A weapon equipped in your hand
#
# Once you have those Press Play
#
#






while True:
    Spellweaving = Player.GetSkillValue('Spell Weaving')
    if Spellweaving < 20 and Player.Mana > 20:
        Spells.CastSpellweaving('Arcane Circle')
        Misc.Pause(2000)
        
    if Spellweaving >= 20 and Spellweaving < 36 and Player.Mana > 20:
        Spells.CastSpellweaving('Immolating Weapon')
        Misc.Pause(2200)   
   
    if Spellweaving >= 36 and Spellweaving < 58  and Player.Mana > 40:
        Spells.CastSpellweaving('Reaper Form')
        Misc.Pause(4000)  
       
    if Spellweaving >= 58 and Spellweaving < 74  and Player.Mana > 60:
        Spells.CastSpellweaving('Essence Of Wind')
        Misc.Pause(5000)

    if Spellweaving >= 74 and Spellweaving < 92  and Player.Mana > 60:
        Spells.CastSpellweaving('Wildfire')
        Target.WaitForTarget(4000,False)
        Target.Self()
        Misc.Pause(5000) 

    if Spellweaving >= 92 and Spellweaving != Player.GetSkillCap('Spell Weaving') and Player.Mana > 60:
        if Player.Hits < 50:
            Spells.CastSpellweaving('Gift Of Renewal')
            Target.WaitForTarget(4000,False)
            Target.Self()
            Misc.Pause(2000)
        else:
            Spells.CastSpellweaving('Word Of Death')
            Target.WaitForTarget(4000,False)
            Target.Self()
        Misc.Pause(2000)            
   
    if Spellweaving == Player.GetSkillCap('Spell Weaving'):
        Misc.ScriptStopAll()
        
</code>        