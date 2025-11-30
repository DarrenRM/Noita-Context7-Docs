---
title: Projectile Repulsion Sector (No Particles)
category: entities/misc/perks
---

# Projectile Repulsion Sector (No Particles)

This entity defines a perk that creates a repulsion field around the player, pushing away projectiles. This specific variant is designed to do so without generating visual particle effects.

## Key Components

### InheritTransformComponent
This component is used to inherit the transform properties of another entity.

*   **`only_position="1"`**: Indicates that only the position (x and y) should be inherited, not rotation or scale.

#### Transform
Defines the relative position of this component.

*   **`position.x="0"`**: The x-coordinate offset.
*   **`position.y="-8"`**: The y-coordinate offset.

### LuaComponent
This component executes a Lua script to implement the perk's functionality.

*   **`script_source_file="data/scripts/perks/projectile_repulsion_sector.lua"`**: Specifies the path to the Lua script that handles the repulsion logic.
*   **`execute_every_n_frame="2"`**: The script will be executed every 2 frames, ensuring a balance between responsiveness and performance.