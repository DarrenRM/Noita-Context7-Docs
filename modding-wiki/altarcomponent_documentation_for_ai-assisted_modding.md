---
title: AltarComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:AltarComponent
category: modding-wiki
---

# AltarComponent Documentation

This documentation covers the `AltarComponent` in Noita, a crucial element for creating and modifying altars within the game. Understanding this component is essential for modders looking to implement custom altar behaviors, rewards, or interactions, significantly enhancing the possibilities for new gameplay mechanics.

## Overview of AltarComponent

The `AltarComponent` is a fundamental part of Noita's entity system that defines the behavior and properties of altars. These entities are typically used for offering items or spells in exchange for something, often health or other resources. Modding this component allows for deep customization of these exchange mechanics.

## AltarComponent Properties

The `AltarComponent` has several properties that can be configured in an entity's XML definition. These properties control various aspects of the altar's functionality.

### Core Properties

| Property Name | Type | Description | Default Value |
| :------------ | :--- | :---------- | :------------ |
| `altar_type` | `string` | Defines the type of altar, influencing its base behavior and interactions. | `default` |
| `mana_cost` | `float` | The amount of mana required to activate the altar. | `0` |
| `mana_gain` | `float` | The amount of mana gained when the altar is successfully used. | `0` |
| `health_cost` | `float` | The amount of health required to activate the altar. | `0` |
| `health_gain` | `float` | The amount of health gained when the altar is successfully used. | `0` |
| `item_to_sacrifice` | `string` | The ID of the item that must be sacrificed to use the altar. | `none` |
| `item_to_gain` | `string` | The ID of the item that is gained upon successful use. | `none` |
| `spell_to_sacrifice` | `string` | The ID of the spell that must be sacrificed to use the altar. | `none` |
| `spell_to_gain` | `string` | The ID of the spell that is gained upon successful use. | `none` |
| `random_item_count` | `int` | The number of random items to grant from a predefined pool. | `0` |
| `random_spell_count` | `int` | The number of random spells to grant from a predefined pool. | `0` |
| `random_item_tags` | `string` | Comma-separated list of tags to filter random items. | `none` |
| `random_spell_tags` | `string` | Comma-separated list of tags to filter random spells. | `none` |
| `random_item_pool` | `string` | The ID of a custom item pool to draw random items from. | `none` |
| `random_spell_pool` | `string` | The ID of a custom spell pool to draw random spells from. | `none` |
| `use_sound_effect` | `string` | The name of the sound effect to play when the altar is used. | `none` |
| `fail_sound_effect` | `string` | The name of the sound effect to play when the altar fails to activate. | `none` |
| `success_visual_effect` | `string` | The name of the visual effect to play upon successful use. | `none` |
| `fail_visual_effect` | `string` | The name of the visual effect to play upon failure. | `none` |
| `recharge_time` | `float` | The time in seconds before the altar can be used again. | `0` |
| `max_uses` | `int` | The maximum number of times the altar can be used before it breaks or becomes inactive. | `-1` (infinite) |
| `is_unique` | `bool` | If true, the altar can only be used once per game session. | `false` |
| `requires_player_nearby` | `bool` | If true, the player must be within a certain range to activate the altar. | `true` |
| `player_proximity_radius` | `float` | The radius within which the player must be for `requires_player_nearby` to be true. | `50` |

### `altar_type` Specific Properties

Some `altar_type` values might introduce or modify specific behaviors. For example, a "sacrifice_altar" might have different default behaviors or require specific sacrifice mechanics.

*   **`sacrifice_altar`**: This type is often used for altars where a specific item or spell must be destroyed to gain a reward.
*   **`healing_altar`**: Primarily focused on restoring health, potentially with a mana cost.
*   **`mana_altar`**: Primarily focused on restoring mana, potentially with a health cost.

## Example XML Implementation

Here's an example of how to define an `AltarComponent` in an entity's XML file. This example creates a simple altar that sacrifices a "potion_healing_minor" to grant a "potion_healing_greater".

```xml
<entity name="my_custom_sacrifice_altar" tags="altar">
    <AltarComponent
        altar_type="sacrifice_altar"
        item_to_sacrifice="potion_healing_minor"
        item_to_gain="potion_healing_greater"
        mana_cost="50"
        health_cost="10"
        use_sound_effect="sounds/altar_use.wav"
        success_visual_effect="effects/altar_success.particle"
        recharge_time="30"
    />
    <Sprite sprite="sprites/altar_base.png" />
</entity>
```

## Using Lua with AltarComponent

While most altar configurations are done via XML, Lua scripting can be used to dynamically modify altar behavior, check conditions, or trigger custom events.

### Accessing AltarComponent in Lua

You can access the `AltarComponent` of an entity using its `GetComponent` method.

```lua
local entity_id = 12345 -- Replace with the actual entity ID
local altar_component = EntityGetFromId(entity_id):GetComponent("AltarComponent")

if altar_component then
    -- Access properties
    local altar_type = altar_component.altar_type
    print("Altar type: " .. altar_type)

    -- Modify properties (if allowed by the component's design)
    -- altar_component.mana_cost = 100 -- Example of modification
end
```

### Custom Altar Logic with Lua

You can attach Lua scripts to entities that contain an `AltarComponent` to implement more complex logic. This often involves using entity event hooks.

For instance, you might want to check if a player has a specific perk before allowing an altar to be used, or trigger a unique visual effect based on a random outcome.

```lua
-- Example: Custom logic for a unique altar
function MyCustomAltarLogic(entity, event)
    if event.type == "altar_use_attempt" then
        local player = event.player_entity
        if not player then return end

        -- Check if player has a specific perk
        if not PerkHas(player, "PERK_MY_UNIQUE_PERK") then
            print("You need a special perk to use this altar!")
            -- Prevent the altar use
            event.cancel = true
            return
        end

        -- Add custom reward logic
        if altar_component.item_to_gain == "some_default_item" then
            -- Grant a different, rarer item instead
            local custom_reward_item = "potion_super_healing"
            EntityAddItem(player, custom_reward_item)
            print("You received a rare potion!")
            event.cancel = true -- Cancel default reward to apply custom one
        end
    end
end

-- Attach this script to an entity with AltarComponent
-- You would typically do this by adding a <LuaComponent script_path="path/to/your/script.lua" /> to the entity XML.
```

## Important Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity System Documentation](https://noita.wiki.gg/wiki/Modding:_Entity_System)
*   [Component Documentation](https://noita.wiki.gg/wiki/Modding:_Components)