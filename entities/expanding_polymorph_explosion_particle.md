---
title: Expanding Polymorph Explosion Particle
category: entities
---

# Expanding Polymorph Explosion Particle

This entity defines a particle effect that expands outwards, simulating a polymorph explosion. It utilizes a `ProjectileComponent` to manage its lifetime and trigger an explosion when it expires, and a `SpriteParticleEmitterComponent` to generate the visual particles.

## Key Components and Attributes

### ProjectileComponent

This component governs the projectile's behavior, including its lifetime and how it reacts upon death or expiration.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lifetime`                | The duration (in frames) the projectile exists before expiring.             |
| `on_lifetime_out_explode` | If `1`, the projectile will explode when its lifetime runs out.             |
| `damage`                  | The damage dealt by the projectile. Set to `0` for this example.            |
| `speed_min`, `speed_max`  | Minimum and maximum speed of the projectile. Set to `0` for a stationary effect. |

#### `config_explosion`

This nested element defines the properties of the explosion triggered by the projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `damage`                  | Damage dealt by the explosion. Set to `0` for this example.                 |
| `explosion_radius`        | The radius of the explosion. Set to `0` for this example.                   |
| `camera_shake`            | The intensity of camera shake caused by the explosion. Set to `0`.          |
| `particle_effect`         | If `1`, particles are created by the explosion. Set to `0`.                 |
| `damage_mortals`          | If `1`, the explosion damages living entities. Set to `0`.                  |
| `physics_explosion_power` | The power of the physics-based explosion. Set to `0`.                       |

### SpriteParticleEmitterComponent

This component is responsible for emitting visual particles that form the expanding explosion effect.

| Attribute                     | Description