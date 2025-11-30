---
title: Laser Gate Horizontal Emitter Logic
category: scripts/buildings
---

# Laser Gate Horizontal Emitter Logic

This script controls the emission behavior of a horizontal laser gate entity in Noita. It dynamically toggles the laser emitter based on a calculated "arc" value, creating a pulsating or flickering effect.

## Key Components and Logic

### Entity Initialization

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions.
*   **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity.
*   **`local x,y = EntityGetTransform( entity_id )`**: Gets the entity's position. This is used to introduce variation in the emission pattern based on its vertical placement.

### Emission Pattern Calculation

*   **`local arc = math.cos( GameGetFramNum() * 0.03 + y * 0.05 )`**: This is the core of the emission logic.
    *   `GameGetFrameNum()`: The current game frame number, providing a time-based oscillation.
    *   `* 0.03`: Controls the speed of the oscillation.
    *   `y * 0.05`: Introduces a spatial variation. Entities at different vertical positions will have slightly different oscillation phases.
    *   `math.cos()`: The cosine function creates a smooth, oscillating value between -1 and 1.

### Laser Emitter Control

*   **`local comp = EntityGetFirstComponent( entity_id, "LaserEmitterComponent" )`**: Attempts to find the `LaserEmitterComponent` attached to the entity.
*   **`if ( comp ~= nil ) then ... end`**: Executes the following code only if the `LaserEmitterComponent` is found.
*   **`if ( arc < 0 ) then ComponentSetValue2( comp, "is_emitting", true ) else ComponentSetValue2( comp, "is_emitting", false ) end`**:
    *   If the calculated `arc` value is less than 0 (meaning the cosine wave is in its negative phase), the `is_emitting` property of the `LaserEmitterComponent` is set to `true`, activating the laser.
    *   Otherwise (if `arc` is 0 or positive), `is_emitting` is set to `false`, deactivating the laser.

This results in the laser gate emitting a laser beam when the `arc` value is negative, creating a pulsating or flickering effect that varies slightly with the gate's vertical position.