---
title: Physics Trap Laser Script
category: scripts
---

---

# Physics Trap Laser Script

This script controls the behavior of a physics trap laser entity in Noita, specifically its activation and damage-related functions.

## Core Functionality

### `electricity_receiver_switched(on)`

This function is triggered when the entity receives an electricity signal, acting as a switch.

-   **`on` (boolean):**
    -   `true`: Activates the laser emitter.
    -   `false`: Deactivates the laser emitter.

It iterates through the entity's children, finds the one named "laser", and manipulates its `LaserEmitterComponent` to control emission.

### `damage_received(damage, message, entity_thats_responsible, is_fatal)`

This function is called when the entity takes damage.

-   **`damage` (number):** The amount of damage taken.
-   **`message` (string):** A description of the damage source.
-   **`entity_thats_responsible` (entity ID):** The entity that caused the damage.
-   **`is_fatal` (boolean):** Whether the damage was fatal.

This function specifically targets the "laser" child entity. It retrieves a variable storage component named "laser_duration" and uses its integer value to set the `emit_until_frame` property of the `LaserEmitterComponent`. This effectively controls how long the laser will emit after taking damage.

## Key Components Manipulated

### `LaserEmitterComponent`

This component is directly modified by the script to control the laser's emission state and duration.

-   **`is_emitting` (boolean):** Controls whether the laser is currently active.
-   **`emit_until_frame` (integer):** Sets the frame number until which the laser should emit.

### Variable Storage Component (`laser_duration`)

This component is used to store a configurable duration for the laser's emission.

-   **`value_int` (integer):** The integer value representing the duration in frames.