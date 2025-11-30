---
title: Big Magic Shield Start Projectile
category: scripts
---

# Big Magic Shield Start Projectile

This script defines the behavior for the initial projectile that spawns the "Big Magic Shield" effect. It creates multiple smaller shield parts that orbit the player or a target.

## Key Functionality

*   **Spawns Shield Parts:** Creates a ring of `big_magic_shield_part.xml` projectiles around the caster.
*   **Orbital Behavior:** Each spawned part is given an initial angle and rotation to create an orbiting effect.
*   **Owner Tracking:** The shield parts are tagged with the `shooter_id` to identify their owner.
*   **Self-Destruction:** The initial projectile entity is immediately killed after spawning the parts.

## Core Attributes & Logic

### Projectile Spawning

*   `how_many`: Determines the number of shield parts to spawn (default: 8).
*   `angle_inc`: Calculates the angular separation between spawned parts.
*   `theta`: The initial angle for the first spawned part, influenced by game frame for a dynamic start.
*   `length`: The radial distance from the center where shield parts are spawned.

### Rotation and Offset

*   `rotation`: A random rotation is applied to the spawned shield parts, with a minimum absolute value to ensure noticeable rotation. A rare chance for a larger rotation (20) exists.

### Shooter Identification

*   The script attempts to identify the entity that shot this projectile (`shooter_id`).
*   If the shooter is not found, it searches for the closest "hittable" entity.

### Shield Part Creation

*   A loop iterates `how_many` times to spawn individual shield parts.
*   `shoot_projectile_from_projectile`: This function is used to spawn a new projectile (`big_magic_shield_part.xml`) relative to the current projectile's position.

### Variable Storage for Shield Parts

Each spawned shield part receives the following variables via `VariableStorageComponent`:

*   `name = "angle"`: Stores the initial angle (`theta`) of the shield part.
*   `name = "rot"`: Stores the calculated random rotation (`rotation`) for the shield part.
*   `name = "owner"`: Stores the `shooter_id` to identify the owner of the shield.

### Entity Management

*   `EntityKill( entity_id )`: The initial projectile entity is immediately removed from the game after its task is complete.

```lua
-- Example of how a shield part might use the stored variables (in its own script)
-- local angle = ComponentGetValue2( self.entity, "VariableStorageComponent", "angle" )
-- local rot = ComponentGetValue2( self.entity, "VariableStorageComponent", "rot" )
-- local owner = ComponentGetValue2( self.entity, "VariableStorageComponent", "owner" )
```