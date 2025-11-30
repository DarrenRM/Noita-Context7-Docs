---
title: Beamstone Kick Item Script
category: scripts
---

---

# Beamstone Kick Item Script

This script defines the behavior for the "Beamstone Kick" item in Noita. When activated, it triggers a powerful beam attack and consumes the item.

## Core Functionality

The `kick()` function is the primary logic for this item.

### Key Actions:

*   **Get Entity ID and Position:** Retrieves the unique identifier and current world coordinates of the entity holding the item.
*   **Adjust Position:** Slightly shifts the Y-coordinate upwards to ensure the spawned effects appear above the player.
*   **Inventory Check:** Prevents the script from executing if the item is in the player's inventory or hand (i.e., not actively equipped and in the world).
*   **Play Sound:** Triggers a specific sound effect (`misc/beam_from_sky_kick`) for auditory feedback.
*   **Spawn Particles:** Loads and places particle effects (`data/entities/particles/beamstone_kick.xml`) at the item's location.
*   **Spawn Beam Entity:** Loads and places the main beam entity (`data/entities/misc/beam_from_sky.xml`) responsible for the attack.
*   **Destroy Item:** Removes the "Beamstone Kick" item entity from the game world after its effect is triggered.

## Script Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

function kick()
	-- ... (implementation details as described above)
end
```

## Dependencies

*   `data/scripts/lib/utilities.lua`: Assumed to contain helper functions, though not explicitly used in the provided snippet.
*   `data/audio/Desktop/misc.bank`: Contains the sound effect.
*   `data/entities/particles/beamstone_kick.xml`: Defines the visual particle effects.
*   `data/entities/misc/beam_from_sky.xml`: Defines the main beam entity and its behavior.