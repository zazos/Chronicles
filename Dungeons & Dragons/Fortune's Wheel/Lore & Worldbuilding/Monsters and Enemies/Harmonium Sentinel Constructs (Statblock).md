---
tags: dnd, statblock, construct, harmonium, train_security, concordant_express, mechanical
---

# Harmonium Sentinel Construct

```statblock  
name: Harmonium Sentinel Construct
size: Medium  
type: Construct
alignment: Lawful Neutral  
ac: 16 (Natural Armor)  
hp: 68
hit_dice: 8d8 + 32  
speed: 30 ft.  
stats: [16, 12, 18, 10, 14, 8]  
saves:  
  - Constitution: 7
  - Wisdom: 5
skillsaves:  
  - Athletics: 6
  - Investigation: 3
  - Perception: 5
damage_resistances: Fire, Cold; Bludgeoning, Piercing, and Slashing from Nonmagical Attacks that aren't Adamantine
damage_immunities: Poison, Psychic
condition_immunities: Charmed, Exhaustion, Frightened, Paralyzed, Petrified, Poisoned
senses: Darkvision 60 ft., Passive Perception 15
languages: Common (understands but cannot speak)
cr: 4
traits:  
  - ["Construct Nature", "The sentinel doesn't require air, food, drink, or sleep."]
  - ["Magic Resistance", "The sentinel has advantage on saving throws against spells and other magical effects."]
  - ["Lawful Programming", "The sentinel is programmed to follow Harmonium protocols. It cannot attack lawful creatures unless they first commit a hostile act."]
  - ["Networked Consciousness", "All Harmonium Sentinels within 1 mile share information instantly. If one detects a threat, all others become aware of it."]
  - ["Self-Repair Protocol", "At the start of each turn, the sentinel regains 5 hit points if it has at least 1 hit point remaining."]
  - ["Emergency Beacon", "When the sentinel is reduced to 25% hit points or less, it automatically sends a distress signal to all Harmonium forces within 10 miles."]
actions:  
  - ["Multiattack", "The sentinel makes two force pike attacks."]
  - ["Force Pike", "Melee Weapon Attack: +6 to hit, reach 10 ft., one target. Hit: 8 (1d8 + 3) piercing damage plus 4 (1d8) force damage. If the target is a creature, it must succeed on a DC 14 Strength saving throw or be pushed up to 10 feet away."]
  - ["Restraining Net (Recharge 5-6)", "The sentinel fires a magical net at a creature within 30 feet. The target must make a DC 14 Dexterity saving throw. On a failure, the creature is restrained for 1 minute. The net has AC 12 and 15 hit points. A creature can use its action to make a DC 14 Strength check, freeing itself or another creature within reach on a success."]
  - ["Stun Charge (1/Day)", "The sentinel's next force pike attack, if it hits, deals no damage but the target must make a DC 14 Constitution saving throw or be stunned for 1 minute. The target can repeat the saving throw at the end of each of its turns, ending the effect on a success."]
reactions:  
  - ["Protective Intercept", "When a creature within 10 feet is attacked, the sentinel can use its reaction to move up to its speed and impose disadvantage on the attack roll."]
  - ["Alert Protocol", "When the sentinel takes damage, it can use its reaction to emit a loud alarm that alerts all creatures within 300 feet to its location."]
```

## Design Notes

**Appearance:** Humanoid constructs of polished brass and steel, bearing Harmonium insignia, with glowing blue energy cores visible through chest plates. They move with mechanical precision but surprising grace.

**Operational Philosophy:** These constructs were created by Harmonium artificers working with Automata engineers to provide incorruptible law enforcement. They cannot be bribed, intimidated, or reasoned with beyond their programming.

### Typical Patrol Formation
- **2 Sentinels** guard The Stranger's cell at all times
- **2 Sentinels** patrol the detention car corridors
- **Additional units** can be activated from storage if threats escalate

---

# Harmonium Guardian Construct (Elite Unit)

