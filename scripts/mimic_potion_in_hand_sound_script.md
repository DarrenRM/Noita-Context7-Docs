---
title: Mimic Potion In Hand Sound Script
category: scripts
---

---

# Mimic Potion In Hand Sound Script

This script adds random sound effects to a mimic potion when it's held by an entity.

## Functionality

The script plays one of two sounds ("jump" or "damage/projectile") with a 1 in 4 chance for each sound, and an overall 1 in 4 chance for any sound to play.

## Key Attributes

*   **`entity_id`**: Retrieves the unique identifier of the entity holding the potion.
*   **`x`, `y`**: Gets the transform (position) of the entity.
*   **`SetRandomSeed(x, y)`**: Initializes the random number generator based on the entity's position to ensure consistent randomness for that specific entity.
*   **`Random(1, 4)`**: Generates a random integer between 1 and 4 (inclusive).
*   **`GameEntityPlaySound(entity_id, sound_name)`**: Plays a specified sound effect for the given entity.

## Sound Logic

The script uses nested `if` statements to determine which sound to play:

1.  **Outer `if ( Random(1,4) == 1)`**: This condition has a 1 in 4 chance of being true. If it's false, no sound is played.
2.  **Inner `if ( Random(1,4) == 1)`**: If the outer condition is true, this inner condition is checked.
    *   If true (1 in 4 chance), `GameEntityPlaySound(entity_id, "jump")` is called.
    *   If false (3 in 4 chance), `GameEntityPlaySound(entity_id, "damage/projectile")` is called.

This results in:
*   A 1/16 chance of playing "jump".
*   A 3/16 chance of playing "damage/projectile".
*   A 12/16 (3/4) chance of playing no sound.