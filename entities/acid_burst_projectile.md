---
title: Acid Burst Projectile
category: entities
---

# Acid Burst Projectile

This document details the `acidburst.xml` entity, defining a player-owned projectile that emits acid particles.

## Core Entity Properties

*   **name**: `$projectile_default` - A generic name, often overridden by specific projectile types.
*   **tags**: `acid`, `projectile_player` - Identifies the projectile as acidic and originating from the player.

## Base Projectile Configuration

The projectile inherits properties from `data/entities/base_projectile.xml`.

### Velocity Component

*   **gravity\_y**: `-100` - Applies a constant upward force, counteracting gravity.
*   **mass**: `0.02` - Defines the projectile's mass.

## Projectile Component

This component governs the projectile's behavior and interactions.

### Key Attributes:

*   **lob\_min**: `0.8` - Minimum lobbing factor for projectile trajectory.
*   **lob\_max**: `1.0` - Maximum lobbing factor for projectile trajectory.
*   **speed\_min**: `0` - Minimum initial speed.
*   **speed\_max**: `0` - Maximum initial speed. (Projectile speed is not directly set here, likely influenced by other factors or initial velocity).
*   **friction**: `0.0` - No friction applied to the projectile.
*   **direction\_random\_rad**: `0.2` - Introduces a slight random deviation in the projectile's direction.
*   **penetrate\_entities**: `1` - Allows the projectile to pass through entities.
*   **lifetime**: `10` - The projectile exists for 10 frames before expiring.
*   **damage**: `0` - The projectile itself deals no direct damage.
*   **damage\_every\_x\_frames**: `15` - Damage is applied every 15 frames if applicable (though damage is 0 here).

### Other Notable Attributes:

*   `on_death_explode`: `0` - Does not explode upon death.
*   `on_death_gfx_leave_sprite`: `0` - Does not leave a sprite upon death.
*   `on_lifetime_out_explode`: `0` - Does not explode when lifetime ends.
*   `explosion_dont_damage_shooter`: `1` - If it were to explode, it wouldn't damage the shooter.
*   `die_on_low_velocity`: `0` - Does not die when velocity becomes low.
*   `on_collision_die`: `0` - Does not die upon collision.
*   `velocity_sets_scale`: `0` - Velocity does not affect scaling.
*   `lifetime_randomness`: `0` - Lifetime is fixed.
*   `ragdoll_force_multiplier`: `0.01` - Minimal force applied to ragdolls.
*   `hit_particle_force_multiplier`: `0.25` - Moderate force for hit particles.
*   `camera_shake_when_shot`: `0.0` - No camera shake when fired.

## Particle Emitter Component

This component controls the emission of acid particles.

### Key Attributes:

*   **emitted\_material\_name**: `acid` - The material of the particles emitted.
*   **count\_min**: `15` - Minimum number of particles emitted per emission cycle.
*   **count\_max**: `20` - Maximum number of particles emitted per emission cycle.
*   **lifetime\_min**: `1.1` - Minimum lifetime of emitted particles.
*   **lifetime\_max**: `2.8` - Maximum lifetime of emitted particles.
*   **create\_real\_particles**: `1` - Emits actual game particles.
*   **is\_emitting**: `1` - The emitter is active.

### Positional and Velocity Offsets:

*   **offset.x**: `0`
*   **offset.y**: `2`
*   **x\_pos\_offset\_min**: `-8`
*   **y\_pos\_offset\_min**: `-8`
*   **x\_pos\_offset\_max**: `8`
*   **y\_pos\_offset\_max**: `8`
*   **x\_vel\_min**: `-10`
*   **x\_vel\_max**: `10`
*   **y\_vel\_min**: `-10`
*   **y\_vel\_max**: `10`

### Emission Interval:

*   **emission\_interval\_min\_frames**: `1`
*   **emission\_interval\_max\_frames**: `1` - Particles are emitted continuously with no delay between frames.

## Audio Component

*   **file**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank.
*   **event\_root**: `projectiles/acid` - The root event for acid projectile sounds.

## Variable Storage Component

*   **name**: `projectile_file`
*   **value\_string**: `data/entities/projectiles/deck/acidburst.xml` - Stores the path to this entity's XML file.