---
title: Projectile Eater Sector (No Particles)
category: entities
---

# Projectile Eater Sector (No Particles)

This entity defines a projectile-eating sector that does not emit particles. It's a component used to create areas that consume incoming projectiles.

## Key Components

### InheritTransformComponent

This component is used to inherit the transform properties of another entity.

*   **`only_position="1"`**: Indicates that only the position should be inherited, not rotation or scale.

### Transform

Defines the relative position of this entity.

*   **`position.x="0"`**: The x-coordinate of the transform.
*   **`position.y="-8"`**: The y-coordinate of the transform.

### LuaComponent

This component attaches a Lua script to the entity, enabling custom behavior.

*   **`script_source_file="data/scripts/perks/projectile_eater_sector.lua"`**: Specifies the Lua script file responsible for the entity's logic. This script likely handles the projectile-eating functionality.
*   **`execute_every_n_frame="1"`**: The script will execute every frame, ensuring continuous operation.