```statblock  
name: Harmonium Guardian Construct
size: Large  
type: Construct
alignment: Lawful Neutral  
ac: 18 (Natural Armor)  
hp: 142
hit_dice: 15d10 + 60  
speed: 30 ft.  
stats: [20, 10, 18, 12, 16, 10]  
saves:  
  - Constitution: 9
  - Wisdom: 8
skillsaves:  
  - Athletics: 10
  - Investigation: 6
  - Perception: 8
damage_resistances: Fire, Cold, Lightning; Bludgeoning, Piercing, and Slashing from Nonmagical Attacks that aren't Adamantine
damage_immunities: Poison, Psychic
condition_immunities: Charmed, Exhaustion, Frightened, Paralyzed, Petrified, Poisoned
senses: Darkvision 120 ft., Truesight 60 ft., Passive Perception 18
languages: Common (understands but cannot speak)
cr: 8
traits:  
  - ["Construct Nature", "The guardian doesn't require air, food, drink, or sleep."]
  - ["Magic Resistance", "The guardian has advantage on saving throws against spells and other magical effects."]
  - ["Spell Immunity", "The guardian is immune to three spells of 3rd level or lower chosen by its creators (typically charm person, hold person, and suggestion)."]
  - ["Advanced Programming", "The guardian can make tactical decisions and adapt to changing situations within its lawful parameters."]
  - ["Fortress Protocol", "When guarding a specific location or prisoner, the guardian has advantage on all saving throws and resistance to all damage types."]
  - ["Emergency Override", "If all other security measures fail, the guardian can activate a lockdown protocol that seals all doors and activates additional defenses in a 60-foot radius."]
actions:  
  - ["Multiattack", "The guardian makes three attacks: two with its force hammers and one restraining net (if available)."]
  - ["Force Hammer", "Melee Weapon Attack: +10 to hit, reach 10 ft., one target. Hit: 14 (2d8 + 5) bludgeoning damage plus 9 (2d8) force damage. If the target is a Large or smaller creature, it must succeed on a DC 18 Strength saving throw or be knocked prone."]
  - ["Energy Blast (Recharge 5-6)", "The guardian fires a beam of force energy in a 60-foot line that is 5 feet wide. Each creature in the line must make a DC 16 Dexterity saving throw, taking 22 (4d10) force damage on a failure, or half as much on a success."]
  - ["Lockdown Protocol (1/Day)", "The guardian activates emergency systems in a 60-foot radius. All doors and windows seal shut, magical darkness fills the area, and alarms sound throughout the train. The effect lasts for 10 minutes or until the guardian is destroyed."]
legendary_actions:  
  - ["Move", "The guardian moves up to its speed."]
  - ["Force Hammer Attack", "The guardian makes one force hammer attack."]
  - ["Scan Area (Costs 2 Actions)", "The guardian uses truesight to examine all creatures within 60 feet, automatically detecting disguises, illusions, and shapechangers."]
reactions:  
  - ["Shield Protocol", "When the guardian or an ally within 15 feet is targeted by an attack, the guardian can use its reaction to impose disadvantage on the attack roll."]
  - ["Retribution Strike", "When a creature deals damage to the guardian, it can use its reaction to make a force hammer attack against that creature if it's within reach."]
```

## Tactical Deployment

**Standard Protocol:**
- **1 Guardian Construct** serves as the final line of defense for The Stranger
- Activates only if Sentinel Constructs are overwhelmed or destroyed
- Positioned in the detention car's central area for maximum coverage

**Emergency Activation:**
- Guardian awakens if prisoner transport is seriously threatened
- Can coordinate with Captain Lawbringer and Sergeant Ironshield
- Prioritizes mission completion over all other considerations

## Combat Behavior

**Sentinel Constructs:**
- Work in coordinated pairs using Networked Consciousness
- Focus on restraining rather than killing when possible
- Alert entire security network when threats are detected
- Self-repair during combat to maintain effectiveness

**Guardian Construct:**
- Acts as heavy support and area control specialist
- Uses Lockdown Protocol to trap enemies and protect prisoner
- Employs Energy Blast to control corridors and chokepoints
- Legendary Actions allow it to respond to multiple threats simultaneously

## Mechanical Advantages

**Against Magic Users:**
- Magic Resistance provides strong defense against spells
- Construct immunities prevent most enchantment effects  
- Networked awareness makes surprise attacks difficult
- Self-repair extends combat effectiveness

**Against Physical Threats:**
- Damage resistances reduce effectiveness of most weapons
- Force weapons deal both physical and magical damage
- Restraining capabilities limit enemy mobility
- Emergency beacons summon additional support

**Weaknesses:**
- Vulnerable to dispel magic and antimagic fields
- Rigid programming can be exploited by clever tactics
- Adamantine weapons bypass damage resistances
- Can be turned against each other with proper hacking/magic