---
title: Egg Fire Projectile
category: entities
---

# Egg Fire Projectile

This document describes the `egg_fire.xml` entity, which defines a projectile used in Noita. This projectile is a basic fire projectile with specific behaviors and effects.

## Key Attributes

### Entity
- **name**: `$projectile_default` - Indicates this entity inherits default projectile properties.

### Base Projectile (`data/entities/base_projectile.xml`)
- **VelocityComponent**:
    - **gravity_y**: `100` - Applies a downward gravitational force to the projectile.

### Projectile Component (`ProjectileComponent`)
- **_enabled**: `1` - Ensures the projectile component is active.
- **lob_min**: `0.8` - Minimum lob angle for projectile trajectory.
- **lob_max**: `1.0` - Maximum lob angle for projectile trajectory.
- **speed_min**: `160` - Minimum initial speed of the projectile.
- **speed_max**: `170` - Maximum initial speed of the projectile.
- **on_death_explode**: `0` - The projectile does not explode upon death.
- **on_death_gfx_leave_sprite**: `0` - No graphical effects are left behind when the projectile dies.
- **on_lifetime_out_explode**: `0` - The projectile does not explode when its lifetime expires.
- **explosion_dont_damage_shooter**: `0` - The projectile's explosion can damage the shooter.
- **die_on_low_velocity**: `0` - The projectile does not die when its velocity becomes low.
- **damage**: `0` - The projectile itself deals no direct damage.
- **on_collision_die**: `0` - The projectile does not die upon collision.
- **lifetime**: `19` - The projectile exists for 19 frames before expiring.
- **config_explosion**: Empty, indicating no specific explosion configuration is applied directly here.

### Variable Storage Component (`VariableStorageComponent`)
- **name**: `entity_list`
- **value_string**: `fire` - This likely tags the projectile as a "fire" type, potentially for interactions with other game systems.

### Lua Component (`LuaComponent`)
- **script_source_file**: `data/scripts/items/egg_hatch.lua` - This script is executed when the projectile is removed, suggesting it handles the "hatching" or spawning of something upon the projectile's demise.
- **execute_every_n_frame**: `-1` - The script does not execute periodically.
- **execute_on_removed**: `1` - The script executes once when the entity is removed.

### Audio Component (`AudioComponent`)
- **file**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank containing projectile sounds.
- **event_root**: `player_projectiles/throwable` - Defines the root event for player-thrown projectile sounds.