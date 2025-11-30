---
title: Sampo Normal Ending Entity
category: entities
---

# Sampo Normal Ending Entity

This entity defines the visual and functional elements for the "Sampo Normal Ending" in Noita. It primarily handles the visual effects and entity spawning associated with this specific ending sequence.

## Key Components and Functionality

### World State Modification

*   **`edit_component( GameGetWorldStateEntity(), "WorldStateComponent", ... )`**: This section modifies the `WorldStateComponent` of the global world state entity.
    *   **`vars.damage_flash_multiplier = 0.0`**: This specific modification disables or significantly reduces any damage flash effects that might otherwise occur during this ending sequence. This suggests a desire for a cleaner, less visually disruptive ending.

### Entity Spawning

*   **`EntityLoad( "data/entities/animals/boss_centipede/ending/midas_entities.xml", x, y )`**: This is the core functionality of this entity. It loads another entity file (`midas_entities.xml`) at the current position (`x`, `y`) of the Sampo Normal Ending entity.
    *   This implies that the `midas_entities.xml` file contains the actual visual assets, particle effects, or other entities that constitute the "Sampo Normal Ending" visual presentation. The Sampo Normal Ending entity itself acts as a trigger or container for these more detailed visual elements.

## Lua Scripting

```lua
dofile( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

edit_component( GameGetWorldStateEntity(), "WorldStateComponent", function(comp,vars)
		vars.damage_flash_multiplier = 0.0
end)

EntityLoad( "data/entities/animals/boss_centipede/ending/midas_entities.xml", x, y )
```