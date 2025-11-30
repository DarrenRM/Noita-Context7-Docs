---
title: Bounce Spark Projectile Spawner
category: scripts
---

---

# Bounce Spark Projectile Spawner

This script defines the behavior for a projectile that spawns other projectiles. When this projectile is active, it will create one or more "bounce spark" projectiles.

## Key Functionality

*   **Projectile Spawning:** The primary function is to spawn child projectiles.
*   **Randomized Spawning:** The number and direction of spawned projectiles are randomized.
*   **Projectile Types:** It can spawn two types of child projectiles:
    *   `bounce_spark_friendly_fire.xml`: A standard bounce spark projectile.
    *   `bounce_spark_friendly_fire_silent.xml`: A silent variant of the bounce spark projectile.
*   **Self-Destruction:** The parent projectile is killed after spawning its children.

## Core Attributes

*   `entity_id`: The unique identifier for the projectile entity.
*   `pos_x`, `pos_y`: The current position of the projectile.
*   `angle`: The initial angle for spawning child projectiles, determined procedurally.
*   `speed`: The speed of the spawned child projectiles, randomized within a range.
*   `vel_x`, `vel_y`: The calculated velocity components for the spawned projectiles.
*   `extra`: A random value determining if additional silent projectiles are spawned.

## Spawning Logic

1.  **Initialization:** Retrieves the projectile's entity ID and position. Sets a random seed based on position and game frame.
2.  **Primary Spawn:**
    *   Calculates a random `angle` and `speed`.
    *   Determines `vel_x` and `vel_y` based on the angle and speed.
    *   Spawns a `bounce_spark_friendly_fire.xml` projectile using `shoot_projectile_from_projectile`.
3.  **Optional Additional Spawns:**
    *   A random `extra` value is calculated (0, 1, or 2).
    *   If `extra` is greater than 0, a loop runs `extra` times.
    *   Inside the loop, a new random `angle` and `speed` are calculated.
    *   `vel_x` and `vel_y` are determined.
    *   A `bounce_spark_friendly_fire_silent.xml` projectile is spawned.
4.  **Cleanup:** The parent projectile is killed using `EntityKill(entity_id)`.

## Key Functions Used

*   `GetUpdatedEntityID()`: Gets the ID of the entity that executed the script.
*   `EntityGetTransform(entity_id)`: Retrieves the position of an entity.
*   `SetRandomSeed(seed1, seed2)`: Initializes the random number generator.
*   `ProceduralRandom(seed1, seed2)`: Generates a pseudo-random number based on seeds.
*   `Random(min, max)`: Generates a random number within a specified range.
*   `math.cos(angle)`, `math.sin(angle)`: Trigonometric functions for calculating velocity components.
*   `shoot_projectile_from_projectile(parent_entity_id, projectile_xml_path, pos_x, pos_y, vel_x, vel_y, is_enemy)`: Spawns a new projectile from an existing one.
*   `math.max(a, b)`: Returns the larger of two numbers.
*   `EntityKill(entity_id)`: Destroys an entity.