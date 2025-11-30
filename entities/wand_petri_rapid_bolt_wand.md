---
title: Wand Petri (Rapid Bolt Wand)
category: entities
---

---

# Wand Petri (Rapid Bolt Wand)

This document describes the `wand_petri.xml` entity, which defines a specific type of wand in Noita. This wand is characterized by its rapid firing capability and is intended for AI-assisted modding.

## Core Functionality

The `wand_petri.xml` entity inherits base functionality from `base_item.xml` and `base_wand.xml`. Its unique behavior is primarily driven by the `AbilityComponent` and a custom Lua script.

### Key Attributes in `AbilityComponent`

*   **`ui_name`**: "Rapid bolt wand" - The in-game name displayed to the player.
*   **`mana_max`**: `300` - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: `80` - The speed at which mana regenerates.
*   **`sprite_file`**: `data/items_gfx/machinegun.xml` - Specifies the visual representation of the wand.
*   **`use_gun_script`**: `1` - Indicates that the wand's behavior is controlled by a script.
*   **`drop_as_item_on_death`**: `1` - The wand will be dropped as an item when the player dies.
*   **`amount_in_inventory`**: `1` - The default quantity of this wand when found.
*   **`max_amount_in_inventory`**: `1` - The maximum quantity of this wand that can be held.

### Gun Configuration (`gun_config`)

*   **`deck_capacity`**: `8` - The number of spells that can be held in the wand's spell deck.
*   **`reload_time`**: `18` - The time in frames it takes to reload the wand.
*   **`actions_per_round`**: `1` - The number of actions performed per firing cycle.
*   **`shuffle_deck_when_empty`**: `0` - The spell deck does not shuffle when empty.

### Gun Action Configuration (`gunaction_config`)

*   **`fire_rate_wait`**: `5` - The delay in frames between consecutive shots.

## Scripting and Behavior

### `LuaComponent`

*   **`script_source_file`**: `data/scripts/gun/procedural/wand_petri.lua` - This is the core script that defines the wand's unique firing pattern and spell behavior. It's executed when the wand is added to the game.
*   **`execute_on_added`**: `1` - The script runs immediately upon the wand being added.
*   **`remove_after_executed`**: `1` - The script is removed after its initial execution.

### `HotspotComponent`

*   **`_tags`**: `"shoot_pos"` - Marks this component as the origin point for projectiles.
*   **`offset.x`**: `20` - The horizontal offset of the shooting position from the wand's center.
*   **`offset.y`**: `0` - The vertical offset of the shooting position from the wand's center.

## Visuals and Physics

### `SpriteComponent`

*   **`next_rect_animation`**: `"JobAbilityMachinegun"` - Refers to an animation state, likely related to the "machinegun" visual theme.

### `ItemComponent`

*   **`play_hover_animation`**: `1` - Enables a hovering animation when the item is in the inventory or on the ground.

### `SimplePhysicsComponent`

*   **`_enabled`**: `0` - Physics are disabled for this item, meaning it won't be affected by gravity or collisions in the same way as other physical objects.

## Mana Management

### `ManaReloaderComponent`

*   **`_tags`**: `"enabled_in_world,enabled_in_hand,enabled_in_inventory"` - This component ensures that mana regeneration is active regardless of whether the wand is in the world, in the player's hand, or in the inventory.