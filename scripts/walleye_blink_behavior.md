---
title: Walleye Blink Behavior
category: scripts
---

---

# Walleye Blink Behavior

This script defines a behavior for entities, specifically the "Walleye," that causes them to occasionally perform a blinking animation.

## Key Components and Logic

### Entity Initialization

-   **`entity_id`**: Retrieves the unique identifier for the entity being processed.
-   **`pos_x`, `pos_y`**: Gets the current position of the entity.
-   **`SetRandomSeed`**: Initializes the random number generator based on the entity's position and the current game frame to ensure consistent random behavior for a given entity state.
-   **`rnd = Random(0, 7)`**: Generates a random integer between 0 and 7 (inclusive).

### Velocity Reset

The script explicitly resets the velocity of the entity to zero, ensuring it remains stationary before potentially blinking.

-   **`edit_component( entity_id, "VelocityComponent", ...)`**: Targets the `VelocityComponent` and sets its `mVelocity` to `(0, 0)`.
-   **`edit_component( entity_id, "CharacterDataComponent", ...)`**: Targets the `CharacterDataComponent` and also sets its `mVelocity` to `(0, 0)`. This might be a redundant check or specific to how `CharacterDataComponent` handles movement.

### Blink Animation Trigger

-   **`if ( rnd == 5 ) then ... end`**: The blinking animation is triggered only if the generated random number `rnd` is exactly 5. This means there's a 1 in 8 chance (approximately 12.5%) of a blink occurring on any given frame where this script is active.
-   **`local sprite = EntityGetFirstComponent( entity_id, "SpriteComponent" )`**: Checks if the entity has a `SpriteComponent`. This is a prerequisite for playing animations.
-   **`if ( sprite ~= nil ) then ... end`**: If a `SpriteComponent` exists:
    -   **`GamePlayAnimation( entity_id, "blink", 0, "stand", 0 )`**: Plays the "blink" animation on the entity. The parameters `0, "stand", 0` likely control animation speed, transition states, or other animation-specific settings.