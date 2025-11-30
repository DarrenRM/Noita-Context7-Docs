---
title: Wizard Cave Gate Logic
category: scripts
---

# Wizard Cave Gate Logic

This script defines the behavior of the Wizard Cave Gate, a special entity that interacts with projectiles and collects "egg items" to eventually spawn a monster spawner.

## Core Functionality

The gate exerts a repulsive force on projectiles within a certain radius and absorbs nearby "egg items". Once a specific number of eggs are collected, the gate transforms into a monster spawner and plays a unique soundscape.

## Key Attributes

*   **`distance_full`**: Defines the maximum radius (in pixels) within which the gate exerts its force on projectiles.
*   **`max_egg_count`**: The number of "egg items" the gate needs to collect before triggering its transformation.
*   **`calculate_force_at(body_x, body_y)`**: A function that calculates the repulsive force vector to be applied to an entity at `(body_x, body_y)`. The force is inversely proportional to the distance from the gate's center.
*   **Projectile Repulsion**: The script iterates through all entities tagged as "projectile" within `distance_full`. For each projectile with a `VelocityComponent`, it calculates a repulsive force using `calculate_force_at` and applies it, dampening vertical velocity.
*   **Physics Body Force Application**: The `PhysicsApplyForceOnArea` function is used to apply a calculated force to all physics bodies within a defined area around the gate. The force is scaled by the body's mass.
*   **Egg Collection**: The script checks for entities tagged as "egg\_item" within a 70-pixel radius. If an egg is found and is not being held, it is absorbed:
    *   An `wizardcave_gate_egg_fx.xml` entity is spawned at the egg's location.
    *   A sound effect is played.
    *   The egg entity is destroyed.
    *   An internal counter (`egg_count`) is incremented.
*   **Transformation Trigger**: When the `egg_count` reaches `max_egg_count`:
    *   A `wizardcave_gate_monster_spawner.xml` entity is spawned at the gate's original position.
    *   A specific audio event is triggered, including music fade-out and a new music track.
    *   The Wizard Cave Gate entity is destroyed.

## Internal Variables

*   **`entity_id`**: The unique identifier for the gate entity.
*   **`x`, `y`**: The current position of the gate, which subtly drifts over time using sine and cosine functions based on the game frame number.
*   **`x_orig`, `y_orig`**: The original, static position of the gate.

## Code Structure

The script is organized into functions for calculating forces and then proceeds to handle projectile repulsion, physics body interaction, and egg collection logic sequentially. It utilizes `dofile_once` for utility functions and `is_in_camera_bounds` for optimization.