---
title: Chest Randomization Script
category: scripts
---

---

# Chest Randomization Script

This script defines the behavior for random chests in Noita, determining what items they can contain and how they are spawned.

## Core Functions

### `make_random_card(x, y)`

*   **Purpose:** Creates a random spell card entity at the specified coordinates.
*   **Key Attributes:**
    *   Iterates through a list of available spell `actions`.
    *   Checks for `spawn_requires_flag` to ensure certain spells only appear after specific game events.
    *   Considers `spawn_probability` (though "0" is treated as invalid).
    *   Returns the created entity ID or prints an error if no valid action is found.

### `chest_load_gold_entity(entity_filename, x, y, remove_timer)`

*   **Purpose:** Loads a gold entity and adjusts its pickup behavior.
*   **Key Attributes:**
    *   Uses `load_gold_entity` to create the gold.
    *   If the gold has `auto_pickup` enabled, it sets `next_frame_pickable` to a future frame to prevent immediate collection.

### `drop_random_reward(x, y, entity_id, rand_x, rand_y, set_rnd)`

*   **Purpose:** The main function for determining and spawning random rewards from a chest.
*   **Key Attributes:**
    *   **Randomization:** Uses `SetRandomSeed` for deterministic spawning if `set_rnd` is true.
    *   **Item Categories & Probabilities:**
        *   **Bomb:** (7% chance) Spawns `bomb_small.xml`.
        *   **Gold:** (33% chance) Spawns various `goldnugget` entities with randomized amounts, influenced by the `perk_gold_is_forever` world state.
        *   **Potion:** (10% chance) Spawns `potion.xml`, `powder_stash.xml`, `potion_secret.xml`, or `potion_random_material.xml`.
        *   **Spell Refresh:** (4% chance) Spawns `spell_refresh.xml` or `shaman_wind.xml`.
        *   **Misc Items:** (6% chance) Spawns items like `safe_haven.xml`, `moon.xml`, `thunderstone.xml`, `evil_eye.xml`, `brimstone.xml`, or randomized `runestone.xml` and special orbs.
        *   **Random Card:** (5% chance) Spawns multiple spell cards using `make_random_card`.
        *   **Wand:** (18% chance) Spawns various levels of `wand_level` and `wand_unshuffle` wands.
        *   **Heart(s):** (10% chance) Spawns `heart.xml`, `dark_alchemist.xml`, `heart_better.xml`, or `heart_fullhp.xml`.
        *   **Convert to Gold:** (2% chance) Transforms the chest entity into gold material.
        *   **Exploding Dice:** (2% chance) Triggers `drop_random_reward` multiple times (2 or 3).
    *   **Deferred Loading:** Uses a table `entities` to store items to be loaded, preventing issues with `SetRandomSeed` calls within some entity loading processes.
    *   **Entity Placement:** Attempts to place entities at `rand_x`, `rand_y` and then applies a transform to the chest's position.

## Event Handlers

### `on_open(entity_item)`

*   **Purpose:** Called when a chest is opened, initiating the reward drop process.
*   **Key Attributes:**
    *   Retrieves the chest's position (`x`, `y`) and potential seed position (`rand_x`, `rand_y`).
    *   Sets the random seed based on these positions.
    *   Calls `drop_random_reward` to spawn items.
    *   Spawns a visual effect (`chest_effect.xml` or `chest_effect_bad.xml`) based on whether a "good" item was dropped.

### `item_pickup(entity_item, entity_who_picked, name)`

*   **Purpose:** Handles the event when a player picks up the chest entity itself.
*   **Key Attributes:**
    *   Calls `on_open` to trigger the chest's contents.
    *   Kills the chest entity after opening.

### `physics_body_modified(is_destroyed)`

*   **Purpose:** Handles the event when the chest is destroyed by physics.
*   **Key Attributes:**
    *   Calls `on_open` to trigger the chest's contents.
    *   Disables and kills the chest entity after opening.