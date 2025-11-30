---
title: Projectile Slow Field Perk
category: entities
---

# Projectile Slow Field Perk

This entity defines the "Projectile Slow Field" perk in Noita. When acquired, it creates a field that slows down projectiles within its radius.

## Key Components

### InheritTransformComponent
This component is used to inherit the transform properties from its parent.

*   **use_root_parent**: Set to `1`, indicating it should inherit from the root parent.

### Transform
Defines the position of the slow field relative to its parent.

*   **position.x**: `0`
*   **position.y**: `-4`

### LuaComponent
This component executes a Lua script to manage the functionality of the slow field.

*   **script_source_file**: `data/scripts/perks/projectile_slow_field.lua` - This points to the script that handles the actual slowing of projectiles.
*   **execute_every_n_frame**: `2` - The script will be executed every 2 frames, allowing for continuous updates to the field's effect.