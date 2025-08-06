---
tags: dnd, sigil, shemeshka, r04m, main_quest
banner: "![[Fortune's Wheel/Images dump/Fortunes Wheel emergence point.webp]]"
---

# Chapter II: Fortune's Wheel

## Part 1: Arrival at the Wheel

*As you climb the last rung of the rusted ladder and force open the forgotten hatch, you push up into a crumbling shrine. The ceiling is collapsed, vines and cobwebs coat old pews, and the dust of decades swirls around them. A Harmonium patrol passes nearby on the street outside—but they don't seem to notice you. You step through an overgrown arch, brushing aside ivy and there it is: Fortune's Wheel, in all its gilded, garish glory.*

[[Fortunes Wheel exterior.webp|Show To Players]]

The door of Fortune's Wheel opens into the Dragon Bar. When they enter, a polite, snappily dressed tiefling bellhop named [[Valek.webp|Valek]] delivers a letter to them that read as follows:

> Honoured guests,
> Welcome! I’ve been expecting you. Don’t fret; you’re safe here. Our city’s so-called “peacekeepers” hold no sway in my establishment. 
> I’ve prepared accommodations for each of you upstairs. Valek will show you to your rooms. Rest, relax, and enjoy room service on me. When you’re ready for entertainment, a gift awaits you at the casino cage. 
> I’ll be down a bit later. See you soon. 
> Your benignant host, 
> Shemeshka

Valek shows the characters to their rooms: luxurious suites fit for royalty on the second floor. A clean set of fine clothes awaits each character.

[[Fortunes Wheel clothes.webp|Show To Players]]

Valek caters to their basic needs, offering to shine equipment, answer questions about the casino, or provide a short tour. With the characters in Valek’s capable hands, Josbert wishes the characters good luck and departs the casino.

### Planar Proprietor
Shemeshka’s reputation precedes her. Characters who question Josbert, Valek, or other locals about her might learn the following details:
- **Arcanaloth:** Shemeshka is an influential arcanaloth who takes pride in her appearance. She owns Fortune’s Wheel and appears in the casino regularly.
- **Influencer:** She’s fantastically wealthy and an information broker par excellence.
- **Spy Master:** Powerful in her own right, Shemeshka also commands a loyal web of spies that could bring the city’s factions to their knees overnight.

---

## Part 2: The Casino Floor

```leaflet
id: FortunesWheelMap
image: [[Fortune's Wheel/Images dump/Fortunes Wheel Map.png]]
bounds: [[0,0], [510, 789]]
height: 550px
width: 100%
lat: 255
long: 395
minZoom: -2
maxZoom: 1.5
defaultZoom: 0
zoomDelta: 1
unit: ft
scale: 5
recenter: false
darkmode: false
```

### F1: Dragon Bar
The Dragon Bar is an extravagant reception area where gamblers gather before hitting the casino proper. At the southeast corner of the bar is a simple door minded by an oni bouncer named Vez. He has orders to welcome the characters to the main casino floor.
- **F1a: Bar:** A sculpture of a red dragon head protrudes from the wall above this mirrored bar, which is tended by a taciturn but friendly equinal guardinal named [[Brayson.png|Brayson]].
- **F1b: Hotel Access:** A staircase near the main entrance ascends to a carpeted hallway of numbered, five-star suites existing in demiplanes.
- **F1c: Kitchen:** Five steam mephit chefs prepare meals for guests in this hectic kitchen.
- **F1d: Stage:** Opening acts take place on a small, curtained stage.
- **F1e: Wheel:** This room houses the original, decommissioned fortune’s wheel.

