---
title: Wand Good 2
category: entities
---

# Wand Good 2

This document details the configuration for `wand_good_2.xml`, a wand entity in Noita.

## Entity Definition

The core entity is defined with tags indicating it's a wand and falls under the "good" category.

```xml
<Entity tags="wand,wand_good">
```

## Ability Component

This component governs the wand's magical capabilities.

### Key Attributes:

*   **`amount_in_inventory`**: The number of this wand that can be held in the inventory (default: 1).
*   **`cooldown_frames`**: Time in frames before the wand can be used again after firing (default: 0).
*   **`drop_as_item_on_death`**: If this wand should be dropped when the player dies (default: 1).
*   **`entity_count`**: Number of projectiles fired per shot (default: 1).
*   **`mana_charge_speed`**: How quickly mana regenerates (default: 30).
*   **`mana_max`**: Maximum mana capacity of the wand (default: 100).
*   **`max_amount_in_inventory`**: Maximum number of this wand that can be in the inventory (default: 1).
*   **`reload_time_frames`**: Time in frames to reload the wand (default: 0).
*   **`sprite_file`**: Path to the sprite used for the wand's visual representation.
*   **`ui_name`**: The name displayed in the user interface.
*   **`use_gun_script`**: Indicates if a custom gun script is used (default: 1).

### Gun Configuration:

*   **`shuffle_deck_when_empty`**: Whether the spell deck is shuffled when empty (default: 0).
*   **`reload_time`**: Time in seconds to reload the wand (default: 24).
*   **`deck_capacity`**: The number of spells the wand can hold (default: 3).

### Gun Action Configuration:

*   **`fire_rate_wait`**: Time in frames to wait between shots (default: 10).

```xml
    <AbilityComponent
        amount_in_inventory="1"
        cooldown_frames="0"
        drop_as_item_on_death="1"
        entity_count="1"
        fast_projectile="0"
		mana_charge_speed="30"
		mana_max="100"
        max_amount_in_inventory="1"
        reload_time_frames="0"
        shooting_reduces_amount_in_inventory="0"
        sprite_file="data/items_gfx/wands/custom/good_02.xml"
        swim_propel_amount="0"
        throw_as_item="0"
        ui_name="wand_good_2"
        use_gun_script="1"
        >
        <gun_config
            shuffle_deck_when_empty="0"
            reload_time="24"
            deck_capacity="3" >
        </gun_config>
        <gunaction_config
            fire_rate_wait="10" >
        </gunaction_config>
    </AbilityComponent>
```

## Hotspot Component

Defines the firing position for projectiles.

### Key Attributes:

*   **`offset.x`**: Horizontal offset from the wand's center.
*   **`offset.y`**: Vertical offset from the wand's center.

```xml
    <HotspotComponent
        _tags="shoot_pos"
        offset.x="15"
        offset.y="-0.5" >
    </HotspotComponent>
```

## Base Item Component

This section defines the fundamental properties of the item.

### Item Component:

*   **`item_name`**: Internal name of the item.
*   **`play_hover_animation`**: Whether to play a hover animation when the item is selected (default: 1).

### Sprite Component:

*   **`image_file`**: Path to the sprite image.
*   **`next_rect_animation`**: Name of the animation to play on the next frame.
*   **`rect_animation`**: Name of the current rectangle animation.
*   **`z_index`**: Determines the drawing order of the sprite.

```xml
    <Base file="data/entities/base_item.xml" >
        <ItemComponent
            item_name="wand_good_2"
			play_hover_animation="1"
			>
        </ItemComponent>

		<SpriteComponent
			_tags="item,enabled_in_world,enabled_in_hand"
			alpha="1"
			image_file="data/items_gfx/wands/custom/good_02.xml"
			next_rect_animation="default"
			rect_animation="default"
			z_index="-1.5" >
		</SpriteComponent>

		<SimplePhysicsComponent
            _enabled="0">
        </SimplePhysicsComponent>
    </Base>
```

## Lua Component (Main Script)

This component executes the primary wand logic via a Lua script.

### Key Attributes:

*   **`execute_on_added`**: If the script should run when the entity is added to the game.
*   **`remove_after_executed`**: If the Lua component should be removed after execution.
*   **`script_source_file`**: Path to the Lua script file.

```xml
    <LuaComponent
        _enabled="1"
        execute_on_added="1"
        remove_after_executed="1"
        script_source_file="data/entities/items/wands/wand_good/wand_good_2.lua"
	>
    </LuaComponent>
```

## Mana Reloader Component

This component handles the automatic reloading of mana for the wand.

```xml
    <ManaReloaderComponent
        _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
    </ManaReloaderComponent>
```

## Lua Component (Pickup Script)

This component executes a Lua script when the wand is picked up.

### Key Attributes:

*   **`script_item_picked_up`**: Path to the Lua script file to execute on pickup.
*   **`remove_after_executed`**: If the Lua component should be removed after execution.

```xml
	<LuaComponent
		script_item_picked_up="data/entities/items/wands/wand_good/wand_good_pickup.lua"
		remove_after_executed="1"
		>
	</LuaComponent>
```