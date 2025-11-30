---
title: Orb Laser Emitter Projectile
category: entities
---

# Orb Laser Emitter Projectile

This document describes the `orb_laseremitter.xml` entity, which defines a player projectile that emits a laser.

## Core Components

This projectile utilizes several key components to define its behavior and appearance.

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="7"`: Moderate air resistance.
    *   `mass="0.05"`: Low mass.

### Projectile Behavior (`ProjectileComponent`)

Defines the projectile's movement, damage, and interaction properties.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's arc.
*   **`speed_min="40"`, `speed_max="40"`**: The projectile travels at a constant speed of 40.
*   **`die_on_low_velocity="0"`**: Does not die when its velocity becomes low.
*   **`on_death_explode="0"`**: Does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave a sprite upon death.
*   **`on_lifetime_out_explode="0"`**: Does not explode when its lifetime ends.
*   **`explosion_dont_damage_shooter="1"`**: If it were to explode, it wouldn't damage the shooter.
*   **`damage="0.8"`**: Base damage of the projectile itself (likely before laser).
*   **`on_collision_die="0"`**: Does not die upon collision.
*   **`lifetime="100"`**: The projectile exists for 100 frames.
*   **`knockback_force="1.3"`**: Applies a knockback force of 1.3.

### Visuals (`SpriteComponent`)

Defines the projectile's visual representation.

*   **`_enabled="0"`**: This sprite component is initially disabled.
*   **`image_file="data/projectiles_gfx/orb_blue.xml"`**: Uses a blue orb graphic.
*   **`offset_x="6"`, `offset_y="6"`**: Offsets the sprite's position.
*   **`rect_animation="spawn"`**: Uses a "spawn" animation.
*   **`emissive="1"`, `additive="1"`**: The sprite is emissive and uses additive blending for a glowing effect.

### Particle Effects (`ParticleEmitterComponent`)

Generates visual particles.

*   **`emitted_material_name="spark_blue"`**: Emits blue sparks.
*   **`gravity.y="0.10"`**: Particles are affected by slight gravity.
*   **`count_min="1"`, `count_max="5"`**: Emits between 1 and 5 particles per emission.
*   **`lifetime_min="0.6"`, `lifetime_max="0.8"`**: Particles last between 0.6 and 0.8 seconds.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="1"`**: The emitter is active.

### Lighting (`LightComponent`)

Adds a light source to the projectile.

*   **`_enabled="1"`**: The light component is active.
*   **`radius="150"`**: The light has a radius of 150 units.
*   **`r="30"`, `g="30"`, `b="90"`**: The light color is a dark blue.

### Audio (`AudioComponent`)

Handles sound effects.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Uses the projectiles audio bank.
*   **`event_root="projectiles/orb_b"`**: Triggers the "orb_b" sound event.

### Laser Emission (`LaserEmitterComponent`)

Controls the laser beam.

*   **`is_emitting="0"`**: The laser is initially not emitting.
*   **`<laser>`**: Defines the laser's properties:
    *   `damage_to_entities="0.12"`: Deals 0.12 damage per tick to entities.
    *   `max_cell_durability_to_destroy="11"`: Can destroy 11 durability from terrain cells.
    *   `damage_to_cells="12000"`: Deals 12000 damage to terrain cells.
    *   `root_entity_is_responsible_for_damage="1"`: The emitter is responsible for damage calculation.
    *   `max_length="160"`: The laser beam has a maximum length of 160.
    *   `beam_radius="1.5"`: The laser beam has a radius of 1.5.
    *   `hit_particle_chance="20"`: 20% chance to spawn hit particles.
    *   `beam_particle_chance="90"`: 90% chance to spawn beam particles.
    *   `beam_particle_type="plasma_fading"`: Uses "plasma_fading" particles for the beam.

### Lua Scripting (`LuaComponent`)

Executes custom Lua logic.

*   **`script_source_file="data/scripts/projectiles/laser_emitter_start.lua"`**: Executes a script to manage the laser emitter's activation.
*   **`execute_every_n_frame="2"`**: Executes the script every 2 frames.
*   **`remove_after_executed="1"`**: Removes the Lua component after its first execution.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables.

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
*   **`value_string="data/entities/projectiles/deck/orb_laseremitter.xml"`**: The value is the file path itself.