### F2: Casino Cages
Here gamblers can cash out their winnings or purchase razorleaves (the casino's currency) for 10 gp a piece.
- **Welcome Gifts:** When the characters first visit, a teller gives them each a black satin bag containing 10 razorleaves.

### F3: Illusory Fountain
*Heavy doors swing inward, revealing a jingling fountain of gold coins rising from the floor of an extravagant gambling hall. The glittering spout originates from the open palm of a statue depicting a confident arcanaloth cast in solid gold.*
The coins are an illusion. The statue depicts Shemeshka and is a scrying device for the security room (F10).

### F4: Slot Machines
A maze of gambling machines, including four stationary duodrones. A friendly night hag, [[nighthag_slot_machine.webp|Putrice]], can explain the rules. A game costs 1 razorleaf. (See original `Fortune's Wheel.md` for full prize table).

### F5: Table Games
Velvet-lined tables host various games with a 1 razorleaf buy-in.
- **Dead Hand’s Dice:** A dice game run by a vampire croupier. Highest total wins, but rolling a 1 is an automatic loss.
- **Olidammara’s Bounty:** A betting game where a spectator rolls itself on a 20-sided layout to determine the winning number.

### F6: Big Ticket Prize
This area displays a gilded **apparatus of Kwalish**, which can be won at the main wheel.

### F7: Fortune's Wheel
The casino's main attraction. A spin costs 5 razorleaves (once per 24 hours). Roll on the prize table to determine the outcome. (See original `Fortune's Wheel.md` for full prize table).

### F8: Ice Lounge
A bar chipped from a magic glacier, tended by a yeti named Phiwi. A young white dragon, Winter's Bite, is here sulking after gambling away his hoard.

### F9: Stage
A lofty stage featuring various acts, including an illusionist, a renowned singer, and a ghostly troubadour.

### F10: Security Room
Three [[nothic.webp|nothics]] monitor the casino through invisible sensors, including the statue in F3.

### F11: Private Rooms
Lavish rooms for private meetings or exclusive games.

### F12: Portal to the Platinum Rooms
An alcove with a portal that opens only for creatures carrying a rare **platinum razorleaf chip**.

---

## Part 3: The Main Event

### Here Comes the Queen
Once the PCs have settled in, Shemeshka makes her grand entrance.
*The grand chandelier’s lights dim briefly, then flare brighter as Shemeshka descends the central staircase... The chatter in Fortune’s Wheel hushes to a reverent murmur as all eyes fix upon her.*
She gives a welcoming speech, reminding everyone that every favor has its cost.

Later, a contingent of Harmonium officers bursts in to arrest the party. Shemeshka intervenes, trading a secret to the Harmonium in exchange for them leaving her guests alone.

### Casino in Chaos
The PCs are expected. Shemeshka has orchestrated this meeting. She approaches them:
>*"My dear, dear lost things. How many times have we done this now? No? You don’t remember? Ah… how tragic. Let’s fix that, shall we?”*
She claims she knows them, that they are loops in a broken story. But just as she begins to reveal what she knows, chaos erupts.

**Trigger:** The moment at least **half the party** steps within 15 ft of any duodrone slot machine.
*Static ripples off the party like heat-haze. The four duodrone croupiers stiffen, optic lenses spinning. The illusion-coins in the golden fountain freeze in midair, then duplicate, then fork outward as if reality can’t decide where to place them.*

| Rd | Event (Initiative 20) | Mechanical Effects & DM Notes |
|---|---|---|
| **1** | **Jackpot Cascade** | Every slot machine flashes “777,” ejecting scalding-hot copper coins. Area F4 becomes difficult terrain. Creatures starting their turn there take 1 fire damage. |
| **2** | **Feedback Loop** | The four duodrones fire grappling arms to "tag" the PCs. Each targets a random PC (+4 to hit, 10-ft pull, DC 14 Str save or restrained). |
| **3** | **Shemeshka Enters** (Init 15) | Shemeshka appears and casts **mass suggestion** (DC 18 Wis) to calm the patrons. |
| | **R04M’s Dash** (Init 10) | A tiny brass cube, [[r04m_delivers_message.webp|R04M]], ricochets toward the PCs, shoves a parchment into a character's hand, blurts: **"Walking Castle—remember!"** and misty steps away. |
| **4** | **Glitch Surge** | A planar harmonic dispels all illusions in 60 ft. DC 15 Con save or be deafened for 1 minute and pushed 10 ft. |
| **5** | **System Crash Warning** | A vertical warp to Mechanus splits the air above the fountain. **“If you remain inside when the timer reaches zero (2 more rounds), the room will plane-shift in fragments.”** |
| **6** | **Final Pulse / Forced Exit** | A thundering bong. PCs still inside must succeed on a DC 17 Dex save or take 4d6 force damage and be ejected from the casino. |

---

## Part 4: The Escape

### Using the Parchment
As soon as a character unfolds or reads the parchment, the coordinates activate.
*The parchment’s ink shimmers... Above the chaos, a vertical wound splits the air—a gaping portal to Mechanus yawns open... In the eye of this storm stands Shemeshka... Her two eyes, molten gold and unblinking, pin you in place... As the portal’s gears begin to turn... the parchment in your hand pulses with desperate urgency... The world lurches... and then—green fields, endless and wild, beneath a sky that spirals with impossible colors. You land, breathless, in the Outlands. The coordinates from the parchment blaze in your mind, pointing your gaze toward a distant, impossible silhouette: the Walking Castle.*

R04M's message on the parchment reads:
_"Friends, loop detected. We meet again. I am. Happy? Locate: Walking Castle. Coordinates: [45.12, -30.56], [50.67, -25.43], [55.78, -20.89]. Objective: Restore harmony. Remember: R04M is a friend!"_

### Leaving the Casino
If the PCs choose to leave without using the parchment, they find Sigil on high alert. They are now fugitives with a mysterious parchment, and they must find their own way to the Outlands.
