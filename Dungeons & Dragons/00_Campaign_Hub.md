---
banner: "![[Fortune's Wheel/Images dump/outlands_wide.jpg]]"
banner_y: 0.5
---

# Fortune's Wheel: Campaign Hub

> A campaign of cosmic conspiracy, forgotten pasts, and desperate survival across the Outer Planes. The characters, mysteriously returned from the dead, must navigate the treacherous streets of Sigil and the strange landscapes of the Outlands to uncover the truth of their second chance at life before their fate is sealed for them.

---

## Current Status
*   **Party Location:** A walking castle on a cliffside in the Outlands, near the gate-town of Torch.
*   **Immediate Goal:** Decide what to do with the rescued Githzerai, Laxuelu, and the knowledge he protects. Figure out how to use the powerful [[Emberheart Core|Emberheart Core]].
*   **Active Threats:** Bhaal's growing influence on Zill; Shemeshka the Marauder's newfound interest in the party; potential pursuit from the Harmonium or agents of the Reverie.

---
> [!multi-column]
> > [!tip] Recent
> > ```dataview
> > LIST
> > FROM ""
> > SORT file.mtime DESC
> > LIMIT 5
> > ```
> 
> > [!link] Recaps 
> > 
> > ```dataview
> > LIST
> > FROM "Dungeons & Dragons/Fortune's Wheel/Session Recaps"
> > SORT file.mtime DESC
> > LIMIT 5
> > ```


```dataviewjs
// --- CONFIGURATION ---
const icons = {
  age: '⏳',
  notes: '📝',
  recent: '🔥'
};
// --- END CONFIGURATION ---

const allFiles = dv.pages('');

// Check if the vault has any files at all
if (allFiles.length === 0) {
  dv.paragraph("Your vault is just getting started! Create a note to see your stats.");
} else {
  // --- All calculations now happen inside the 'else' block ---

  const files = dv.pages('"/"'); // Target all files for stats

  // 1. Vault Age
  const firstFile = files.sort(p => p.file.cday, 'asc')[0];
  const vaultStartDate = firstFile.file.cday;
  const vaultAgeDays = Math.floor(dv.date('now').diff(vaultStartDate, 'days').toObject().days);

  // 2. Total Notes
  const totalFiles = files.length; 
  
  // 3. Files Created This Week
  const filesThisWeek = files.where(p => p.file.cday >= dv.date('now').startOf('week')).length;

  // --- DISPLAY ---
  dv.table([], [[
    `${icons.age} **${vaultAgeDays}** days old`,
    `${icons.notes} **${totalFiles}** notes`,
    `${icons.recent} **${filesThisWeek}** new this week`
  ]]);
}
```


## Key Links & Resources

| Plot Arcs                                           | World & Lore                                                                              | Game Management                                       |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| [[Act 00 - Summary\|Act 00 - Awakening and Escape]] | [[Fortune's Wheel/Lore & Worldbuilding/Characters' backstories/\|PCs & Backstories]]      | [[Fortune's Wheel/Session Prep/\|► Session Prep]]     |
| [[Act 0.5 - Summary\|Act 0.5 - World's in Chaos]]   | [[Fortune's Wheel/Lore & Worldbuilding/NPCs/\|NPCs]]                                      | [[Fortune's Wheel/Session Recaps/\|◄ Session Recaps]] |
| [[Act 01 - Summary\|Act 01 - The Eternal Boundary]] | [[Fortune's Wheel/Lore & Worldbuilding/Locations/\|Locations]]                            | [[Fortune's Wheel/Templates/]]                        |
| [[Act 02 - Summary\|Act 02 - Fortune's Wheel]]      | [[Fortune's Wheel/Lore & Worldbuilding/Faction - Philosophies/\|Factions & Philosophies]] |                                                       |
|                                                     | [[Fortune's Wheel/Lore & Worldbuilding/Homebrew Items/\|Magic Items]]                     |                                                       |

---

## Player Characters

*   **Zill:** Grappling with the dark influence of Bhaal after a near-death experience.
*   **Nibi:** Entrusted with a psychic plea to "save the knowledge" by the Githzerai, Laxuelu.
*   **Rubicon:** Continues to act as a decisive and sometimes ruthless protector of the group.
*   **Orianna:** Juggling her warlock pact with a quest to infiltrate the dangerous Original Sin Cartel.
*   **LO:** Now in possession of a mysterious portal key delivered by the modron, R04M.
*   **Darius:** Currently maintaining his disguise as the Dustman agent, Toranna, back in the Mortuary.

---

## Major Story Threads

- [x] **The Truth of the Reverie:** Who is the leader of the Reverie and what is their ultimate goal for the "returned" souls?
	- [ ] A large portion of the organization has been deceased–Veylith lives.
- [ ] **Bhaal's Bargain:** What does the Lord of Murder want from Zill, and can his influence be severed?
	- [ ] **Shar's Dark Promises:** The Lady of Loss appeared in Zill's dreams, offering him the embrace of the endless night. 
- [ ] **Shemeshka's Game:** Why is the Arcanaloth spymaster of Fortune's Wheel so interested in the party? What does she know?
- [ ] **The Concordant Express:** Plan the heist to free the Hands of Havoc member for Adia Panama.
- [ ] **The Sylvanian Coup:** Will the party help Clarion and the guardinals deal with the corrupted Wolf Lord?
- [ ] **The Emberheart Core:** Find someone (like Shafi Bin Ahmad Zin) to craft the Infernal Iron device to unlock the core's power.
- [ ] **Orianna's Mission:** Infiltrate the Bucket of Blood tavern in Pazunia for her patron.
