---
title: Tentacles Animation Script
category: scripts
---

# Tentacles Animation Script

This script animates the tentacles of an entity by controlling the motor speed of their associated `PhysicsJointComponent`s. It creates a wave-like motion.

## Key Components and Logic

### Entity and Component Identification

*   `GetUpdatedEntityID()`: Retrieves the unique identifier for the entity this script is attached to.
*   `EntityGetComponent(entity_id, "PhysicsJointComponent")`: Fetches all `PhysicsJointComponent`s associated with the entity. These components are crucial for the animation.

### Animation Parameters

*   `dir`: A direction multiplier that alternates between `1.0` and `-1.0` for each tentacle, creating opposing movements.
*   `offset`: A base offset for the sine wave calculation, allowing for phase shifting between tentacles.
*   `time`: Calculated as `GameGetFrameNum() / 60.0`, representing the elapsed time in seconds, driving the animation over time.

### Joint Component Manipulation

The script iterates through each `PhysicsJointComponent` found:

*   `ComponentSetValue(joint, "mMotorEnabled", "1")`: Enables the motor for the joint, allowing it to be controlled.
*   `ComponentSetValue(joint, "mMotorSpeed", math.sin(offset + time * 5.0) * 20.0 * dir)`: This is the core animation logic.
    *   `math.sin(...)`: Generates a smooth, oscillating value.
    *   `offset + time * 5.0`: The sine wave's input, controlled by time and the offset. The `5.0` multiplier controls the speed of the oscillation.
    *   `* 20.0`: Scales the amplitude of the sine wave.
    *   `* dir`: Applies the alternating direction for each tentacle.
*   `ComponentSetValue(joint, "mMaxMotorTorque", 1000.0)`: Sets a high maximum torque to ensure the motor can achieve the desired speed.

### Looping and Direction Alternation

*   The `dir` variable is multiplied by `-1.0` in each iteration, causing consecutive tentacles to move in opposite directions.
*   A counter `i` is used to reset the `dir` alternation after every 4 tentacles, though the `offset` modification for this reset is commented out.