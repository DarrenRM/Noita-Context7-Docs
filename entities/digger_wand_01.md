---
title: Digger Wand 01
category: entities
---

# Digger Wand 01

This document details the configuration for the "Digger Wand 01" entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Entity Definition

The core entity is defined with the tag `wand`, indicating its function as a magical weapon.

```xml
<Entity tags="wand">
    <!-- ... other components ... -->
</Entity>
```

## Ability Component

This component governs the wand's magical capabilities, including firing mechanics, mana, and visual representation.

### Key Attributes:

*   **`sprite_file`**: Specifies the visual sprite for the wand.
    *   `data/items_gfx/wands/custom/scepter_01.xml`
*   **`cooldown_frames`**: The number of frames between wand shots.
    *   `1`
*   **`mana_charge_speed`**: How quickly mana regenerates.
    *   `35`
*   **`mana_max`**: The maximum mana capacity of the wand.
    *   `140`
*   **`use_gun_script`**: Enables the use of a custom gun script for firing logic.
    *   `1`

### Gun Configuration (`gun_config`):

*   **`shuffle_deck_when_empty`**: Determines if the spell deck is shuffled when depleted.
    *   `0` (False)
*   **`reload_time`**: The time in seconds to reload the wand.
    *   `2`
*   **`deck_capacity`**: The number of spells the wand can hold.
    *   `12`

### Gun Action Configuration (`gunaction_config`):

*   **`fire_rate_wait`**: The wait time in frames between firing actions.
    *   `1`

```xml
<AbilityComponent
    _enabled="1"
    sprite_file="data/items_gfx/wands/custom/scepter_01.xml"
    swim_propel_amount="0"
    ui_name=""
    drop_as_item_on_death="0"
    cooldown_frames="1"
    entity_count="1"
    reload_time_frames="0"
    mana_charge_speed="35"
    mana_max="140"
    use_gun_script="1"
    >
    <gun_config
        shuffle_deck_when_empty="0"
        reload_time="2"
        deck_capacity="12" >
    </gun_config>
    <gunaction_config
        fire_rate_wait="1" >
    </gunaction_config>
</AbilityComponent>
```

## Hotspot Component

Defines the origin point for firing projectiles.

### Key Attributes:

*   **`offset.x`**: Horizontal offset from the wand's center.
    *   `17`
*   **`offset.y`**: Vertical offset from the wand's center.
    *   `-0.5`

```xml
<HotspotComponent
    _tags="shoot_pos"
    offset.x="17"
    offset.y="-0.5" >
</HotspotComponent>
```

## Base Item Component

Standard component for items, defining its name and behavior when picked up or dropped.

### Key Attributes:

*   **`item_name`**: The internal name of the item.
    *   `fire_wand`
*   **`remove_on_death`**: Whether the item is removed when the player dies.
    *   `1` (True)
*   **`collect_nondefault_actions`**: If true, allows collecting spells that are not part of the default wand setup.
    *   `1` (True)

```xml
<Base file="data/entities/base_item.xml" >
    <ItemComponent
        item_name="fire_wand"
        remove_on_death="1"
        collect_nondefault_actions="1" >
    </ItemComponent>
</Base>
```

## Lua Component (Setup Script)

This component executes a Lua script upon being added to the game, typically for initializing procedural elements or custom wand behavior.

### Key Attributes:

*   **`execute_on_added`**: If true, the script runs when the entity is added.
    *   `1` (True)
*   **`remove_after_executed`**: If true, the Lua component is removed after execution.
    *   `1` (True)
*   **`script_source_file`**: The path to the Lua script to be executed.
    *   `data/scripts/gun/procedural/digger_01_setup.lua`

```xml
<LuaComponent
    execute_on_added="1"
    remove_after_executed="1"
    script_source_file="data/scripts/gun/procedural/digger_01_setup.lua"
    >
</LuaComponent>
```

## Mana Reloader Component

This component enables the wand to automatically reload mana over time.

### Key Attributes:

*   **`_tags`**: Defines when the component is active.
    *   `enabled_in_world,enabled_in_hand,enabled_in_inventory`

```xml
<ManaReloaderComponent
    _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
</ManaReloaderComponent>
```