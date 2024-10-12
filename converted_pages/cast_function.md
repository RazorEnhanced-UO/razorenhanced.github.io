#  Scripting - Cast function 
Here can find some information about Enhanced Scripting function about cast spell and ability. Note that the optional targeted form is not available on all servers. If the optional targeted form DOES work on your server, you still have to wait after casting with Misc.Pause(...) for whatever the cast time should be. The server wont accept other commands until the cast time has completed.

##  Magery 
{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Cast Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.Cast(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Cast the spell specified, the spellname doesn't have to be spelled exactly. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target. Note that this form can cast any of the classes of spell (Necro Mage...).
|- style="background-color:#f0f0f0;"
|**Returns**
|none
|-
|**In Object:**
|Items
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String SpellName, *optionally Item or Int for a target*

|}

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Magery Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastMagery(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a magery spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Clumsy
  * Create Food
  * Feeblemind
  * Heal
  * Magic Arrow
  * Night Sight
  * Reactive Armor
  * Weaken
  * Agility
  * Cunning
  * Cure
  * Harm
  * Magic Trap
  * Magic Untrap
  * Protection
  * Strength
  * Bless
  * Fireball
  * Magic Lock
  * Poison
  * Telekinesis
  * Teleport
  * Unlock
  * Wall of Stone
  * Arch Cure
  * Arch Protection
  * Curse
  * Fire Field
  * Greater Heal
  * Lightning
  * Mana Drain
  * Recall
  * Blade Spirits
  * Dispel Field
  * Incognito
  * Magic Reflection
  * Mind Blast
  * Paralyze
  * Poison Field
  * Summon Creature
  * Dispel
  * Energy Bolt
  * Explosion
  * Invisibility
  * Mark
  * Mass Curse
  * Paralyze Field
  * Reveal
  * Chain Lightning
  * Energy Field
  * Flamestrike
  * Gate Travel
  * Mana Vampire
  * Mass Dispel
  * Meteor Swarm
  * Polymorph
  * Earthquake
  * Energy Vortex
  * Resurrection
  * Summon Air Elemental
  * Summon Daemon
  * Summon Earth Elemental
  * Summon Fire Elemental
  * Summon Water Elemental

|}

##  Necro 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Necro Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastNecro(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a necro spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Curse Weapon
  * Pain Spike
  * Corpse Skin
  * Evil Omen
  * Blood Oath
  * Wraith Form
  * Mind Rot
  * Summon Familiar
  * Horrific Beast
  * Animate Dead
  * Poison Strike
  * Wither
  * Strangle
  * Lich Form
  * Exorcism
  * Vengeful Spirit
  * Vampiric Embrace

|}

##  Chivalry 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Chivalry Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastChivalry(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a chivalry spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Close Wounds
  * Remove Curse
  * Cleanse By Fire
  * Consecrate Weapon
  * Sacred Journey
  * Divine Fury
  * Dispel Evil
  * Enemy Of One
  * Holy Light
  * Noble Sacrifice

|}

##  Bushido 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Bushido Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastBushido(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a bushido spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Honorable Execution
  * Confidence
  * Counter Attack
  * Lightning Strike
  * Evasion
  * Momentum Strike

|}

##  Ninjitsu 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Ninjitsu Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastNinjitsu(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a ninjitsu spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Animal Form
  * Backstab
  * Surprise Attack
  * Mirror Image
  * Shadow jump
  * Focus Attack
  * Ki Attack

|}

##  Spellweaving 


{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Spellweaving Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastSpellweaving(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a spellweaving spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Arcane Circle
  * Gift Of Renewal
  * Immolating Weapon
  * Attune Weapon
  * Thunderstorm
  * Natures Fury
  * Summon Fey
  * Summoniend
  * Reaper Form
  * Wildfire
  * Essence Of Wind
  * Dryad Allure
  * Ethereal Voyage
  * Word Of Death
  * Gift Of Life
  * Arcane Empowerment

|}

##  Mysticism 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Mysticism Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastMysticism(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a mysticism spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Animated Weapon
  * Healing Stone
  * Purge
  * Enchant
  * Sleep
  * Eagle Strike
  * Stone Form
  * SpellTrigger
  * Mass Sleep
  * Cleansing Winds
  * Bombard
  * Spell Plague
  * Hail Storm
  * Nether Cyclone
  * Rising Colossus

|}

