---
title: Starting Wand RNG Configuration
category: data/entities
---

# Starting Wand RNG Configuration

This document details the configuration for a starting wand entity in Noita, specifically focusing on its randomized properties and how it's generated.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

### Key Components

*   **`<AbilityComponent>`**: Defines the wand's core abilities and behavior.
    *   `amount_in_inventory`: The number of this item that can be held in the inventory. Set to `1`.
    *   `cooldown_frames`: Cooldown between shots. Set to `0` for immediate firing.
    *   `drop_as_item_on_death`: If the wand should drop as an item when the player dies. Set to `1` (true).
    *   `entity_count`: Number of entities spawned per shot. Set to `1`.
    *   `mana_charge_speed`: How quickly mana regenerates. Set to `30`.
    *   `mana_max`: Maximum mana capacity. Set to `100`.
    *   `max_amount_in_inventory`: Maximum stack size in inventory. Set to `1`.
    *   `reload_time_frames`: Time to reload the wand. Set to `0`.
    *   `sprite_file`: Path to the sprite used for the wand. Set to `"data/items_gfx/handgun.xml"`.
    *   `ui_name`: The name displayed in the UI. Set to `"Bolt staff"`.
    *   `use_gun_script`: Indicates if a gun script is used. Set to `1` (true).
    *   **`<gun_config>`**: Specific settings for the gun's behavior.
        *   `shuffle_deck_when_empty`: Whether to shuffle the spell deck when empty. Set to `0` (false).
        *   `reload_time`: Reload time in frames. Set to `24`.
        *   `deck_capacity`: Number of spells the wand can hold. Set to `3`.
    *   **`<gunaction_config>`**: Configuration for firing actions.
        *   `fire_rate_wait`: Delay between firing actions in frames. Set to `10`.

*   **`<HotspotComponent>`**: Defines points of interest on the entity, such as firing positions.
    *   `_tags`: Tags associated with the component. `"shoot_pos"` indicates a firing position.
    *   `offset.x`: X-axis offset for the hotspot. Set to `8`.
    *   `offset.y`: Y-axis offset for the hotspot. Set to `-0.5`.

*   **`<Base file="data/entities/base_item.xml">`**: Inherits properties from the base item definition.
    *   **`<ItemComponent>`**: Attributes related to the item's functionality.
        *   `item_name`: Internal name of the item. Set to `"default_gun"`.
        *   `remove_on_death`: Whether the item is removed on player death. Set to `1` (true).
        *   `collect_nondefault_actions`: If collecting this item triggers non-default actions. Set to `1` (true).
    *   **`<SpriteComponent>`**: Defines the visual representation of the item.
        *   `_tags`: Tags for sprite behavior. `"item,enabled_in_world,enabled_in_hand"` means it's visible in the world and when held.
        *   `image_file`: Path to the sprite image. Set to `"data/items_gfx/handgun.xml"`.
        *   `z_index`: Controls rendering order. Set to `-1.5`.

*   **`<Base file="data/entities/base_wand_pickup.xml">`**: Inherits properties from the base wand pickup definition.
    *   **`<LuaComponent _enabled="0">`**: A disabled Lua component, likely for specific pickup behaviors not used here.

*   **`<LuaComponent _enabled="1">`**: This component enables the procedural generation of the starting wand.
    *   `execute_on_added`: If the script should execute when the entity is added. Set to `1` (true).
    *   `remove_after_executed`: If the component should be removed after execution. Set to `1` (true).
    *   `script_source_file`: The path to the Lua script responsible for generating the wand's spells. Set to `"data/scripts/gun/procedural/starting_wand.lua"`.

*   **`<ManaReloaderComponent>`**: A component that allows the wand to passively reload mana.
    *   `_tags`: Tags indicating when this component is active. `"enabled_in_world,enabled_in_hand,enabled_in_inventory"` means it's active in all these states.