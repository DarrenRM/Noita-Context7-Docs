---
title: Orb Laser Emitter Four Projectile
category: entities
---

# Orb Laser Emitter Four Projectile

This document describes the `orb_laseremitter_four.xml` entity, which defines a player projectile that emits four laser beams.

## Core Components

### Base Projectile (`BaseComponent`)

This component inherits from the default projectile behavior.

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `7` - Moderate air resistance.
*   **`mass`**: `0.05` - Low mass, contributing to its speed.

### Projectile Behavior (`ProjectileComponent`)

Defines the projectile's movement and interaction properties.

*   **`lob_min`**: `0.8`, **`lob_max`**: `1.0` - Controls the arc of the projectile.
*   **`speed_min`**: `40`, **`speed_max`**: `40` - The projectile travels at a constant speed of 40.
*   **`die_on_low_velocity`**: `0` - The projectile does not disappear if its velocity drops.
*   **`on_death_explode`**: `0` - No explosion upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite left behind on death.
*   **`on_lifetime_out_explode`**: `0` - No explosion when lifetime ends.
*   **`explosion_dont_damage_shooter`**: `1` - The projectile does not damage its owner if it explodes (though it doesn't explode by default).
*   **`damage`**: `0.8` - Base damage dealt by the projectile itself.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.
*   **`lifetime`**: `100` - The projectile exists for 100 frames.
*   **`knockback_force`**: `1.3` - The force applied to entities upon collision.

### Visuals (`SpriteComponent`)

Defines the projectile's appearance.

*   **`_enabled`**: `0` - This sprite component is disabled by default.
*   **`image_file`**: `data/projectiles_gfx/orb_blue.xml` - Uses a blue orb graphic.
*   **`emissive`**: `1` - The sprite emits light.
*   **`additive`**: `1` - The sprite uses additive blending for a glowing effect.

### Particle Effects (`ParticleEmitterComponent`)

Generates visual particles around the projectile.

*   **`emitted_material_name`**: `spark_blue` - Emits blue sparks.
*   **`gravity.y`**: `0.10` - Slight downward gravity for particles.
*   **`count_min`**: `1`, **`count_max`**: `5` - Emits between 1 and 5 particles per emission.
*   **`lifetime_min`**: `0.6`, **`lifetime_max`**: `0.8` - Particles last between 0.6 and 0.8 seconds.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.

### Lighting (`LightComponent`)

Adds a light source to the projectile.

*   **`radius`**: `150` - The light extends 150 units.
*   **`r`**: `30`, **`g`**: `30` - Blueish light color.
*   **`b`**: `90`

### Audio (`AudioComponent`)

Handles sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Uses the projectiles audio bank.
*   **`event_root`**: `projectiles/orb_b` - Triggers sounds related to blue orbs.

### Laser Emitters (`LaserEmitterComponent`)

This entity utilizes four `LaserEmitterComponent` instances to create four distinct laser beams. Each component is configured to emit a laser with specific properties.

*   **`is_emitting`**: `0` - This is set to `0` by default, meaning the lasers are not active until triggered by a script.
*   **`laser_angle_add_rad`**: This attribute is used to offset the angle of each laser beam.
    *   The first emitter has no offset (0 radians).
    *   The second has an offset of `1.570796` radians (90 degrees).
    *   The third has an offset of `3.14159` radians (180 degrees).
    *   The fourth has an offset of `4.712` radians (270 degrees).
*   **`laser`**: The nested `<laser>` tag defines the properties of each beam:
    *   **`damage_to_entities`**: `0.08` - Small damage to entities.
    *   **`max_cell_durability_to_destroy`**: `11` - Durability of cells destroyed by the laser.
    *   **`damage_to_cells`**: `12000` - High damage to terrain cells.
    *   **`root_entity_is_responsible_for_damage`**: `1` - The projectile entity is responsible for damage.
    *   **`max_length`**: `112` - The maximum length of the laser beam.
    *   **`beam_radius`**: `3.5` - The width of the laser beam.
    *   **`hit_particle_chance`**: `20` - Chance to spawn particles on hit.
    *   **`beam_particle_chance`**: `90` - High chance to spawn particles along the beam.
    *   **`beam_particle_type`**: `plasma_fading` - Uses fading plasma particles for the beam.

### Script Execution (`LuaComponent`)

This component triggers a Lua script to manage the laser emission.

*   **`script_source_file`**: `data/scripts/projectiles/laser_emitter_start.lua` - The script responsible for activating the lasers.
*   **`execute_every_n_frame`**: `2` - The script runs every 2 frames.
*   **`remove_after_executed`**: `1` - The script is removed after its first execution.

### Variable Storage (`VariableStorageComponent`)

Stores a reference to the projectile's own XML file.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/orb_laseremitter_four.xml`