---
title: Electricity Pulse Prop
category: scripts
---

---

# Electricity Pulse Prop

This script defines a prop that generates an electrical pulse. When activated, it spawns several "electricity_medium" entities in a circular pattern around its position.

## Key Attributes

*   **`entity_id`**: The unique identifier for the entity running this script.
*   **`x`, `y`**: The world coordinates of the prop.
*   **`dir_x`, `dir_y`**: Initial direction vector for the pulse. In this case, it's set to `(16, 0)`, indicating a horizontal direction.
*   **`dx`, `dy`**: Variables to store the calculated offset for spawning entities.
*   **Loop for Spawning**: The script iterates 4 times to spawn multiple electricity entities.
    *   **`vec_rotate( dir_x, dir_y, math.pi * 0.5 * ( i - 1 ) )`**: This function rotates the initial direction vector (`dir_x`, `dir_y`) by increments of 90 degrees (`math.pi * 0.5`) for each iteration (`i`). This creates a circular spread of the spawned entities.
    *   **`EntityLoad( "data/entities/misc/electricity_medium.xml", x + dx, y + dy )`**: This function loads the `electricity_medium.xml` entity at the calculated position (`x + dx`, `y + dy`), effectively creating the electrical pulse effect.

## Example Usage

This script is typically attached to a prop entity that, when triggered (e.g., by proximity, a switch, or another event), will execute this Lua code to create the electrical pulse. The `electricity_medium.xml` entity would then define the visual and damage properties of the electrical discharge.