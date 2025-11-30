---
title: Firepillar Projectile Behavior
category: entities
---

# Firepillar Projectile Behavior

This Lua script defines the behavior of a projectile fired by the boss centipede, specifically the "firepillar". It handles the spawning and initial velocity of these projectiles.

## Key Attributes and Actions

*   **Entity Initialization**:
    *   Retrieves the unique `entity_id` for the current projectile.
    *   Gets the `pos_x` and `pos_y` coordinates of the projectile's spawn location.

*   **Sound Effect**:
    *   Plays a "duplicate" sound effect when the projectile is initialized.

*   **Projectile Spawning**:
    *   Uses the `shoot_projectile_from_projectile` function to create new projectile entities.
    *   Each spawned projectile is of type `data/entities/animals/boss_centipede/firepillar_part.xml`.

*   **Velocity Calculation**:
    *   The horizontal velocity (`vel_x`) is procedurally randomized based on the projectile's position, creating a slight spread.
    *   The spawned projectiles have varying vertical and horizontal velocities to create a distinct firing pattern.

## Spawning Details

The script spawns three `firepillar_part` projectiles with the following characteristics:

| Projectile Index | Horizontal Velocity (`vel_x`) | Vertical Velocity (`vel_y`) |
| :--------------- | :---------------------------- | :-------------------------- |
| 1                | Procedurally Randomized       | -75                         |
| 2                | 0                             | -200                        |
| 3                | `-vel_x * 2`                  | -150                        |