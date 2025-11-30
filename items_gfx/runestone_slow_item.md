---
title: Runestone Slow Item
category: data
---

# Runestone Slow Item

This document details the configuration for the "Runestone Slow" item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Item Properties

The `Runestone Slow` is a pickup item that grants a specific ability.

### `ItemComponent`

| Attribute        | Value                               | Description                                                                 |
| :--------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `item_name`      | `$item_runestone_slow`              | Internal name for the item, used for referencing and localization.          |
| `ui_sprite`      | `data/ui_gfx/items/runestone_slow.png` | Path to the sprite used in the UI inventory and item selection screens.     |
| `ui_description` | `$itemdesc_runestone`               | Localization key for the item's descriptive text in the UI.                 |

### `UIInfoComponent`

| Attribute | Value              | Description                               |
| :-------- | :----------------- | :---------------------------------------- |
| `name`    | `$item_runestone_slow` | The name displayed in the UI.             |

### `AbilityComponent`

| Attribute | Value              | Description                               |
| :-------- | :----------------- | :---------------------------------------- |
| `ui_name` | `$item_runestone_slow` | The name displayed for the ability in UI. |

## Visuals

### `PhysicsImageShapeComponent`

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file` | `data/items_gfx/runestones/runestone_slow.png` | The primary sprite for the item when it's a physical entity in the world. |

### `SpriteComponent`

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file` | `data/items_gfx/in_hand/runestone_slow.png` | The sprite used when the item is held by the player.                        |

## Functionality

### `LuaComponent` (Scripting)

This component links the item to its associated Lua script, which defines its in-game behavior.

| Attribute           | Value                                       | Description