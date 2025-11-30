---
title: Base Projectile Physics
category: entities
---

# Base Projectile Physics

This document describes the core components and attributes for defining projectile physics in Noita, serving as a foundational template for custom projectile entities.

## Core Components

### PhysicsBodyComponent
Defines the physical properties of the projectile.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `uid`                 | Unique identifier for the physics body.                                  |
| `allow_sleep`         | Whether the body can enter a sleep state to save performance.            |
| `is_bullet`           | Marks this as a bullet, affecting collision detection and physics.       |
| `auto_clean`          | If `1`, the physics body is automatically removed when no longer needed. |
| `on_death_leave_physics_body` | If `1`, the physics body persists after the entity dies.               |
| `hax_fix_going_through_ground` | A workaround to prevent projectiles from passing through the ground. |

### PhysicsImageShapeComponent
Defines the visual shape and collision material of the projectile.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `body_id` | Links this shape to a `PhysicsBodyComponent` by its `uid`.               |
| `material`| The physics material used for collision (e.g., "fuse", "wood").          |

### PhysicsThrowableComponent
Enables the projectile to be thrown.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `throw_force_coeff` | A coefficient that influences the force applied when throwing.           |

### VelocityComponent
Manages the projectile's velocity.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `affect_physics_bodies` | If `1`, this component's velocity will influence physics bodies.         |

### DamageModelComponent
Handles damage-related properties, including interactions with materials.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `fire_damage_amount`      | The amount of fire damage dealt.                                         |
| `hp`                      | The hit points of the projectile.                                        |
| `materials_damage`        | If `1`, the projectile can damage materials it collides with.            |
| `materials_that_damage`   | A comma-separated list of materials that will damage the projectile.     |
| `materials_how_much_damage` | The amount of damage dealt to materials.                                 |

### ProjectileComponent
Defines the projectile's behavior over its lifetime and upon death.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `on_lifetime_out_explode` | If `1`, the projectile explodes when its lifetime expires.               |
| `on_death_explode`      | If `1`, the projectile explodes when it dies.                            |
| `lifetime`              | The duration (in frames) the projectile exists before expiring.          |
| `on_death_gfx_leave_sprite` | If `1`, the projectile's sprite remains after death.                     |
| `do_moveto_update`      | If `1`, the projectile will attempt to move towards a target.            |

#### `config_explosion`
Defines the parameters for an explosion when the projectile dies or its lifetime ends.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `damage`                  | The base damage dealt by the explosion.                                  |
| `camera_shake`            | The intensity of camera shake caused by the explosion.                   |
| `explosion_radius`        | The radius of the explosion's effect.                                    |
| `explosion_sprite`        | Path to the sprite used for the explosion visual effect.                 |
| `load_this_entity`        | Path to an entity to load as a particle effect upon explosion.           |
| `ray_energy`              | The energy of the explosion's destructive rays.                          |
| `physics_explosion_power.min` | The minimum force applied to physics objects by the explosion.           |
| `physics_explosion_power.max` | The maximum force applied to physics objects by the explosion.           |
| `sparks_count_min`        | Minimum number of sparks created by the explosion.                       |
| `sparks_count_max`        | Maximum number of sparks created by the explosion.                       |
| `stains_radius`           | The radius of stains left by the explosion.                              |