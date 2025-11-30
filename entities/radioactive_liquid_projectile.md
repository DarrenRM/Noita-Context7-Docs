---
title: Radioactive Liquid Projectile
category: entities
---

---

# Radioactive Liquid Projectile

This document details the configuration for the "radioactive_liquid" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag, inheriting base projectile properties.

```xml
<Entity name="$projectile_default" >
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
    		gravity_y="-100">
    	</VelocityComponent>
	</Base>
    <!-- ... ProjectileComponent, ParticleEmitterComponent, VariableStorageComponent ... -->
</Entity>
```

## Key Components

### ProjectileComponent

This component governs the projectile's behavior, including its movement, damage, and interaction with the environment.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | Minimum and maximum lob angle (in radians) for projectile trajectory.       |
| `speed_min`, `speed_max`  | Minimum and maximum initial speed of the projectile.                        |
| `friction`                | How quickly the projectile loses velocity due to air resistance.            |
| `direction_random_rad`    | Random deviation in projectile direction (in radians).                      |
| `die_on_low_velocity`     | If true, the projectile is destroyed when its velocity drops below a threshold. |
| `on_collision_die`        | If true, the projectile is destroyed upon colliding with something.         |
| `lifetime`                | Base duration (in frames) the projectile exists before expiring.            |
| `lifetime_randomness`     | Additional random duration (in frames) added to the projectile's lifetime.  |
| `damage`                  | The amount of damage the projectile deals on impact.                        |
| `camera_shake_when_shot`  | Intensity of camera shake when this projectile is fired.                    |

### ParticleEmitterComponent

This component controls the visual effects of the projectile, specifically the emission of "radioactive_liquid" particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to be emitted.                           |
| `count_max`               | The maximum number of particles to be emitted.                              |
| `offset.x`, `offset.y`    | Offset from the projectile's center for particle emission.                  |
| `x_pos_offset_min/max`    | Minimum and maximum horizontal offset for particle spawn position.          |
| `y_pos_offset_min/max`    | Minimum and maximum vertical offset for particle spawn position.            |
| `x_vel_min/max`           | Minimum and maximum horizontal velocity for emitted particles.              |
| `y_vel_min/max`           | Minimum and maximum vertical velocity for emitted particles.                |
| `lifetime_min/max`        | Minimum and maximum lifetime (in frames) for emitted particles.             |
| `create_real_particles`   | If true, creates actual game particles rather than cosmetic ones.           |
| `emission_interval_min/max_frames` | The frame interval between particle emissions.                            |
| `is_emitting`             | If true, the particle emitter is active.                                    |

### VariableStorageComponent

This component stores variables associated with the entity. In this case, it stores the projectile's own file path.

| Attribute      | Description                                  |
| :------------- | :------------------------------------------- |
| `name`         | The name of the variable.                    |
| `value_string` | The string value assigned to the variable.   |