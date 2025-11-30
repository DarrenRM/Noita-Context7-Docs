---
title: Kantele Magic Script
category: scripts
---

# Kantele Magic Script

This script defines the functionality for the Kantele item in Noita, allowing players to cast spells by playing specific musical "songs" through a sequence of notes.

## Core Mechanics

The Kantele script operates by detecting player input (represented by "notes") and comparing them against predefined song patterns. When a complete song is played, it triggers specific magical effects.

### Song Definitions

The script defines several songs, each associated with a unique sequence of notes. These notes are represented by single letters.

```lua
local kantele_songs = {
	portal = { "a", "dis", "e", "g" },
	bomb = { "g", "d", "e", "d" },
	worm = { "d", "e", "a", "e", "dis" },
	alchemy = { "f", "g", "f", "a2", "c" },
}
```

### Player Interaction

The script checks for nearby players and their current Kantele song state. It tracks the player's progress through a song and the currently selected song.

### Note Matching

When a player inputs a note, the script compares it to the expected note in the current song sequence.

- If the note matches and is not the last note of the song, the player progresses to the next note in the sequence.
- If the note matches and is the last note of the song, the spell is cast.
- If the note does not match, the song progress is reset.

### Starting New Songs

If no song is currently in progress, the script listens for the first note of any defined song. If the input note matches the first note of a song, that song becomes the active one.

## Spell Effects

Successfully completing a song triggers distinct magical effects:

### Portal Song

- **Effect:** Spawns a `mystery_teleport_back.xml` entity at the player's location.
- **Conditions:** Can only be cast once per player, tracked by the `kantele_secret_00` tag.
- **Feedback:** Displays important messages to the player.

### Bomb Song

- **Effect:** Spawns a `bomb_holy.xml` projectile at the player's location.
- **Conditions:** Can only be cast once per player, tracked by the `kantele_secret_01` tag.
- **Feedback:** Displays important messages to the player.

### Worm Song

- **Effect:** Spawns a `worm_big.xml` entity near the player.
- **Conditions:** Can only be cast once per player, tracked by the `kantele_secret_02` tag.
- **Feedback:** Displays important messages to the player.

### Alchemy Song

- **Effect:** Interacts with nearby "alchemist_key" entities.
    - Increments a "status" variable on the key.
    - Triggers visual effects and updates the key's description based on its status (1 or 2).
    - Prevents re-casting on the same key once its status reaches 2.
- **Conditions:** Requires an "alchemist_key" entity within a 48-unit radius.
- **Feedback:** Displays specific messages for key interactions.

## Key Variables and Components

The script relies on `VariableStorageComponent` on both the Kantele entity and the player entity to manage song state and progress.

- **Kantele Entity:** Stores the current note being played (`kantele_note`).
- **Player Entity:** Stores the currently active song (`kantele_song`) and the current position within that song (`kantele_song_pos`).

## Important Notes

- The script uses `GameAddFlagRun` and entity tags to prevent certain spells from being cast multiple times.
- String lengths and comparisons are crucial for note and song matching.
- The `alt_notes` table (not fully defined in the provided snippet) is used to handle alternative note mappings for the "alchemy" song.