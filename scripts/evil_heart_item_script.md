---
title: Evil Heart Item Script
category: scripts
---

---

# Evil Heart Item Script

This script defines the behavior of the "Evil Heart" item in Noita. When picked up, it increases the player's maximum HP, with a potential cap and visual/audio feedback.

## Key Functionality

### `item_pickup(entity_item, entity_who_picked, name)`

This function is called when the player picks up the Evil Heart item.

*   **`entity_item`**: The entity representing the Evil Heart item itself.
*   **`entity_who_picked`**: The entity of the player who picked up the item.
*   **`name`**: The internal name of the item (e.g., "data/entities/items/heart_evil.xml").

### Core Logic

1.  **Retrieve Components**: It accesses the `DamageModelComponent` and `VariableStorageComponent` of the player.
2.  **HP Calculation**:
    *   It reads the player's current `max_hp` and stores the original value in `max_hp_old`.
    *   It retrieves a global multiplier (`HEARTS_MORE_EXTRA_HP_MULTIPLIER`) which defaults to "1" if not found.
    *   The `max_hp` is increased by `2 * multiplier`.
3.  **HP Capping**:
    *   If the player has a `max_hp_cap` defined in their `DamageModelComponent` (and it's greater than 0), the `max_hp` is capped at this value using `math.min()`.
4.  **Component Updates**:
    *   The original `max_hp` is stored in `max_hp_old` within the `DamageModelComponent`.
    *   The new calculated `max_hp` is applied to the `DamageModelComponent`.
    *   `mLastMaxHpChangeFrame` is updated to the current game frame number.
5.  **Visual and Audio Feedback**:
    *   A particle effect (`heart_effect.xml`) is spawned at the item's location.
    *   A log message is printed to the player:
        *   If HP was increased, it uses `$logdesc_heart_evil` with the new HP value.
        *   If the HP increase was blocked by the cap, it uses `$logdesc_heart_blocked`.
    *   If the HP was successfully increased (not blocked by cap), a "poison_big.xml" effect is attached to the player.
    *   A music cue ("item") is triggered.
6.  **Item Removal**: The Evil Heart item entity is destroyed using `EntityKill()`.

## Key Attributes and Components

### `DamageModelComponent`

This component is crucial for managing the player's health.

| Attribute     | Description