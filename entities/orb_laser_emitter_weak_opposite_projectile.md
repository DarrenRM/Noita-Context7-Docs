---
title: Orb Laser Emitter (Weak, Opposite) Projectile
category: data
---

# Orb Laser Emitter (Weak, Opposite) Projectile

This entity defines a weak, opposite-facing laser emitter projectile, likely used in Noita's deck-building system. It's a projectile that, upon activation, can emit a laser beam.

## Key Components and Attributes

### Entity
- **name**: `$projectile_default` (Inherits default projectile properties)
- **tags**: `projectile_player` (Indicates it's a player-controlled projectile)

### Base Projectile (`BaseComponent`)
- **file**: `data/entities/base_projectile.xml` (Inherits core projectile behavior)
- **VelocityComponent**:
    - **gravity_y**: `0` (No vertical gravity applied)
    - **air_friction**: `7` (Moderate air resistance)
    - **mass**: `0.05` (Lightweight projectile)

### Projectile Behavior (`ProjectileComponent`)
- **_enabled**: `1` (Component is active)
- **lob_min/lob_max**: `0.8` / `1.0` (Controls projectile arc, minimal lobbing)
- **speed_min/speed_max**: `40` (Fixed projectile speed)
- **die_on_low_velocity**: `0` (Projectile does not die if speed drops)
- **on_death_explode**: `0` (No explosion on death)
- **on_death_gfx_leave_sprite**: `0` (No sprite left on death)
- **on_lifetime_out_explode**: `0` (No explosion when lifetime ends)
- **explosion_dont_damage_shooter**: `1` (Explosions from this projectile won't harm the shooter)
- **damage**: `0.8` (Base damage of the projectile itself)
- **on_collision_die**: `0` (Projectile does not die on collision)
- **lifetime**: `100` (Duration in frames before despawning)
- **knockback_force**: `1.3` (Force applied to entities on hit)

### Visuals (`SpriteComponent`)
- **_enabled**: `0` (Sprite is initially disabled, likely activated by script)
- **image_file**: `data/projectiles_gfx/orb_blue.xml` (References the sprite definition)
- **emissive**: `1` (Sprite emits light)
- **additive**: `1` (Sprite uses additive blending for a glowing effect)

### Particle Effects (`ParticleEmitterComponent`)
- **emitted_material_name**: `spark_blue` (Emits blue sparks)
- **gravity.y**: `0.10` (Particles have slight downward gravity)
- **count_min/count_max**: `1` / `5` (Emits 1 to 5 particles per emission)
- **lifetime_min/lifetime_max**: `0.6` / `0.8` (Particles last for 0.6 to 0.8 seconds)
- **emit_cosmetic_particles**: `1` (Emits visual-only particles)

### Lighting (`LightComponent`)
- **_enabled**: `1` (Light is active)
- **radius**: `150` (Radius of the light emitted)
- **r, g, b**: `30, 30, 90` (Blueish light color)

### Audio (`AudioComponent`)
- **file**: `data/audio/Desktop/projectiles.bank` (Sound bank used)
- **event_root**: `projectiles/orb_b` (Specific sound event for this orb)

### Laser Emission (`LaserEmitterComponent`)
- **is_emitting**: `0` (Laser is not emitting by default, controlled by script)
- **laser_angle_add_rad**: `3.14159` (Adds 180 degrees to the laser's initial angle, making it opposite)
- **laser**:
    - **damage_to_entities**: `0.065` (Damage per tick to entities)
    - **max_cell_durability_to_destroy**: `11` (Durability of terrain cells to destroy)
    - **damage_to_cells**: `10000` (High damage to terrain)
    - **root_entity_is_responsible_for_damage**: `1` (The emitter is responsible for damage calculation)
    - **max_length**: `96` (Maximum length of the laser beam)
    - **beam_radius**: `2.0` (Thickness of the laser beam)
    - **hit_particle_chance**: `20` (Chance to spawn particles on hit)
    - **beam_particle_type**: `plasma_fading` (Type of particles emitted along the beam)

### Scripting (`LuaComponent`)
- **script_source_file**: `data/scripts/projectiles/laser_emitter_start.lua` (Lua script to control laser emission)
- **execute_every_n_frame**: `2` (Script executes every 2 frames)
- **remove_after_executed**: `1` (Script is removed after its first execution)

### Variables (`VariableStorageComponent`)
- **name**: `projectile_file`
- **value_string**: `data/entities/projectiles/deck/orb_laseremitter_weak.xml` (References the base weak laser emitter for potential shared properties or logic)