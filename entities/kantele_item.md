---
title: Kantele Item
category: entities
---

# Kantele Item

This document details the `kantele.xml` entity, which defines the Kantele item in Noita. It functions as a unique wand with specific properties.

## Core Components

The Kantele is built upon several base entity files, inheriting their functionalities and then customizing them.

### Base Files

*   **`data/entities/base_item.xml`**: Provides fundamental item properties like sprite rendering and UI information.
*   **`data/entities/base_wand.xml`**: Grants the Kantele its wand-like behavior, including spell casting mechanics.
*   **`data/entities/base_wand_pickup.xml`**: Handles the pickup behavior of the item.

## Key Attributes and Elements

### SpriteComponent

Defines the visual appearance of the Kantele.

*   **`image_file`**: `data/items_gfx/kantele.xml` - Specifies the graphical assets for the Kantele.
*   **`offset_x`**: `1` - Horizontal offset for the sprite.
*   **`offset_y`**: `3.5` - Vertical offset for the sprite.

### ItemComponent

Manages item-specific behaviors and UI display.

*   **`item_name`**: `$item_kantele` - The internal name for the item, used for localization.
*   **`play_hover_animation`**: `1` - Enables a hover animation when the item is interacted with.
*   **`always_use_item_name_in_ui`**: `1` - Ensures the item's name is always displayed in the UI.

### AbilityComponent

This is the core component that defines the Kantele's unique wand capabilities.

*   **`sprite_file`**: `data/items_gfx/kantele.xml` - The sprite used for the ability's visual representation.
*   **`swim_propel_amount`**: `-30` - Affects player movement when swimming.
*   **`ui_name`**: `$item_kantele` - The name displayed in the UI for this ability.
*   **`cooldown_frames`**: `1` - Very short cooldown between uses.
*   **`reload_time_frames`**: `1` - Very short reload time.
*   **`use_gun_script`**: `1` - Indicates it uses a gun script for firing.
*   **`mana_charge_speed`**: `30` - How quickly mana recharges.
*   **`mana_max`**: `2` - The maximum mana capacity.

#### `gun_config`

Configures the spell deck behavior.

*   **`shuffle_deck_when_empty`**: `0` - The spell deck does not shuffle when empty.
*   **`deck_capacity`**: `20` - The maximum number of spells the Kantele can hold.

#### `gunaction_config`

Configures the firing action.

*   **`fire_rate_wait`**: `2` - The delay between firing spells.

### HotspotComponent

Defines a point for actions, typically the firing position.

*   **`offset.x`**: `10` - Horizontal offset for the hotspot.
*   **`offset.y`**: `-0.5` - Vertical offset for the hotspot.

### ManaReloaderComponent

Enables mana regeneration for the item.

*   **`_tags`**: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - Specifies when this component is active.