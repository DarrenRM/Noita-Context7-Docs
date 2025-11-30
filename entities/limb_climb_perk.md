---
title: Limb Climb Perk
category: entities
---

# Limb Climb Perk

This entity defines the "Limb Climb" perk in Noita. It grants the player the ability to climb on surfaces.

## Key Components

### LuaComponent
This component is responsible for the perk's functionality, linking it to a Lua script.

*   **script\_source\_file**: `data/scripts/perks/attack_foot_climb.lua` - Specifies the Lua script that handles the perk's logic.
*   **execute\_every\_n\_frame**: `1` - Indicates that the script should execute every frame, allowing for real-time interaction.

### InheritTransformComponent
This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.