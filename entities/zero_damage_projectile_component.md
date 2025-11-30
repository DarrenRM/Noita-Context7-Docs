---
title: Zero Damage Projectile Component
category: entities
---

# Zero Damage Projectile Component

This entity defines a projectile that deals zero damage. It primarily utilizes a Lua component to achieve this effect.

## Key Components

### LuaComponent

This component is responsible for the core functionality of the zero-damage projectile.

*   **`script_source_file`**: `data/scripts/projectiles/zero_damage.lua`
    *   Specifies the Lua script that handles the projectile's behavior.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script should be executed every frame.
*   **`remove_after_executed`**: `1`
    *   The entity will be removed from the game after the script has been executed once.

## Usage

This entity is likely used as a base or a component for other projectiles that are intended to have no damaging effect, such as certain utility projectiles or visual effects. The associated Lua script (`zero_damage.lua`) would contain the logic to ensure no damage is applied to targets.