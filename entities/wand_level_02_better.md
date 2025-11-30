---
title: Wand Level 02 Better
category: entities
---

# Wand Level 02 Better

This document describes the `wand_level_02_better.xml` entity, which defines a specific type of wand in Noita. This wand is designed for rapid projectile firing.

## Core Components

This wand is built upon several base entity files and includes specific components to define its behavior and appearance.

### Base Files

*   **`data/entities/base_item.xml`**: Provides fundamental item properties like sprite rendering and hover animations.
*   **`data/entities/base_wand.xml`**: Inherits general wand functionalities.

### Key Components and Attributes

The `AbilityComponent` is central to defining the wand's unique characteristics.

#### `AbilityComponent`

This component governs the wand's magical capabilities.

*   **`ui_name`**: "Rapid bolt wand" - The name displayed in the game's UI.
*   **`sprite_file`**: `data/items_gfx/machinegun.xml` - Specifies the visual representation of the wand.
*   **`mana_max`**: `200` - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: `60` - How quickly the wand recharges mana.
*   **`max_amount_in_inventory`**: `1` - Only one of this wand can be held at a time.
*   **`drop_as_item_on_death`**: `1` - The wand will be dropped as an item if the player dies.
*   **`use_gun_script`**: `1` - Indicates that a custom script is used for its firing behavior.

#### `gun_config`

Configures the wand's projectile firing mechanics.

*   **`deck_capacity`**: `8` - The number of spells that can be held in the wand's "deck".
*   **`reload_time`**: `18` - The time in frames it takes to reload the wand after firing.
*   **`shuffle_deck_when_empty`**: `1` - The spell deck will be shuffled when it runs out of spells.
*   **`actions_per_round`**: `1` - The number of actions performed per firing cycle.

#### `gunaction_config`

Fine-tunes the timing of firing actions.

*   **`fire_rate_wait`**: `5` - The delay in frames between consecutive shots.

#### `HotspotComponent`

Defines the origin point for projectiles.

*   **`offset.x`**: `20` - The horizontal offset of the firing position.
*   **`offset.y`**: `0` - The vertical offset of the firing position.

#### `LuaComponent`

Links the wand to its custom scripting logic.

*   **`script_source_file`**: `data/scripts/gun/procedural/wand_level_02_better.lua` - The path to the Lua script that controls the wand's procedural generation and behavior.
*   **`execute_on_added`**: `1` - The script will run when the wand is added to the game.
*   **`remove_after_executed`**: `1` - The Lua component will be removed after its initial execution.

#### `ManaReloaderComponent`

Enables mana regeneration for the wand.

*   **`_tags`**: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - Specifies when the mana reloader is active.