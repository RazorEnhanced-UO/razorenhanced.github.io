<code>
#Bushido Training by Frank Castle
#You need two wolf spiders and a 100% poison weapon for this. 
#It is NOT fast but it will get you there.

while True:
    Bushido = Player.GetSkillValue('Bushido')
    if Bushido < 60 and Player.Mana > 10:
        Spells.CastBushido("Confidence")
        Misc.Pause(1500)
        
    elif Bushido >= 60 and Bushido < 75 and Player.Mana > 5:
        Spells.CastBushido('Counter Attack')
        Misc.Pause(1500)   
   
    elif Bushido >= 75 and Bushido < 101  and Player.Mana > 10:
        Spells.CastBushido('Lightning Strike')
        Misc.Pause(2000)  

    elif Bushido >= 101 and Player.Mana > 10:
        Spells.CastBushido('Momentum Strike')
        Misc.Pause(1500)    
        
</code>        