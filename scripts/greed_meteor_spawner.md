---
title: Greed Meteor Spawner
category: scripts
---

# Greed Meteor Spawner

This script is responsible for spawning meteors as part of the "Greed Curse" mechanic in Noita. It triggers a screen shake and then spawns a random number of meteors at a specified location.

## Key Attributes

*   **`count`**: Determines the number of meteors to spawn. This is a random value between 1 and 3.
*   **`shoot_projectile`**: The core function used to spawn entities.
    *   **`entity_id`**: The ID of the entity executing this script.
    *   **`"data/entities/misc/greed_curse/greed_meteor.xml"`**: The XML file defining the meteor entity to be spawned.
    *   **`pos_x + Random( -360, 360 )`**: The X-coordinate for the meteor spawn. It's offset from the spawner's X position by a random amount between -360 and 360.
    *   **`pos_y - 300`**: The Y-coordinate for the meteor spawn. It's consistently 300 units above the spawner's Y position.
    *   **`Random( -200, 200 )`**: The initial X velocity of the meteor, randomized between -200 and 200.
    *   **`Random( 700, 1500 )`**: The initial Y velocity of the meteor, randomized between 700 and 1500, giving it a downward trajectory.
*   **`GameScreenshake( 15 )`**: Triggers a screen shake with an intensity of 15.

## Usage

This script is typically attached to an entity that acts as a trigger for the Greed Curse's meteor event. When the conditions for the curse are met, this script is executed, leading to the visual and gameplay effect of meteors falling from the sky.

## Related Files

*   `data/entities/misc/greed_curse/greed_meteor.xml`: Defines the appearance and behavior of the spawned meteors.