---
title: Experimental Wand 4
category: entities
---

# Experimental Wand 4

This document details the configuration for an experimental wand in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the wand is defined by the `<Entity>` tag, with the `wand` tag indicating its type.

```xml
<Entity tags="wand">
    <!-- ... other components ... -->
</Entity>
```

## Ability Component

This component governs the wand's core functionality, including mana, firing mechanics, and inventory behavior.

### Key Attributes:

*   **`mana_max`**: The maximum mana capacity of the wand.
    *   Value: `100`
*   **`mana_charge_speed`**: How quickly the wand recharges mana.
    *   Value: `100`
*   **`cooldown_frames`**: The cooldown between shots in frames.
    *   Value: `0` (No cooldown)
*   **`reload_time_frames`**: The time it takes to reload the wand in frames.
    *   Value: `0` (Instant reload)
*   **`amount_in_inventory`**: The default amount of this item found in the inventory.
    *   Value: `1`
*   **`max_amount_in_inventory`**: The maximum number of this item that can be held in the inventory.
    *   Value: `1`
*   **`drop_as_item_on_death`**: Whether the wand drops as an item when the player dies.
    *   Value: `1` (Drops)
*   **`ui_name`**: The internal name used for UI elements.
    *   Value: `experimental_wand_3` (Note: This seems to be a naming inconsistency with the file name)
*   **`sprite_file`**: Specifies the sprite used for the wand when it's an item.
    *   Value: `data/items_gfx/wands/custom/chainsaw.xml`

### Gun Config:

Defines the wand's spell-casting behavior.

*   **`deck_capacity`**: The number of spells the wand can hold.
    *   Value: `2`
*   **`shuffle_deck_when_empty`**: Whether the spell deck shuffles when empty.
    *   Value: `0` (Does not shuffle)

### Gun Action Config:

Controls the timing of firing actions.

*   **`fire_rate_wait`**: The delay between firing actions in frames.
    *   Value: `1`

```xml
    <AbilityComponent
        amount_in_inventory="1"
        cooldown_frames="0"
        drop_as_item_on_death="1"
        entity_count="1"
        entity_file=""
        fast_projectile="0"
		mana_charge_speed="100"
		mana_max="100"
        max_amount_in_inventory="1"
        reload_time_frames="0"
        shooting_reduces_amount_in_inventory="0"
        sprite_file="data/items_gfx/wands/custom/chainsaw.xml"
        swim_propel_amount="0"
        throw_as_item="0"
        ui_name="experimental_wand_3"
        use_gun_script="1"
        >
        <gun_config
            shuffle_deck_when_empty="0"
            reload_time="0"
            deck_capacity="2" >
        </gun_config>
        <gunaction_config
            fire_rate_wait="1" >
        </gunaction_config>
    </AbilityComponent>
```

## Hotspot Component

Defines the position from which projectiles are fired.

*   **`offset.x`**: Horizontal offset from the wand's center.
    *   Value: `8`
*   **`offset.y`**: Vertical offset from the wand's center.
    *   Value: `1`

```xml
    <HotspotComponent
        _tags="shoot_pos"
        offset.x="8"
        offset.y="1" >
    </HotspotComponent>
```

## Base Item Component

This component defines the item's properties and visual representation.

### Item Component:

*   **`item_name`**: The internal name for the item, often used for localization.
    *   Value: `$item_chainsaw`
*   **`play_hover_animation`**: Whether to play a hover animation when the item is in hand.
    *   Value: `1` (Plays animation)

### Sprite Component:

Determines the visual appearance of the wand in the game world and in hand.

*   **`image_file`**: The primary sprite file for the wand.
    *   Value: `data/items_gfx/wands/custom/actual_wand.xml`
*   **`z_index`**: Controls the rendering order.
    *   Value: `-1.5` (Renders behind most other world elements)

```xml
    <Base file="data/entities/base_item.xml" >
        <ItemComponent
            item_name="$item_chainsaw"
			play_hover_animation="1"
			>
        </ItemComponent>

		<SpriteComponent
			_tags="item,enabled_in_world,enabled_in_hand"
			alpha="1"
			image_file="data/items_gfx/wands/custom/actual_wand.xml"
			next_rect_animation="default"
			rect_animation="default"
			z_index="-1.5" >
		</SpriteComponent>

		<SimplePhysicsComponent
            _enabled="0">
        </SimplePhysicsComponent>
    </Base>
```

## Lua Component

This component links the wand entity to a custom Lua script that defines its unique behavior.

*   **`script_source_file`**: The path to the Lua script file.
    *   Value: `data/entities/items/wands/experimental/experimental_wand_4.lua`
*   **`execute_on_added`**: Whether the script should execute immediately when the entity is added.
    *   Value: `1` (Executes on add)
*   **`remove_after_executed`**: Whether the Lua component should be removed after its initial execution.
    *   Value: `1` (Removes after execution)

```xml
    <LuaComponent
        _enabled="1"
        execute_on_added="1"
        remove_after_executed="1"
        script_source_file="data/entities/items/wands/experimental/experimental_wand_4.lua"
	>
    </LuaComponent>
```

## Mana Reloader Component

This component enables the wand to automatically reload mana.

```xml
    <ManaReloaderComponent
        _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
    </ManaReloaderComponent>
```