---
title: Orbit Laser Projectile
category: entities
---

# Orbit Laser Projectile

This entity defines a projectile that emits a laser beam. It's designed to be part of an orbiting system, likely for a spell or effect.

## Key Attributes

### Entity
- **name**: `$projectile_default` (This is a placeholder, likely overridden by specific spell configurations)
- **tags**: `orbit_projectile`, `orbit_laser` (Identifies its role in orbiting systems and as a laser)

### Base Projectile
- **file**: `data/entities/base_projectile.xml` (Inherits fundamental projectile properties)

#### VelocityComponent
- **gravity_y**: `0` (No vertical gravity applied)
- **air_friction**: `0` (No air resistance)
- **mass**: `0.05` (Lightweight projectile)

### ProjectileComponent
- **lob_min/max**: `0.8` to `1.0` (Controls the arc of the projectile)
- **speed_min/max**: `42` (Constant speed)
- **die_on_low_velocity**: `0` (Does not die if speed drops)
- **on_death_explode**: `0` (Does not explode on death)
- **on_death_gfx_leave_sprite**: `0` (Does not leave a sprite on death)
- **on_lifetime_out_explode**: `0` (Does not explode when lifetime ends)
- **explosion_dont_damage_shooter**: `1` (Laser explosion does not harm the caster)
- **damage**: `0.8` (Base damage of the projectile itself, not the laser)
- **on_collision_die**: `0` (Does not die on collision)
- **lifetime**: `7200` (Long lifetime, suggesting it's meant to persist)
- **knockback_force**: `1.3` (Applies a small knockback)

### SpriteComponent
- **_enabled**: `0` (The sprite is disabled by default, likely meaning the laser is the primary visual)
- **image_file**: `data/projectiles_gfx/orb_blue.xml` (Reference to the projectile's visual asset)
- **emissive**: `1` (The sprite emits light)
- **additive**: `1` (The sprite uses additive blending for a glowing effect)

### ParticleEmitterComponent
- **emitted_material_name**: `spark_blue` (Emits blue sparks)
- **gravity.y**: `0.10` (Slight downward gravity for particles)
- **count_min/max**: `1` to `5` (Number of particles emitted)
- **lifetime_min/max**: `0.6` to `0.8` (Duration of particles)
- **create_real_particles**: `0` (Emits cosmetic particles only)
- **emit_cosmetic_particles**: `1` (Ensures cosmetic particles are emitted)
- **is_emitting**: `1` (Particle emission is active)

### LaserEmitterComponent
- **is_emitting**: `0` (Laser emission is controlled by a Lua script)
- **laser_angle_add_rad**: `1.570796` (Adds 90 degrees to the laser's angle)

#### Laser
- **damage_to_entities**: `0.045` (Low damage per tick to entities)
- **max_cell_durability_to_destroy**: `11` (Can destroy a small amount of cell durability)
- **damage_to_cells**: `10000` (High damage to terrain cells)
- **root_entity_is_responsible_for_damage**: `1` (The originating entity handles damage calculations)
- **max_length**: `64` (Maximum length of the laser beam)
- **beam_radius**: `2.0` (Thickness of the laser beam)
- **hit_particle_chance**: `20` (Chance to spawn particles on hit)
- **beam_particle_chance**: `90` (High chance to spawn particles along the beam)
- **beam_particle_type**: `plasma_fading` (Type of particles emitted along the beam)

### LuaComponent
- **script_source_file**: `data/scripts/projectiles/laser_emitter_start.lua` (Script responsible for initiating laser emission)
- **execute_every_n_frame**: `2` (Script runs every 2 frames)
- **remove_after_executed**: `1` (Script is removed after its first execution)

### VariableStorageComponent
- **name**: `projectile_file`
- **value_string**: `data/entities/projectiles/deck/orb_laseremitter_weak.xml` (Specifies the configuration file for this projectile when used in a deck)