---
title: Wand Good 1 - Procedural Generation
category: entities
---

---

# Wand Good 1 - Procedural Generation

This document details the procedural generation of a "Good Wand" entity in Noita, focusing on its key attributes and how they are randomized.

## Entity Configuration

This wand is procedurally generated, meaning its specific stats can vary each time it appears in the game.

### Core Wand Properties

*   **`name`**: A list of potential names for the wand. The game randomly selects one.
    *   Example: `{"Fast wand"}`
*   **`deck_capacity`**: The maximum number of spells the wand can hold.
    *   Value: `19`
*   **`actions_per_round`**: The number of spells that can be cast per action.
    *   Value: `1`
*   **`reload_time`**: The time it takes for the wand to reload after casting spells. This is randomized within a range.
    *   Range: `{0.5, 0.5}` (Note: The provided source has a typo, likely intended to be a range like `{0.3, 0.7}`)
*   **`shuffle_deck_when_empty`**: Determines if the wand shuffles its spell deck when it runs out of spells.
    *   Value: `0` (False)
*   **`fire_rate_wait`**: A negative value that influences how quickly the wand can fire.
    *   Value: `-20`
*   **`spread_degrees`**: The angular spread of the spells cast by the wand.
    *   Value: `0`
*   **`speed_multiplier`**: A multiplier applied to the speed of the spells cast.
    *   Value: `1.25`
*   **`mana_charge_speed`**: The speed at which the wand regenerates mana. Randomized within a range.
    *   Range: `{600, 700}`
*   **`mana_max`**: The maximum mana capacity of the wand. Randomized within a range.
    *   Range: `{800, 1000}`
*   **`actions`**: A list of possible spell actions that can be added to the wand's deck.
    *   Examples: `{"LASER", "HEAVY_BULLET", "SLOW_BULLET", "ROCKET", "LANCE"}`

### Procedural Generation Logic

The script utilizes helper functions to randomize certain attributes:

*   **`get_random_from(target)`**: Selects a single random element from a table.
*   **`get_random_between_range(target)`**: Selects a random integer between the first two elements of a table (min, max).

The script then applies these randomized values to the wand's components, such as `ui_name`, `reload_time`, `mana_charge_speed`, and `mana_max`.

### Spell Actions

The wand is configured to have one spell action added to its deck, randomly chosen from the `gun.actions` list.

*   **`action_count`**: `1`
*   **`gun_action`**: Randomly selected from `gun.actions`.

### Item Component

*   **`item_name`**: `$item_wand_good_1` (Internal identifier for the wand).
*   **`always_use_item_name_in_ui`**: `true` (Ensures the wand's name is always displayed in the UI).