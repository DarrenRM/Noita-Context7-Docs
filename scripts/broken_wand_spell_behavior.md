---
title: Broken Wand Spell Behavior
category: scripts
---

# Broken Wand Spell Behavior

This script defines the behavior for a "broken wand" item in Noita, which periodically shoots a random projectile after a delay.

## Key Attributes

*   **`speed`**: The projectile's initial velocity.
*   **`recoil`**: The force applied to the wand when a projectile is fired.
*   **`max_torque`**: The maximum rotational force applied to the wand.
*   **`start_delay`**: The number of game frames to wait before the wand can fire its first projectile.

## Core Logic

The script operates in several stages:

### 1. Delay Check

*   It first checks a `throw_time` variable stored in the wand's `variable_storage_component`.
*   If the current frame number (`t`) is less than `throw_time + start_delay`, the script returns, preventing firing.

### 2. Spell Availability Check

*   It then checks a `spells_remaining` variable in the `variable_storage_component`.
*   If `spells_remaining` is greater than 0, the wand proceeds to fire.

### 3. Projectile Firing

*   **Position and Direction**: Retrieves the wand's current position and rotation. Calculates the projectile's velocity vector based on the wand's rotation.
*   **Recoil and Torque**: Applies recoil force opposite to the projectile's direction and a random torque to simulate instability.
*   **Offsetting**: Adjusts the projectile's spawn position slightly to prevent self-collision.
*   **Spell Selection**:
    *   A predefined list of projectile types is available:
        ```lua
        local spells = {
            "data/entities/projectiles/deck/light_bullet.xml",
            "data/entities/projectiles/deck/light_bullet.xml",
            "data/entities/projectiles/deck/arrow.xml",
            "data/entities/projectiles/deck/bullet.xml",
            "data/entities/projectiles/deck/bubbleshot.xml",
            "data/entities/projectiles/deck/disc_bullet.xml"
        }
        ```
    *   A random spell is chosen from this list using a seeded random number generator.
*   **Projectile Creation**: The `shoot_projectile` function is called to instantiate the chosen spell.
*   **Decrementing Spells**: The `spells_remaining` count is decremented.

## Helper Functions Used

*   `GetUpdatedEntityID()`: Gets the ID of the entity running the script.
*   `get_variable_storage_component()`: Retrieves a specific component from an entity.
*   `ComponentGetValue2()`: Gets the value of a component's field.
*   `ComponentSetValue2()`: Sets the value of a component's field.
*   `EntityGetTransform()`: Gets the position and rotation of an entity.
*   `vec_rotate()`: Rotates a 2D vector.
*   `PhysicsApplyForce()`: Applies a force to an entity.
*   `PhysicsApplyTorque()`: Applies a torque to an entity.
*   `ProceduralRandomf()`: Generates a random float within a range, influenced by entity position and time.
*   `SetRandomSeed()`: Seeds the random number generator.
*   `Random()`: Generates a random integer within a range.
*   `shoot_projectile()`: A custom function (likely from `utilities.lua`) to create and launch a projectile.