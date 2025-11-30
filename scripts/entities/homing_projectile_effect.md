---
title: Homing Projectile Effect
category: scripts/entities
---

---

# Homing Projectile Effect

This entity defines a script that can be applied to projectiles to give them homing capabilities.

## Key Components

### LuaComponent

This component is responsible for executing the Lua script that adds homing behavior to a projectile.

*   **`script_shot`**: Specifies the path to the Lua script that will be executed. In this case, it's `data/scripts/streaming_integration/scripts/add_homing_on_shot.lua`. This script contains the logic for making the projectile home in on targets.
*   **`execute_every_n_frame`**: Set to `-1`, indicating that the script is executed once when the projectile is spawned or when the component is initialized, rather than on a recurring frame basis.

## Usage

To make a projectile homing, you would typically add this `LuaComponent` to the projectile's entity definition in its XML file. The associated Lua script (`add_homing_on_shot.lua`) would then handle the targeting and steering logic.