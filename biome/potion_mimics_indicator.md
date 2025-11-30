---
title: Potion Mimics Indicator
category: biome
---

# Potion Mimics Indicator

This script defines a static tile used to indicate the presence of potion mimics within a biome.

## Core Functionality

The primary purpose of this entity is to be converted into a specific material and then immediately killed, effectively acting as a placeholder or trigger within the biome generation.

### Key Attributes

*   **`EntityConvertToMaterial`**: This function is called to transform the entity into the `glowstone_altar_hdr` material. This material likely has visual properties that serve as the indicator.
*   **`EntityKill`**: Immediately after conversion, the entity is killed. This ensures it doesn't persist as a physical object but rather its effect (the material conversion) is the intended outcome.

### Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Converts the entity to the 'glowstone_altar_hdr' material.
-- The 'false' and 'true' arguments likely control specific conversion behaviors (e.g., preserving physics, affecting lighting).
EntityConvertToMaterial( entity_id, "glowstone_altar_hdr", false, true )

-- Immediately removes the entity from the game world.
EntityKill( entity_id )
```