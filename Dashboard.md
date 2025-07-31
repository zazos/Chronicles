
![[VampireHunterD.gif|600]]


> [!bookmark]+ Links
> -	[[Thesis Collection|Thesis]]
> - [[Work | Work Related]]
> - [[Dungeons & Dragons| Dungeons and Dragons]]

> [!multi-column]
> > [!info] Recent
> > ```dataview
> > LIST
> > FROM ""
> > SORT file.mtime DESC
> > LIMIT 5
> > ```
> 
> > [!success] Notes 
> > 
> > ```dataview
> > LIST
> > FROM "Notes"
> > SORT file.mtime DESC
> > LIMIT 5
> > ```
> 

```button
name Create Note
type command  
action Daily Notes: Open today's daily note  
class grad_button btn_cyan 
```



> [!cards|3]
>  **Self** 
> ![External Image|center|440](https://raw.githubusercontent.com/D3Ext/aesthetic-wallpapers/main/images/pink-mecha.png)
>  **[[Thesis Collection]] — #thesis**   <br>  **[[Notes]] — #notes** 
>  
>  **Work**
> ![External Image|center|440](https://raw.githubusercontent.com/D3Ext/aesthetic-wallpapers/main/images/wallhaven-28rjj6.png)
>**[[Proposals]] — #proposal **  <br> **[[LLMs]] — #llm**  
>
>  **Others**
> ![[VampireHunterDdesert.webp||center|440]]
>**[[Dungeons & Dragons]] — #dnd**  <br>
>


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
