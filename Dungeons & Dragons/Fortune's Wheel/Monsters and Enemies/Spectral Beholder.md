---
tags: dnd, monster
---

# Spectral Beholder

*Through the ghostlight haze, the eye trembles. A voice, distant yet mournful, echoes from the beholder’s maw:*
> I was Lord Enveris… I begged them not to flood the tombs... you must... find my sigil-sealed ring... free us...

```statblock  
image: [[spectral_beholder.png]]
name: Spectral Beholder
size: Huge
type: undead
subtype: spirit
alignment: chaotic evil
ac: 16
hp: 136
hit_dice: 16d10 + 48
speed: fly 20 ft. (hover)
stats: [10, 14, 16, 17, 15, 18]
saves:
  - con: 6
  - wis: 5
  - cha: 7
skillsaves:
  - perception: 8
  - intimidation: 7
damage_vulnerabilities:
damage_resistances: Acid, Lightning, Fire; Bludgeoning, Piercing, and Slashing from nonmagical weapons
damage_immunities: Cold, Necrotic, Poison
condition_immunities: Charmed, Frightened, Grappled, Paralyzed, Petrified, Poisoned, Prone, Restrained
senses: Darkvision 120 ft., Passive Perception 18
languages: Deep Speech, understands all it knew in life
cr: 8
spells:
traits:
  - [Incorporeal Form, "The spectral beholder can pass through solid objects as if they were difficult terrain. It takes 10 (3d6) force damage if it ends its turn inside an object."]
  - [Ethereal Glare, "Nonmagical ranged attacks automatically miss the beholder unless the attacker can see into the Ethereal Plane or use force/radiant damage."]
  - [Undead Dominion, "Undead allies within 30 ft. gain resistance to radiant damage and advantage on saving throws against turning."]
actions:
  - [Spectral Bite, "Melee Weapon Attack: +6 to hit, reach 5 ft., one target. Hit: 22 (4d10) necrotic damage."]
  - [Eye Rays, "The beholder shoots three of the following magical eye rays at random. Each ray targets one to three creatures it can see within 120 ft. Each target must succeed on a DC 15 saving throw or suffer the listed effect:
    1. **Withering Ray (Con)**: 36 (8d8) necrotic damage.
    2. **Gravemind Ray (Wis)**: Frightened for 1 minute. Save ends at end of each turn.
    3. **Drowned Vision Ray (Int**): Stunned until end of target’s next turn.
    4. **Entropy Ray (Dex)**: 27 (6d8) force damage and visible aging. Half damage on success.
    5. **Chains of the Dead Ray (Str)**: Restrained for 1 minute. Save ends each turn.
    6. **Deathlight Ray (Cha)**: 22 (5d8) radiant damage. If reduced to 0 HP, nearby allies must save vs. fear."]
legendary_actions:
  - [Ray Attack, "The beholder uses one random Eye Ray."]
  - [Phase Drift, "The beholder teleports up to 20 ft. to a watery surface it can see."]
  - [Gaze of the Deep (Costs 2), "One creature within 30 ft. must succeed on a DC 15 Wisdom saving throw or fall unconscious, lulled by ghostly drowning. Wakes on damage or ally action."]
```

