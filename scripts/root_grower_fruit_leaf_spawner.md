---
title: Root Grower Fruit/Leaf Spawner
category: scripts
---

---

# Root Grower Fruit/Leaf Spawner

This script determines whether to spawn a `root_grower_fruit.xml` or `root_grower_leaf.xml` entity at the current position. The choice is made probabilistically.

## Key Functionality

*   **Probabilistic Spawning:** Uses `ProceduralRandomf` to decide between spawning a fruit or a leaf.
*   **Entity Loading:** Loads either `root_grower_fruit.xml` or `root_grower_leaf.xml` based on the random outcome.
*   **Transform Application:** Sets the position and a random rotation for the spawned entity.

## Logic Breakdown

The script checks a random value against `0.5`:

*   **If `ProceduralRandomf(pos_x, pos_y) < 0.5` (50% chance):**
    *   Loads `data/entities/props/root_grower_fruit.xml`.
    *   Applies a random rotation between -90 and +90 degrees.
*   **Else (50% chance):**
    *   Loads `data/entities/props/root_grower_leaf.xml`.
    *   Applies a random rotation between 0 and 360 degrees.

## Related Entities

*   `data/entities/props/root_grower_fruit.xml`
*   `data/entities/props/root_grower_leaf.xml`