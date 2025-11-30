---
title: Starting Bomb Wand
category: entities
---

# Starting Bomb Wand

This document describes the configuration for the "Bomb wand" starting item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Entity Definition

The core entity definition for the Bomb wand.

```xml
<Entity tags="wand">
    <!-- ... other components ... -->
</Entity>
```

## AbilityComponent

This component governs the wand's magical abilities and firing mechanics.

### Key Attributes:

*   **`amount_in_inventory`**: The number of this item that can be held in the inventory.
    *   Value: `1`
*   **`cooldown_frames`**: The time in frames before the wand can be fired again.
    *   Value: `0` (Instantaneous cooldown)
*   **`drop_as_item_on_death`**: Whether the wand drops as an item when the player dies.
    *   Value: `1` (Drops on death)
*   **`entity_count`**: The number of entities spawned per shot.
    *   Value: `1`
*   **`mana_charge_speed`**: The speed at which mana is charged per frame.
    *   Value: `30`
*   **`mana_max`**: The maximum mana capacity of the wand.
    *   Value: `100`
*   **`max_amount_in_inventory`**: The maximum number of this item allowed in the inventory.
    *   Value: `1`
*   **`reload_time_frames`**: The time in frames to reload the wand's deck.
    *   Value: `0` (Instantaneous reload)
*   **`sprite_file`**: The sprite used for the wand when held.
    *   Value: `data/items_gfx/bomb_wand.xml`
*   **`ui_name`**: The name displayed in the user interface.
    *   Value: `Bomb wand`
*   **`use_gun_script`**: Indicates if the wand uses a gun script for its behavior.
    *   Value: `1`

### `gun_config`

Configuration for the wand's deck and reloading.

*   **`shuffle_deck_when_empty`**: Whether the spell deck shuffles when empty.
    *   Value: `0`
*   **`reload_time`**: The time in frames to reload the deck.
    *   Value: `24`
*   **`deck_capacity`**: The number of spells the wand can hold in its deck.
    *   Value: `3`

### `gunaction_config`

Configuration for the firing action.

*   **`fire_rate_wait`**: The delay in frames between shots.
    *   Value: `10`

## HotspotComponent

Defines the firing position relative to the wand sprite.

### Key Attributes:

*   **`offset.x`**: Horizontal offset of the shooting position.
    *   Value: `6`
*   **`offset.y`**: Vertical offset of the shooting position.
    *   Value: `-0.5`

## Base Components

These components define the item's fundamental properties and visual representation.

### `Base file="data/entities/base_item.xml"`

*   **`ItemComponent`**:
    *   **`item_name`**: Internal name of the item.
        *   Value: `bomb_wand`
    *   **`remove_on_death`**: Whether the item is removed when the player dies.
        *   Value: `1`
    *   **`collect_nondefault_actions`**: Whether collecting this item triggers non-default actions.
        *   Value: `1`
*   **`SpriteComponent`**: Defines the item's visual appearance.
    *   **`image_file`**: Path to the sprite image.
        *   Value: `data/items_gfx/bomb_wand.xml`

### `Base file="data/entities/base_wand_pickup.xml"`

This base is included but its `LuaComponent` is disabled, suggesting it's primarily for inheritance of pickup-related logic that isn't actively used here.

## LuaComponent

This component executes a Lua script to define the wand's procedural generation and behavior.

### Key Attributes:

*   **`execute_on_added`**: Whether the script should execute when the entity is added.
    *   Value: `1`
*   **`remove_after_executed`**: Whether the Lua component should be removed after execution.
    *   Value: `1`
*   **`script_source_file`**: The path to the Lua script file.
    *   Value: `data/scripts/gun/procedural/starting_bomb_wand.lua`

## ManaReloaderComponent

This component enables mana regeneration for the wand.

### Key Attributes:

*   **`_tags`**: Tags indicating when this component is active.
    *   Values: `enabled_in_world`, `enabled_in_hand`, `enabled_in_inventory`