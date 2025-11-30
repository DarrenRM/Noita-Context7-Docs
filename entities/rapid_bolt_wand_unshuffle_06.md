---
title: Rapid Bolt Wand (Unshuffle 06)
category: entities
---

# Rapid Bolt Wand (Unshuffle 06)

This entity defines a specific type of wand in Noita, characterized by its rapid firing capability and a unique shuffling behavior for its spell deck.

## Core Components

### Base Item and Wand Configuration

The wand inherits fundamental properties from `base_item.xml` and `base_wand.xml`. Key attributes related to its item and wand behavior are defined within the `<AbilityComponent>` and its nested configurations.

### `<AbilityComponent>` Attributes

*   **`ui_name`**: "Rapid bolt wand" - The in-game name displayed to the player.
*   **`sprite_file`**: `data/items_gfx/machinegun.xml` - Specifies the visual representation of the wand.
*   **`mana_max`**: `500` - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: `120` - How quickly the wand recharges mana.
*   **`max_amount_in_inventory`**: `1` - The maximum number of this wand that can be held.
*   **`drop_as_item_on_death`**: `1` - The wand will be dropped as an item when the player dies.
*   **`use_gun_script`**: `1` - Indicates that this wand utilizes a custom script for its firing behavior.

### Gun Configuration (`<gun_config>`)

*   **`actions_per_round`**: `1` - The number of actions performed per firing cycle.
*   **`shuffle_deck_when_empty`**: `0` - The spell deck does *not* shuffle when it becomes empty. This is a key differentiator for this wand.
*   **`reload_time`**: `18` - The base time in frames to reload the wand.
*   **`deck_capacity`**: `8` - The maximum number of spells that can be held in the wand's deck.

### Gun Action Configuration (`<gunaction_config>`)

*   **`fire_rate_wait`**: `5` - The minimum delay in frames between consecutive shots. This contributes to its rapid firing nature.

### Scripting (`<LuaComponent>`)

*   **`script_source_file`**: `data/scripts/gun/procedural/wand_unshuffle_06.lua` - This is the primary script that governs the wand's unique firing mechanics, including its "unshuffle" behavior.
*   **`execute_on_added`**: `1` - The script executes immediately when the wand is added to the game.
*   **`remove_after_executed`**: `1` - The script is removed after its initial execution.

### Visual and Positioning (`<SpriteComponent>`, `<HotspotComponent>`)

*   **`<SpriteComponent>`**: `next_rect_animation="JobAbilityMachinegun"` - Defines sprite animations.
*   **`<HotspotComponent>`**: `offset.x="20"` - Defines the firing position offset from the wand's center.

### Mana Regeneration (`<ManaReloaderComponent>`)

*   This component enables the wand to regenerate mana over time, with tags indicating it functions in various game states (world, hand, inventory).