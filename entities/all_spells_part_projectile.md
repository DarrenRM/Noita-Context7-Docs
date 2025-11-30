---
title: All Spells Part Projectile
category: entities
---

# All Spells Part Projectile

This entity defines a fundamental projectile component used in Noita's spell system. It acts as a base for many other projectiles, providing core behaviors and properties.

## Key Attributes

### Entity
- **name**: `$projectile_default` - A placeholder name, indicating its foundational role.
- **tags**: `all_spells_part` - Crucial tag for identifying and utilizing this projectile as a component.

### Base Projectile (`data/entities/base_projectile.xml`)
- **VelocityComponent**:
    - **gravity_y**: `0` - No vertical gravity applied to this projectile.
    - **air_friction**: `0` - No air resistance.

### ProjectileComponent
- **_enabled**: `1` - The component is active.
- **lob_min/lob_max**: `0.8`/`1.0` - Controls the lobbing behavior, suggesting minimal to no lobbing.
- **speed_min/speed_max**: `0`/`0` - The projectile starts with zero speed.
- **die_on_low_velocity**: `0` - The projectile does not die if its velocity drops too low.
- **on_death_explode**: `0` - Does not explode upon death.
- **on_death_gfx_leave_sprite**: `0` - Does not leave a sprite graphic upon death.
- **on_lifetime_out_explode**: `0` - Does not explode when its lifetime ends.
- **explosion_dont_damage_shooter**: `1` - If an explosion were to occur, it wouldn't damage the shooter.
- **penetrate_entities**: `1` - Can pass through other entities.
- **penetrate_world**: `1` - Can pass through the game world (terrain).
- **damage**: `0.15` - Base damage value.
- **on_collision_die**: `0` - Does not die upon collision.
- **lifetime**: `250` - The projectile exists for 250 frames.

### LightComponent
- **_enabled**: `1` - The light effect is active.
- **radius**: `90` - The radius of the light emitted.
- **r, g, b**: `30, 95, 160` - Defines the color of the light (a bluish hue).

### LuaComponent
- **script_source_file**: `data/scripts/projectiles/all_spells_part.lua` - Links to the Lua script that governs the projectile's dynamic behavior.
- **execute_every_n_frame**: `1` - The Lua script runs every frame.