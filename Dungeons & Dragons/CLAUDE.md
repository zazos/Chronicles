# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **Dungeons & Dragons campaign repository** for the "Fortune's Wheel" campaign set in the Planescape setting. It is an Obsidian vault containing campaign notes, worldbuilding materials, character backstories, session recaps, and D&D content organized in Markdown files.

## Repository Structure

### Core Architecture

The repository follows a hierarchical structure organized around campaign content:

- **`00_Campaign_Hub.md`** - Main campaign overview and navigation hub
- **`Fortune's Wheel/`** - Main campaign directory containing all content
- **`GEMINI.md`** - AI assistant configuration for campaign management (provides context for AI behavior expectations)

### Content Organization

#### Campaign Structure
- **`Act XX/`** directories contain story arcs (Act 00, 01, 02, 0.5)
- **`Session Recaps/`** - Historical session summaries
- **`Session Prep/`** - Upcoming session preparation materials
- **`Lore & Worldbuilding/`** - Core campaign content organized by type

#### Worldbuilding Hierarchy
```
Lore & Worldbuilding/
├── Characters' backstories/     # PC backstories by character name
├── Faction - Philosophies/      # Planescape factions, cotteries, homebrew organizations
├── Homebrew Items/              # Custom magic items and equipment
├── Locations/                   # Campaign locations by plane/region
├── Monsters and Enemies/        # Stat blocks and enemy descriptions
├── NPCs/                        # Non-player characters with index
└── Sigil/                       # City of Doors locations by ward
```

#### Asset Management
- **`Images dump/`** - Visual assets (character portraits, maps, locations)
- **`Audio Notes/`** - Campaign audio files and sound effects
- **`Templates/`** - Standardized formats for D&D content creation

## Content Standards

### File Naming Conventions
- Use descriptive names with proper capitalization
- Character files organized by character name in subdirectories
- Location files organized geographically (plane > region > specific location)
- Session files follow "Session XX - Title.md" format

### Content Templates
The repository includes standardized templates for:
- **D&D 5e Stat Blocks** (`Templates/D&D 5e Statblock Template.md`)
- **Magic Items** (`Templates/Magic Item Template.md`)
- **Maps** (`Templates/Map Template.md`)

### Cross-Referencing
- Extensive use of Obsidian-style `[[Internal Links]]` for content connections
- Campaign Hub serves as central navigation with organized link tables
- NPCs have a master index file (`NPCs/00_NPCs_Index.md`)

## Campaign Context

### Setting & Theme
- **Planescape D&D Campaign** involving reality corruption and temporal distortions
- Characters experienced a "reality reboot" due to a failed modron upload to Mechanus, awakening in Sigil's Mortuary with fragmented memories at level 3
- Core narrative involves rescuing imprisoned modrons, collecting memory fragments via Mimir, and restoring canonical timeline
- Central antagonist Shemeshka orchestrated the original corruption and continues to interfere with restoration efforts
- Meta-narrative theme: "The Glitch" represents corrupted story data; "The Upload" symbolizes validating experiences as canonical
- For complete backstory, reference `Campaign Overview/M3t4 N4rr4t1v3 Adv4ntur3.md`

### Current Campaign Status
- **Always check `00_Campaign_Hub.md`** for the most current party location, active threats, and immediate goals
- The Campaign Hub is the authoritative source for current session status and ongoing plot threads

## Working with This Repository

### Content Creation Guidelines
- Follow existing organizational structure when adding new content
- Use established templates for stat blocks, magic items, and structured content
- Reference existing NPCs, locations, and factions to maintain continuity
- Add new NPCs to the master index in `NPCs/00_NPCs_Index.md`

### Navigation Best Practices
- Start with `00_Campaign_Hub.md` for campaign overview
- Use Act Summary files to understand story progression
- Reference character backstory files when developing character-specific content
- Consult faction files when involving Planescape organizations

### Consistency Maintenance
- Check existing faction descriptions before creating new political entities
- Reference established locations when designing new areas
- Maintain character voice and backstory consistency across sessions
- Follow Planescape setting conventions for planar locations and entities

## AI Assistant Context

The repository includes `GEMINI.md` which provides specific instructions for AI assistants working with this campaign. It emphasizes:
- Organizational assistance for scattered campaign notes
- Worldbuilding consistency with Planescape lore
- Plot development connected to character backstories
- Proactive identification of narrative connections and potential inconsistencies