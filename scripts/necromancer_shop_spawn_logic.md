---
title: Necromancer Shop Spawn Logic
category: scripts
---

# Necromancer Shop Spawn Logic

This script controls the spawning of either a standard Necromancer Shop or a "super" Necromancer if the player has died a certain number of times.

## Core Logic

The script checks a global variable `STEVARI_DEATHS` to determine which Necromancer variant to spawn.

### Conditional Spawning

*   **Condition:** `tonumber(GlobalsGetValue("STEVARI_DEATHS", 0)) < 3`
    *   If the player has died less than 3 times, a standard `necromancer_shop.xml` is spawned.
*   **Else:**
    *   If the player has died 3 or more times, a `necromancer_super.xml` is spawned.

### Entity Loading

The script uses `EntityLoad` to instantiate the chosen Necromancer entity at the current position of the script's entity.

### Self-Destruction

After spawning the Necromancer, the script's own entity is removed using `EntityKill(entity_id)`.

## Key Attributes/Elements

*   **`GlobalsGetValue("STEVARI_DEATHS", 0)`:** Retrieves the global variable tracking player deaths, defaulting to 0 if not set.
*   **`EntityLoad("path/to/entity.xml", x, y)`:** Loads a specified entity at given coordinates.
*   **`EntityKill(entity_id)`:** Removes the entity that the script is attached to.
*   **`EntityGetTransform(entity_id)`:** Gets the position (x, y) of the entity.

## Example Usage (Conceptual)

This script is typically attached to a trigger or a specific entity that, when activated, initiates the Necromancer spawn sequence based on the player's death count.

```lua
-- Example of how the script might be triggered (not part of the script itself)
-- When this script's entity is activated:
local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform(entity_id)

if tonumber(GlobalsGetValue("STEVARI_DEATHS", 0)) < 3 then
	EntityLoad("data/entities/animals/necromancer_shop.xml", pos_x, pos_y)
else
	EntityLoad("data/entities/animals/necromancer_super.xml", pos_x, pos_y)
end

EntityKill(entity_id)
```