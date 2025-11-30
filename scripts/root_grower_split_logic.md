---
title: Root Grower Split Logic
category: scripts
---

---

# Root Grower Split Logic

This script determines the behavior of a `root_grower` entity when it splits, deciding whether to spawn a new large branch, a regular small branch, or a leaf sprite. The probability of each outcome is determined by a procedural random number based on the entity's position and the current game frame.

## Core Logic

The script uses a series of `if-elseif` conditions based on a procedural random value `r`.

### Random Value Generation

- `r = ProceduralRandomf(pos_x, pos_y + GameGetFrameNum())`: Generates a random float between 0 and 1, influenced by the entity's X and Y coordinates and the current game frame number. This ensures consistent but varied outcomes for each `root_grower`.

### Spawn Outcomes

1.  **Large Branch (Rare):**
    *   **Condition:** `r < 0.005` (0.5% chance)
    *   **Action:** Spawns a new `root_grower.xml` entity.
    *   **Positioning:** The new entity is offset randomly by a small amount (`-3` to `3`) in both X and Y directions to encourage initial spread.

2.  **Regular Small Branch:**
    *   **Condition:** `r < 0.2` (19.5% chance, as it's `r < 0.2` but not `r < 0.005`)
    *   **Action:** Spawns a `root_grower_branch.xml` entity.
    *   **Positioning:** Similar to the large branch, the new entity is offset randomly by a small amount.

3.  **Leaf Sprite:**
    *   **Condition:** `r < 0.5` (30% chance, as it's `r < 0.5` but not `r < 0.2`)
    *   **Action:** Spawns a `root_grower_leaf.xml` entity.
    *   **Positioning:** The leaf sprite is placed at the current entity's position and rotated randomly by `0` to `2 * pi`.

## Key Attributes/Elements

-   **`ProceduralRandomf(x, y, ...)`:** A function used to generate pseudo-random numbers based on world coordinates and potentially other parameters. This is crucial for deterministic but varied world generation.
-   **`EntityLoad(filepath, x, y)`:** Loads an entity from a specified XML file at given coordinates.
-   **`EntitySetTransform(entity_id, x, y, rotation)`:** Sets the position and rotation of an entity.
-   **`GetUpdatedEntityID()`:** Retrieves the ID of the entity currently being processed.
-   **`EntityGetTransform(entity_id)`:** Retrieves the current transform (position and rotation) of an entity.
-   **`GameGetFrameNum()`:** Returns the current game frame number, used to add variability to the random seed.

## Probabilities Summary

| Outcome           | Condition   | Approximate Probability |
| :---------------- | :---------- | :---------------------- |
| Large Branch      | `r < 0.005` | 0.5%                    |
| Small Branch      | `r < 0.2`   | 19.5%                   |
| Leaf Sprite       | `r < 0.5`   | 30%                     |
| (No spawn/other)  | `r >= 0.5`  | 50%                     |