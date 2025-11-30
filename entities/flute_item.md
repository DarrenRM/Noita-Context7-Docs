---
title: Flute Item
category: entities
---

# Flute Item

This document details the configuration for the Flute item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Entity Structure

The Flute is built upon several base entity files, inheriting common functionalities.

-   **`base_item.xml`**: Provides fundamental item properties, including visual representation and basic interaction.
-   **`base_wand.xml`**: Inherits wand-like behavior, suggesting it can be used to cast spells or perform actions.
-   **`base_wand_pickup.xml`**: Handles the mechanics of picking up the item.

## Key Components and Attributes

### `SpriteComponent`

Defines the visual appearance of the Flute.

-   **`image_file`**: `data/items_gfx/flute.xml` - Specifies the graphical asset for the item.
-   **`offset_x`**: `1` - Horizontal offset for the sprite.
-   **`offset_y`**: `3.5` - Vertical offset for the sprite.

### `ItemComponent`

Configures item-specific behaviors and UI display.

-   **`item_name`**: `$item_ocarina` - The internal name for the item, likely used for localization.
-   **`play_hover_animation`**: `1` - Enables a hover animation when the item is interacted with.
-   **`always_use_item_name_in_ui`**: `1` - Ensures the item's name is consistently displayed in the UI.

### `AbilityComponent`

Manages the active abilities and spellcasting aspects of the Flute.

-   **`sprite_file`**: `data/items_gfx/flute.xml` - The sprite used when the ability is active.
-   **`swim_propel_amount`**: `-30` - Affects player movement when the ability is used, likely a slight push.
-   **`ui_name`**: `$item_ocarina` - The name displayed in the UI for this ability.
-   **`cooldown_frames`**: `1` - Minimal cooldown between uses.
-   **`reload_time_frames`**: `1` - Minimal reload time.
-   **`use_gun_script`**: `1` - Indicates that the item uses a script for its firing behavior.
-   **`mana_charge_speed`**: `30` - Speed at which mana is charged.
-   **`mana_max`**: `2` - Maximum mana capacity.

#### `gun_config`

Configuration for the wand-like firing mechanism.

-   **`shuffle_deck_when_empty`**: `0` - The spell deck does not shuffle when empty.
-   **`reload_time`**: `1` - Quick reload time.
-   **`deck_capacity`**: `20` - The maximum number of spells that can be held in the deck.

#### `gunaction_config`

Configuration for the action performed when firing.

-   **`fire_rate_wait`**: `2` - A short delay between firing actions.

### `HotspotComponent`

Defines a point for actions, typically for aiming or spawning projectiles.

-   **`offset.x`**: `10` - Horizontal offset for the hotspot.
-   **`offset.y`**: `-0.5` - Vertical offset for the hotspot.

### `ManaReloaderComponent`

Manages mana regeneration for the item.

-   **`_tags`**: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - The component is active in various states.

---