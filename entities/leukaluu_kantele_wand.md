---
title: Leukaluu Kantele Wand
category: entities
---

# Leukaluu Kantele Wand

This document describes the `leukaluu_kantele.xml` entity, which defines a custom wand in Noita.

## Core Components

The Leukaluu Kantele is a wand with unique properties, primarily defined by its `AbilityComponent` and `VariableStorageComponent`.

### Sprite and Item Information

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/wands/custom/leukaluu_kantele.png` - Specifies the visual appearance of the wand.
    *   `offset_x`, `offset_y`: Adjust the sprite's position.
*   **`ItemComponent`**:
    *   `item_name`: `$item_leukaluu_kantele` - The internal name for the item.
    *   `play_hover_animation`: `1` - Enables a hover animation when the item is selected.
    *   `always_use_item_name_in_ui`: `1` - Ensures the item name is always displayed in the UI.
*   **`UIInfoComponent`**:
    *   `name`: `$item_leukaluu_kantele` - The name displayed in the game's user interface.

### Wand Mechanics (`AbilityComponent`)

This component defines the core functionality of the wand as a weapon.

*   **`sprite_file`**: `data/items_gfx/wands/custom/leukaluu_kantele.png` - The sprite used for the wand's ability.
*   **`swim_propel_amount`**: `-30` - Affects player movement when the wand is active.
*   **`cooldown_frames`**: `1` - Very short cooldown between shots.
*   **`reload_time_frames`**: `1` - Very fast reload.
*   **`use_gun_script`**: `1` - Indicates that this wand uses a gun script for its behavior.
*   **`mana_charge_speed`**: `100` - How quickly mana regenerates.
*   **`mana_max`**: `750` - The maximum mana capacity of the wand.
*   **`gun_config`**:
    *   `shuffle_deck_when_empty`: `0` - The spell deck does not shuffle when empty.
    *   `deck_capacity`: `20` - The wand can hold up to 20 spells.
*   **`gunaction_config`**:
    *   `fire_rate_wait`: `2` - A short delay between firing spells.

### Spell Configuration

*   **`VariableStorageComponent`**:
    *   `name`: `extra_spell`
    *   `value_string`: `SEA_SWAMP` - This is a key attribute. It indicates that the wand will add the `SEA_SWAMP` spell to its deck when it's created or picked up.
*   **`LuaComponent`**:
    *   `script_source_file`: `data/scripts/gun/procedural/wand_add_spells.lua` - This script is executed to add spells to the wand.
    *   `execute_on_added`: `1` - The script runs automatically when the entity is added to the game.
    *   `remove_after_executed`: `1` - The script is removed after it has run once.

### Other Components

*   **`SimplePhysicsComponent`**: `_enabled="0"` - Physics are disabled for this item.
*   **`HotspotComponent`**: Defines the `shoot_pos` for projectile origin.
*   **`ManaReloaderComponent`**: Enables mana regeneration for the wand.
*   **`Base file="data/entities/base_wand_pickup.xml"`**: Inherits pickup behavior for wands.

---