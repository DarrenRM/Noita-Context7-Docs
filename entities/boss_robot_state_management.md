---
title: Boss Robot State Management
category: entities
---

---

# Boss Robot State Management

This script manages the state and behavior of the Boss Robot entity in Noita. It controls its attack patterns, projectile firing, and laser emissions based on an internal state variable.

## Core Functionality

The script primarily interacts with `VariableStorageComponent` to track the robot's current state and `LaserEmitterComponent` to control its laser attacks. It also utilizes `EntityGetInRadiusWithTag` and `EntityGetWithTag` to detect players and other entities.

## Key Components and Variables

*   **`entity_id`**: The unique identifier for the Boss Robot entity.
*   **`x`, `y`**: The current position of the Boss Robot.
*   **`varcomps`**: A list of `VariableStorageComponent` components attached to the entity.
*   **`varcomp`**: The specific `VariableStorageComponent` used for state management.
*   **`state`**: An integer representing the current state of the Boss Robot. This is incremented over time and dictates behavior.
*   **`eatercomp`**: A `VariableStorageComponent` likely used to control a "spell eater" mechanic.
*   **`lcomps`**: A list of `LaserEmitterComponent` components attached to the entity.

## State Transitions and Behaviors

The script cycles through various states, each triggering a different action:

*   **`state == 2`**:
    *   Disables the spell eater (`eatercomp.value_int = 0`).
    *   If players are within 300 units, fires 10 rockets (`rocket_roll.xml`) in random directions.
*   **`state == 4`**:
    *   Enables the spell eater (`eatercomp.value_int = 1`).
*   **`state == 6`**:
    *   Disables the spell eater (`eatercomp.value_int = 0`).
    *   If `LaserEmitterComponent`s exist, aims a laser at the nearest player and sets its properties:
        *   `beam_radius`: 1.5
        *   `damage_to_entities`: 0
        *   `damage_to_cells`: 10
        *   `max_cell_durability_to_destroy`: 2
        *   `audio_enabled`: false
    *   Enables laser emission (`is_emitting = true`).
*   **`state == 8`**:
    *   Modifies the `LaserEmitterComponent` properties for a more powerful attack:
        *   `beam_radius`: 10.5
        *   `damage_to_entities`: 0.6
        *   `damage_to_cells`: 700000
        *   `max_cell_durability_to_destroy`: 14
    *   Enables audio for the first laser emitter (`audio_enabled = true` for `a == 1`).
*   **`state == 10`**:
    *   Disables laser emission (`is_emitting = false`).
    *   Resets laser properties to their initial values (similar to state 6).
    *   Enables the spell eater (`eatercomp.value_int = 1`).
*   **`state == 13`**:
    *   Spawns a "healer drone" (`healerdrone_physics.xml`) if fewer than 3 are present.
    *   Resets the state to 0, restarting the cycle.

## Helper Functions Used

*   **`GetUpdatedEntityID()`**: Retrieves the entity's ID.
*   **`EntityGetTransform( entity_id )`**: Gets the position of an entity.
*   **`EntityGetComponent( entity_id, component_name )`**: Retrieves components attached to an entity.
*   **`ComponentGetValue2( component, value_name )`**: Gets the value of a component's property.
*   **`ComponentSetValue2( component, value_name, value )`**: Sets the value of a component's property.
*   **`SetRandomSeed( x, y )`**: Seeds the random number generator.
*   **`Random( min, max )`**: Generates a random number.
*   **`EntityGetInRadiusWithTag( x, y, radius, tag )`**: Finds entities within a radius with a specific tag.
*   **`shoot_projectile( owner_id, projectile_xml, x, y, vx, vy )`**: Fires a projectile.
*   **`EntityGetWithTag( tag )`**: Finds all entities with a specific tag.
*   **`math.atan2( y, x )`**: Calculates the angle between the positive x-axis and the point (x, y).
*   **`ComponentObjectSetValue2( component, object_name, property_name, value )`**: Sets a property of an object within a component.
*   **`EntityLoad( entity_xml, x, y )`**: Loads a new entity at a specified position.