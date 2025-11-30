---
title: Test Wand Entity
category: entities
---

# Test Wand Entity

This document describes the `testwand.xml` entity, a debug wand designed for testing purposes in Noita.

## Entity Structure

The `testwand.xml` entity is composed of several key components that define its behavior and appearance.

### `AbilityComponent`

This is the core component that defines the wand's functionality as a usable item.

*   **`_enabled`**: `1` - The component is active.
*   **`amount_in_inventory`**: `1` - The wand starts with one charge.
*   **`cooldown_frames`**: `0` - No cooldown between uses.
*   **`drop_as_item_on_death`**: `1` - The wand will drop as an item if the player dies while holding it.
*   **`entity_count`**: `1` - Only one of this entity can exist at a time.
*   **`use_gun_script`**: `1` - Indicates that this wand uses a gun script for its behavior.
*   **`max_amount_in_inventory`**: `1` - The maximum number of this wand that can be held in inventory.
*   **`reload_time_frames`**: `0` - No reload time.
*   **`shooting_reduces_amount_in_inventory`**: `0` - Firing does not consume charges.
*   **`sprite_file`**: `data/items_gfx/disc_gun.xml` - The graphical representation of the wand.
*   **`ui_name`**: `Poison wand` - The name displayed in the user interface.
*   **`mana_charge_speed`**: `90000` - A very high mana charge speed, effectively making it instantly rechargeable.
*   **`item_recoil_recovery_speed`**: `15` - Controls how quickly the wand's recoil recovers.
*   **`mana_max`**: `900` - The maximum mana capacity of the wand.

#### `gun_config`

Defines the basic firing mechanics of the wand.

*   **`actions_per_round`**: `1` - Fires one projectile per action.
*   **`shuffle_deck_when_empty`**: `0` - The spell deck does not shuffle when empty.
*   **`reload_time`**: `1` - A very short reload time.
*   **`deck_capacity`**: `10` - The wand can hold up to 10 spells in its deck.

#### `gunaction_config`

Configures actions related to firing.

*   **`fire_rate_wait`**: `5` - A short delay between firing actions.

### `HotspotComponent`

Defines points of interaction or visual emphasis on the entity.

*   **`_tags`**: `shoot_pos` - This tag identifies the position from which projectiles are fired.
*   **`offset.x`**: `9` - Horizontal offset for the shoot position.
*   **`offset.y`**: `0` - Vertical offset for the shoot position.

### `Base` Component

Inherits base properties from `base_item.xml`.

#### `SpriteComponent`

Manages the visual aspects of the item.

*   **`next_rect_animation`**: `JobAbilityOpgun` - Specifies an animation to be used.

### `ManaReloaderComponent`

This component enables the wand to automatically reload mana.

*   **`_tags`**: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - The mana reloader is active in all these states.