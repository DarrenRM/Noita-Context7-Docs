---
title: Physics Tube Lamp Electricity Pulse
category: scripts
---

---

# Physics Tube Lamp Electricity Pulse

This script defines the behavior for a physics-based lamp that emits a weak electrical pulse when activated.

## Core Functionality

The primary function of this script is to:

1.  **Get Entity Information**: Retrieves the current entity's ID and its world coordinates (`x`, `y`).
2.  **Determine Pulse Direction**: Calculates a random direction for the electrical pulse using `vec_rotate` and `ProceduralRandomf`. This ensures variability in the pulse's trajectory.
3.  **Spawn Electrical Entity**: Loads and places a `data/entities/misc/electricity_weak.xml` entity at the calculated position, effectively creating the electrical pulse.

## Key Attributes/Elements

*   **`entity_id`**: The unique identifier for the lamp entity.
*   **`x`, `y`**: The world coordinates of the lamp.
*   **`dir_x`, `dir_y`**: Variables used to define and rotate the direction vector for the electrical pulse.
*   **`ProceduralRandomf( x, GameGetFrameNum(), 0, math.pi * 2 )`**: Generates a random angle between 0 and 2π (a full circle) based on the entity's position and the current game frame, ensuring a randomized pulse direction each time.
*   **`vec_rotate( dir_x, dir_y, angle )`**: Rotates the initial direction vector (`dir_x`, `dir_y`) by the calculated random `angle`.
*   **`EntityLoad( "data/entities/misc/electricity_weak.xml", x + dir_x, y + dir_y )`**: This is the core action. It loads the `electricity_weak.xml` entity (presumably a visual or functional representation of a weak electrical discharge) at the calculated offset from the lamp's position.

## Example Usage (Conceptual)

This script would typically be attached to an entity that acts as a "physics tube lamp." When this lamp entity is activated (e.g., by player interaction, a trigger, or another game event), this script would execute, causing a weak electrical pulse to emanate from it.

## Debugging Notes (Commented Out)

The commented-out lines indicate potential debugging tools that could be used to visualize the pulse's origin or trajectory:

*   `GameCreateSpriteForXFrames( "data/particles/radar_enemy_strong.png", x + dir_x, y + dir_y, true, 0, 0, 30 )`: Could be used to visualize a strong particle effect at the pulse's destination.
*   `GameCreateSpriteForXFrames( "data/particles/radar_enemy_medium.png", x, y, true, 0, 0, 30 )`: Could be used to visualize a medium particle effect at the lamp's origin.