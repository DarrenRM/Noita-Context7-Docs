---
title: Fizzle Projectile Logic
category: scripts
---

# Fizzle Projectile Logic

This script defines the behavior of the "Fizzle" projectile in Noita. When a Fizzle projectile hits a target, there's a chance it will cause the target to fizzle out, destroying it and spawning additional Fizzle projectiles.

## Key Functionality

### Target Identification

The script first determines the `target_id`. This is typically the entity that fired the projectile or the projectile itself if it has no parent with `GenomeDataComponent`.

### Fizzle Chance

A random chance is calculated to determine if the fizzle effect will occur.

### Projectile Spawning

If the fizzle effect is triggered:
- The target entity is destroyed.
- Five new "fizzle.xml" projectiles are spawned, originating from the target's position and inheriting its velocity.

## Core Attributes/Elements

### `entity_id`
- **Description:** The unique identifier for the current Fizzle projectile entity.
- **Usage:** Used for calculating random seeds and identifying the entity.

### `parent_id`
- **Description:** The entity that spawned this Fizzle projectile.
- **Usage:** Used to determine if the projectile has a parent and to access its components.

### `target_id`
- **Description:** The entity that will be affected by the Fizzle projectile.
- **Usage:** This is the primary entity that the script interacts with for destruction and projectile spawning.

### `fizzle`
- **Description:** A random integer between 1 and 10.
- **Usage:** Determines the probability of the fizzle effect occurring (1 in 10 chance).

### `vel_x`, `vel_y`
- **Description:** The velocity components of the target entity.
- **Usage:** These values are used to set the velocity of the newly spawned Fizzle projectiles.

### `shoot_projectile_from_projectile`
- **Description:** A utility function used to spawn new projectiles.
- **Parameters:**
    - `target_id`: The entity to spawn the projectile from.
    - `"data/entities/projectiles/deck/fizzle.xml"`: The XML file defining the projectile to spawn.
    - `x`, `y`: The spawn position.
    - `vel_x`, `vel_y`: The spawn velocity.

### `EntityKill`
- **Description:** A function to destroy an entity.
- **Usage:** Used to destroy the `target_id` when the fizzle effect is triggered.