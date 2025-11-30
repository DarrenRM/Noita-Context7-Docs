---
title: Procedural Shotgun Generation
category: scripts
---

---

# Procedural Shotgun Generation

This script defines the logic for procedurally generating "shotgun" type weapons in Noita. It focuses on randomizing key gun properties to create unique variations each time.

## Core Generation Logic

The `generate_gun()` function is the main entry point. It retrieves the entity's ID and transform, then uses a random seed based on its position to ensure consistent generation for a given location. A rarity check (`is_rare`) is performed, influencing the potential for more powerful attributes.

## Key Gun Attributes

The script modifies several core attributes of the `AbilityComponent` for the gun:

*   **`actions_per_round`**: Determines how many projectile actions are performed per shot.
    *   Base: Typically 2.
    *   Rare: Can be 3 with a 33% chance.
*   **`reload_time`**: The time it takes for the gun to reload.
    *   Base: Ranges from 40 to 80.
    *   Rare: Reduced by 5-30 units.
*   **`shuffle_deck_when_empty`**: Controls whether the projectile deck is shuffled when depleted.
    *   Base: Usually enabled (1).
    *   Rare: Can be disabled (0) with a 33% chance.
*   **`deck_capacity`**: The number of projectile actions the gun can hold in its "deck".
    *   Base: Ranges from 1 to 5.
    *   Rare: Can be increased by 1-4 units.
    *   Constraint: If `shuffle_deck_when_empty` is 0, `deck_capacity` is capped at 6.

## Projectile Actions (Deck Configuration)

The script populates the gun's projectile deck with a combination of actions. The exact mix is determined by random rolls:

*   **Common Setup:**
    *   `SCATTER_3`
    *   `HEAVY_BULLET` (x2)
    *   `BULLET`
*   **Alternative Setup (10% chance):**
    *   `BURST_3`
    *   `HEAVY_BULLET` (x2)
    *   `BULLET`
*   **Additional Projectile (10% chance):**
    *   `BULLET`
*   **Rare Bonus:**
    *   `BURST_3` (added if `is_rare` is true)

## Naming and Visuals

*   **`ui_name`**: The name displayed in the UI.
    *   Rare guns are prefixed with "Legendary ".
    *   Non-rare guns can receive a random name from a predefined `gun_names` list (if available).
*   **Sprite**: The commented-out `SetItemSprite` line suggests that the gun's sprite is intended to be randomized from a set of shotgun-related graphics.
*   **Light Component**: For rare guns, the `LightComponent` is modified to have a purple glow (`r: 128, g: 0, b: 255`).