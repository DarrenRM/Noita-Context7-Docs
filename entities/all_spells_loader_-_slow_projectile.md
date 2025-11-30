---
title: All Spells Loader - Slow Projectile
category: entities
---

# All Spells Loader - Slow Projectile

This entity defines a projectile used by the "All Spells Loader" functionality in Noita, specifically designed for a slower projectile behavior. It's a base projectile with modifications to its movement, collision, and scripting.

## Key Attributes

### Entity
- **name**: `$projectile_default` - Indicates this is a default projectile type.
- **tags**: `all_spells_loader` - Identifies its association with the spell loader system.

### Base Projectile
- **file**: `data/entities/base_projectile.xml` - Inherits core projectile properties.
  - **VelocityComponent**:
    - **gravity_y**: `0` - No vertical gravity applied.
    - **air_friction**: `0` - No air resistance.

### Projectile Component
- **_enabled**: `1` - The component is active.
- **lob_min/lob_max**: `0.8`/`1.0` - Controls the minimum and maximum lob angle, suggesting a relatively straight trajectory.
- **speed_min/speed_max**: `0`/`0` - The projectile starts with zero initial speed.
- **die_on_low_velocity**: `0` - The projectile does not die if its velocity becomes low.
- **on_death_explode**: `0` - No explosion upon death.
- **on_death_gfx_leave_sprite**: `0` - No sprite left behind on death.
- **on_lifetime_out_explode**: `0` - No explosion when lifetime expires.
- **explosion_dont_damage_shooter**: `1` - If an explosion were to occur, it wouldn't damage the shooter.
- **penetrate_entities**: `1` - Can pass through entities.
- **penetrate_world**: `1` - Can pass through the world geometry.
- **damage**: `0.15` - Deals a small amount of damage.
- **on_collision_die**: `0` - Does not die upon collision.
- **lifetime**: `36005` - A very long lifetime, indicating it persists for a significant duration.

### Lua Component
- **script_source_file**: `data/scripts/projectiles/all_spells_launch_slow.lua` - Links to a custom Lua script that dictates its behavior.
- **execute_every_n_frame**: `9000` - The associated Lua script executes every 9000 frames, contributing to its slow, deliberate action.

### Homing Component
- **homing_targeting_coeff**: `130.0` - A high coefficient for homing, suggesting it will actively seek targets.
- **homing_velocity_multiplier**: `0.86` - The homing velocity is slightly reduced, contributing to the "slow" aspect.