##  Mastery 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Mastery Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastMastery(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a mastery spell by spellname. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * Inspire
  * Invigorate
  * Resilience
  * Perseverance
  * Tribulation
  * Despair
  * Death Ray
  * Ethereal Blast
  * Nether Blast
  * Mystic Weapon
  * Command Undead
  * Conduit
  * Mana Shield
  * Summon Reaper
  * Enchanted Summoning
  * Anticipate Hit
  * Warcry
  * Intuition
  * Rejuvenate
  * Holy Fist
  * Shadow
  * White Tiger Form
  * Flaming Shot
  * Playing The Odds
  * Thrust
  * Pierce
  * Stagger
  * Toughness
  * Onslaught
  * Focused Eye
  * Elemental Fury
  * Called Shot
  * Saving Throw
  * Shield Bash
  * Bodyguard
  * Heighten Senses
  * Tolerance
  * Injected Strike
  * Potency
  * Rampage
  * Fists Of Fury
  * Knockout
  * Whispering
  * Combat Training
  * Boarding
  *

|}

##  Druid

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Druid Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastDruid(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a druid spell by spellname. Few servers support this and it must be enabled in options panel. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * **Bark Skin** : Turns the druid's skin to bark, increasing physical, poison and energy resistence while reducing fire resistence.

  * **Circle Of Thorns** : Creates a ring of thorns preventing an enemy from moving.

  * **Deadly Spores** : The enemy is afflicted by poisonous spores.

  * **Enchanted Grove** : Causes a grove of magical trees to grow, hiding the player for a short time.

  * **Firefly** : Summons a tiny firefly to light the Druid's path. The Firefly is a weak creature with little or no combat skills.

  * **Forest Kin** : Summons from a list of woodland spirits that will fight for the druid and assist him in different ways.

  * **Grasping Roots** : Summons roots from the ground to entangle a single target.

  * **Hibernate** : Causes the target to go to sleep.

  * **Hollow Reed** : Increases both the strength and the intelligence of the Druid.

  * **Hurricane** : Calls forth a violent hurricane that damages any enemies within range.

  * **Lure Stone** : Creates a magical stone that calls all nearby animals to it.

  * **Mana Spring** : Creates a magical spring that restores mana to the druid and any party members within range.

  * **Mushroom Gateway** : A magical circle of mushrooms opens, allowing the Druid to step through it to another location.

  * **Pack Of Beasts** : Summons a pack of beasts to fight for the Druid. Spell length increases with skill.

  * **Restorative Soil** : Saturates a patch of land with power, causing healing mud to seep through . The mud can restore the dead to life.

  * **Shield Of Earth** : A quick-growing wall of foliage springs up at the bidding of the Druid.

  * **Spring Of Life** : Creates a magical spring that heals the Druid and their party.

  * **Swarm Of Insects** : Summons a swarm of insects that bite and sting the Druid's enemies.

  * **Treefellow** : Summons a powerful woodland spirit to fight for the Druid.

  * **Volcanic Eruption** : A blast of molten lava bursts from the ground, hitting every enemy nearby.

|}

##  Cleric 

{|style="font-size:85%; border:solid 2px; width: 50%;"
|style="font-size:150%;  padding: 2px" colspan="2" | **Player Cast Cleric Spell**
|- style="background-color:#f0f0f0;"
|**Syntax**
|style="width: 90%" | Spells.CastCleric(string SpellName [,item or int target])
|-
|colspan="2" |**Description:**
|-
|colspan="2" |Player cast a cleric spell by spellname. Few servers support this, and it must be enabled in options panel. The target is optional and not available on all servers, but if specified the cast spell will be applied to the specified target.
|- style="background-color:#f0f0f0;"
|**Returns**
|void
|-
|**In Object:**
|Spells
|- style="background-color:#f0f0f0;"
|**Parameters:**
|String Spellname
|-
|**Parameters list:**
|
  * **Angelic Faith** : Turns you into an angel, boosting your stats. At 100 Spirit Speak you get +20 Str/Dex/Int. Every 5 points of SS = +1 point to each stat, at a max of +24. Will also boost your Anatomy, Mace Fighting and Healing, following the same formula.

  * **Banish Evil** : Banishes Undead targets. Auto kills rotting corpses, lich lords, etc. Works well at Doom Champ. Does not produce a corpse however

  * **Dampen Spirit** : Drains the stamina of your target, according to the description

  * **Divine Focus** : Heal for more, but may be broken.

  * **Hammer of Faith** : Summons a War Hammer with Undead Slayer on it for you

  * **Purge** : Cleanses Poison. Better than Cure

  * **Restoration** : Resurrection. Brings the target back with 100% HP/Mana

  * **Sacred Boon** : A HoT, heal over time spell, that heals 10-15 every few seconds

  * **Sacrifice** : Heals your party members when you take damage. Sort of like thorns, but it heals instead of hurts

  * **Smite** : Causes energy damage

  * **Touch of Life** : Heals even if Mortal Strike or poison are active on the target

  * **Trial by Fire** : Attackers receive damage when they strike you, sort of like a temporary RPD buff



|}