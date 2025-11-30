---
title: Fish Projectile
category: entities
---

# Fish Projectile

This document describes the `fish.xml` entity, which defines a projectile in Noita. It inherits base projectile properties and incorporates elements from the `fish.xml` animal entity, suggesting it behaves like a small, fleeing creature when launched.

## Key Components

### ProjectileComponent
This is the core component defining the projectile's behavior.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | Controls the minimum and maximum lob angle of the projectile.               |
| `speed_min`, `speed_max`  | Sets the range for the projectile's initial speed.                          |
| `friction`                | Determines how quickly the projectile loses speed due to air resistance.    |
| `direction_random_rad`    | Adds a small random deviation to the projectile's initial direction.        |
| `on_death_explode`        | If true, the projectile explodes upon death. Set to `0` here.               |
| `on_collision_die`        | If true, the projectile dies upon collision. Set to `0` here.               |
| `lifetime`                | The duration the projectile exists. `-1` means it lasts indefinitely.       |
| `damage`                  | The base damage dealt by the projectile. Set to `0` here.                   |
| `bounces_left`            | The number of times the projectile can bounce off surfaces.                 |
| `camera_shake_when_shot`  | The intensity of camera shake when this projectile is fired.                |
| `hit_particle_force_multiplier` | Multiplier for particle force when hitting something.                     |

### Base Components
The entity inherits from `base_projectile.xml` for fundamental projectile mechanics and `data/entities/animals/fish.xml` for creature-like behavior.

*   **`base_projectile.xml`**: Provides standard projectile functionality.
*   **`data/entities/animals/fish.xml`**: This inclusion suggests the projectile might adopt some AI or visual characteristics of a fish, though many animal-specific components are commented out or disabled.

### VariableStorageComponent
*   `projectile_file`: Stores the path to this entity's XML file, useful for referencing.

## Notable Exclusions/Commented-Out Sections

The `fish.xml` entity contains significant commented-out sections from the `fish.xml` animal base. These include:

*   **`CameraBoundComponent`**: Disabled, meaning the projectile is not bound by camera limits.
*   **`AnimalAIComponent`**: Most AI behaviors are commented out, suggesting the projectile doesn't actively pursue or attack.
*   **`DamageModelComponent`**: Health and fire probability are commented out.
*   **`SpriteComponent`**: The sprite is commented out, implying the projectile might not have a visible graphic by default or relies on other entities for its appearance.
*   **`HitboxComponent`**: Defines the collision area.
*   **`PathFindingComponent`**: Allows for swimming and diving, which might be relevant if the projectile interacts with liquids.
*   **`CollisionTriggerComponent`**: Commented out, this would have defined a trigger area for destruction.
*   **`ExplosionComponent`**: Commented out, this would have defined an explosion effect upon death.

These commented-out sections indicate that the `fish.xml` projectile is primarily a fast-moving, bouncing projectile with minimal inherent damage or complex AI, likely intended for utility or as a component in other spell effects.