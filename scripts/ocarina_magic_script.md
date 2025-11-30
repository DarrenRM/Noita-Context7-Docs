---
title: Ocarina Magic Script
category: scripts
---

# Ocarina Magic Script

This script defines the functionality of the Ocarina item in Noita, allowing players to play specific songs to trigger various magical effects.

## Core Functionality

The script detects when a player is near an Ocarina entity and reads the "ocarina_note" variable from the Ocarina. It then compares this note to the currently active song being played by the player (stored in "ocarina_song" and "ocarina_song_pos" variables on the player). If the notes match and progress the song, the song state is updated. Completing a song triggers a specific magical effect.

## Key Attributes and Elements

### `ocarina_songs` Table

This table defines the note sequences for each Ocarina song.

| Song Name | Notes | Description |
|---|---|---|
| `portal` | `{"a", "f", "d", "e", "a2"}` | Triggers a portal effect. |
| `bomb` | `{"f", "c", "d", "c"}` | Spawns a holy bomb. |
| `worm` | `{"gsharp", "f", "e", "b", "d"}` | Summons a large worm. |
| `alchemy` | `{"a2", "d", "dis", "e", "a"}` | Interacts with alchemist keys. |

### Player Interaction

- The script checks for the presence of a "player_unit" within a 24-unit radius of the Ocarina.
- It reads player-specific variables:
    - `ocarina_song`: The name of the currently active song.
    - `ocarina_song_pos`: The current position within the active song sequence.

### Ocarina Entity Variables

- The Ocarina entity itself stores the `ocarina_note` variable, which represents the note played by the player.

### Song Progression Logic

- The script increments `song_state` as correct notes are played in sequence.
- If an incorrect note is played or the sequence is broken, the song resets.
- Completing a song sets `casting_spell` to `true` and triggers the corresponding magic.

### Magical Effects

#### Portal Magic (`ocarina_songs.portal`)

- **Effect:** Spawns a `mystery_teleport_back.xml` entity at the player's location.
- **Conditions:** Requires the "ocarina_secret_00" tag to not be present on the player.
- **Feedback:** Displays "Ocarina Secret Unlocked!" and adds the "ocarina_secret_00" tag to the player.

#### Bomb Magic (`ocarina_songs.bomb`)

- **Effect:** Spawns a `bomb_holy.xml` projectile.
- **Conditions:** Requires the "ocarina_secret_01" tag to not be present on the player.
- **Feedback:** Displays "Ocarina Secret Unlocked!" and adds the "ocarina_secret_01" tag to the player.

#### Worm Magic (`ocarina_songs.worm`)

- **Effect:** Spawns a `worm_big.xml` entity.
- **Conditions:** Requires the "ocarina_secret_02" tag to not be present on the player.
- **Feedback:** Displays "Ocarina Secret Unlocked!" and adds the "ocarina_secret_02" tag to the player.

#### Alchemy Magic (`ocarina_songs.alchemy`)

- **Effect:** Interacts with entities tagged "alchemist_key".
- **Conditions:**
    - The player must be near an "alchemist_key" entity.
    - The "alchemy_ocarina" tag must not be present on the key.
- **Logic:**
    - Increments a "status" variable on the alchemist key.
    - Spawns particle effects and updates the key's description based on its status (1 or 2).
    - Adds the "alchemy_ocarina" tag to the key.
- **Feedback:** Displays specific messages for unlocking the first or second stage of the alchemist key. If no alchemist keys are found, it prints "$log_alchemist_key_invalid".

### Variable Storage Component

The script heavily relies on `VariableStorageComponent` to store and retrieve song state, notes, and other game flags.

### Entity Manipulation

- `EntityGetInRadiusWithTag`: Used to find nearby players and alchemist keys.
- `EntityGetComponent`: Retrieves component data from entities.
- `ComponentGetValue`, `ComponentGetValue2`, `ComponentGetValueInt`: Used to read values from components.
- `ComponentSetValue2`: Used to write values to components.
- `EntityLoad`: Spawns new entities.
- `EntityHasTag`: Checks for the presence of a tag on an entity.
- `EntityAddTag`: Adds a tag to an entity.
- `GamePrintImportant`, `GamePrint`: Displays messages to the player.
- `GameAddFlagRun`: Adds a global flag.
- `EntitySetComponentsWithTagEnabled`: Enables/disables components based on tags.
- `EntityLoadToEntity`: Loads an entity relative to another entity.
- `edit_component`: A utility function to modify component values.

```lua
-- Example of how the ocarina_songs table is structured
local ocarina_songs = {
	portal = { "a", "f", "d", "e", "a2" },
	bomb = { "f", "c", "d", "c" },
	worm = { "gsharp", "f", "e", "b", "d" },
	alchemy = { "a2", "d", "dis", "e", "a" },
}
```