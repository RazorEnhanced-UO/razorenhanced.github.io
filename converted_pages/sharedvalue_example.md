#  Set Shared Value 
<code>
Misc.SetSharedValue("Key", "Some value set for key")
</code>

#  Get that Shared Value
<code>
test = Misc.ReadSharedValue("Key")
# test should now contain "Some value set for key"
</code>

#  Example Usage


In practice I use this to dynamically affect script behavior. 

For instance I have a fight script that I want to sometimes use whirlwind and sometimes use momentum based on the fighting situation. I don't want to stop mid fight and change the script, and I don't want to copy the whole script just to get this ability to change behavior. 
 
In my fight script I have:
<code>
if Misc.CheckSharedValue("UseMomentum"):
    use_momentum = Misc.ReadSharedValue("UseMomentum")
else:    
    use_momentum = True
if use_momentum and (not Player.SpellIsEnabled('Momentum Strike')):    
    Spells.CastBushido('Momentum Strike')
    Misc.Pause(500)
else:
    Use_weapon_special(weapon)
</code>

Then, in another script attached to a hot key:
<code>
if Misc.CheckSharedValue("UseMomentum"):
    Misc.SetSharedValue("UseMomentum", not(Misc.ReadSharedValue("UseMomentum")))
else:    
    Misc.SetSharedValue("UseMomentum", False)

Mobiles.Message(Player.Serial, 5, "Use Momentum: {}".format(Misc.ReadSharedValue("UseMomentum")))
</code>
