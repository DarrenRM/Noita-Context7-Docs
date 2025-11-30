---
title: WormAIComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:WormAIComponent
category: modding-wiki
---

# WormAIComponent Documentation for AI-Assisted Modding

This document provides a comprehensive guide to the `WormAIComponent` in Noita, detailing its parameters and functionalities. Understanding this component is crucial for modders looking to customize or create new worm behaviors, influencing how these creatures navigate, interact with the environment, and pursue their targets.

## WormAIComponent Parameters

The `WormAIComponent` is a core component that dictates the artificial intelligence and movement patterns of worms in Noita. It is defined within the game's entity XML files.

### Core Parameters

| Parameter Name | Type | Description | Default Value |
|---|---|---|---|
| `worm_type` | String | Specifies the visual and behavioral variant of the worm. | `normal` |
| `speed` | Float | The movement speed of the worm. | `10.0` |
| `acceleration` | Float | How quickly the worm reaches its maximum speed. | `5.0` |
| `turn_speed` | Float | How quickly the worm can change direction. | `180.0` |
| `detection_radius` | Float | The distance at which the worm can detect targets. | `100.0` |
| `detection_angle` | Float | The angular field of view for target detection. | `360.0` |
| `target_tag` | String | The entity tag the worm will prioritize as a target. | `player` |
| `follow_target` | Boolean | If true, the worm will actively pursue the `target_tag`. | `true` |
| `avoid_obstacles` | Boolean | If true, the worm will attempt to navigate around solid objects. | `true` |
| `obstacle_avoidance_strength` | Float | The force applied to avoid obstacles. | `5.0` |
| `ground_following` | Boolean | If true, the worm will try to stay close to the ground. | `true` |
| `ground_following_strength` | Float | The force applied to maintain ground proximity. | `3.0` |
| `dig_speed` | Float | The speed at which the worm can dig through terrain. | `5.0` |
| `dig_material` | String | The material the worm can dig through. | `dirt` |
| `dig_sound` | String | The sound effect played when digging. | `event:/environment/dig_dirt` |
| `damage_on_contact` | Float | The amount of damage the worm inflicts on contact. | `5.0` |
| `contact_damage_type` | String | The type of damage inflicted on contact. | `PHYSICAL` |
| `contact_damage_material` | String | The material the worm's contact damage affects. | `organic` |
| `segment_length` | Float | The length of each segment of the worm's body. | `1.0` |
| `segment_count` | Integer | The number of segments the worm has. | `5` |
| `segment_offset` | Float | An offset applied to segment positioning. | `0.0` |
| `segment_gap` | Float | The gap between segments. | `0.0` |
| `segment_material` | String | The material of the worm's segments. | `worm` |
| `segment_color` | String | The color of the worm's segments (e.g., "255,0,0"). | `255,255,255` |
| `segment_sprite` | String | The sprite used for worm segments. | `data/entities/animals/worm/worm_segment.xml` |
| `head_sprite` | String | The sprite used for the worm's head. | `data/entities/animals/worm/worm_head.xml` |
| `tail_sprite` | String | The sprite used for the worm's tail. | `data/entities/animals/worm/worm_tail.xml` |
| `idle_animation` | String | The animation played when the worm is idle. | `idle` |
| `move_animation` | String | The animation played when the worm is moving. | `move` |
| `dig_animation` | String | The animation played when the worm is digging. | `dig` |
| `death_animation` | String | The animation played when the worm dies. | `death` |
| `spawn_on_death` | String | The entity to spawn when the worm dies. | `` |
| `spawn_on_death_count` | Integer | The number of entities to spawn on death. | `1` |
| `spawn_on_death_radius` | Float | The radius within which entities spawn on death. | `5.0` |
| `spawn_on_death_chance` | Float | The chance (0.0 to 1.0) of spawning entities on death. | `1.0` |
| `ai_script` | String | A custom Lua script to control AI behavior. | `` |
| `ai_script_parameters` | String | Parameters to pass to the custom AI script. | `` |

### Biome-Specific Parameters

Some parameters can be overridden or have different default values based on the biome the worm is spawned in.

| Parameter Name | Description | Biome Mappings |
|---|---|---|
| `speed` | Worm speed can be adjusted per biome. | See [Biome Mappings](#biome-mappings) |
| `dig_speed` | Worm digging speed can be adjusted per biome. | See [Biome Mappings](#biome-mappings) |
| `detection_radius` | Worm detection range can be adjusted per biome. | See [Biome Mappings](#biome-mappings) |
| `segment_material` | The material of the worm's segments can be biome-dependent. | See [Biome Mappings](#biome-mappings) |

#### Biome Mappings

This table shows how biome names map to internal identifiers used for biome-specific parameter adjustments.

| Biome Name | Internal ID |
|---|---|
| Coal Pits | `coal_pits` |
| Snowy Depths | `snowy_depths` |
| The Underground | `underground` |
| The Deep Underground | `deep_underground` |
| The Corruption | `corruption` |
| The Crimson | `crimson` |
| The Jungle | `jungle` |
| The Desert | `desert` |
| The Ocean | `ocean` |
| The Temple | `temple` |
| The Dungeon | `dungeon` |
| The Hell | `hell` |
| The Wandering Void | `wandering_void` |
| The Collapsed Sun | `collapsed_sun` |
| The World Below | `world_below` |
| The Great Forge | `great_forge` |
| The Crystal Caves | `crystal_caves` |
| The Fungus Caves | `fungus_caves` |
| The Toxic Sewers | `toxic_sewers` |
| The Mines | `mines` |
| The Forest | `forest` |
| The Swamp | `swamp` |
| The Lake | `lake` |
| The River | `river` |
| The Caverns | `caverns` |
| The Caves | `caves` |
| The Surface | `surface` |
| The Sky | `sky` |
| The Void | `void` |
| The Abyss | `abyss` |
| The Shadow Biome | `shadow_biome` |
| The Lumina Biome | `lumina_biome` |
| The Umbra Biome | `umbra_biome` |
| The Aether Biome | `aether_biome` |
| The Astral Biome | `astral_biome` |
| The Dream Biome | `dream_biome` |
| The Nightmare Biome | `nightmare_biome` |
| The Echo Biome | `echo_biome` |
| The Silence Biome | `silence_biome` |
| The Whispering Biome | `whispering_biome` |
| The Forgotten Biome | `forgotten_biome` |
| The Ancient Biome | `ancient_biome` |
| The Ruined Biome | `ruined_biome` |
| The Sunken Biome | `sunken_biome` |
| The Frozen Biome | `frozen_biome` |
| The Volcanic Biome | `volcanic_biome` |
| The Crystal Biome | `crystal_biome` |
| The Fungal Biome | `fungal_biome` |
| The Toxic Biome | `toxic_biome` |
| The Mining Biome | `mining_biome` |
| The Forest Biome | `forest_biome` |
| The Swamp Biome | `swamp_biome` |
| The Lake Biome | `lake_biome` |
| The River Biome | `river_biome` |
| The Cavern Biome | `cavern_biome` |
| The Cave Biome | `cave_biome` |
| The Surface Biome | `surface_biome` |
| The Sky Biome | `sky_biome` |
| The Void Biome | `void_biome` |
| The Abyss Biome | `abyss_biome` |

**Note:** The exact biome names and their corresponding internal IDs might vary slightly with game updates. It's always a good practice to cross-reference with the game's internal files if possible.

## Example Usage in Entity XML

Here's an example of how `WormAIComponent` might be used within an entity's XML definition:

```xml
<entity name="MyCustomWorm">
    <physics velocity_x="0" velocity_y="0" />
    <stats hp="50" />
    <sprite texture="data/entities/animals/worm/worm_head.png" />
    <components>
        <component name="WormAIComponent">
            <param name="speed" value="15.0" />
            <param name="acceleration" value="7.0" />
            <param name="turn_speed" value="200.0" />
            <param name="detection_radius" value="150.0" />
            <param name="target_tag" value="player" />
            <param name="avoid_obstacles" value="true" />
            <param name="dig_speed" value="7.0" />
            <param name="damage_on_contact" value="7.5" />
            <param name="segment_count" value="8" />
            <param name="segment_material" value="worm_special" />
            <param name="ai_script" value="data/scripts/ai/my_custom_worm_ai.lua" />
        </component>
    </components>
</entity>
```

## Custom AI Scripts

The `ai_script` parameter allows you to define custom Lua scripts that override or augment the default worm AI. This opens up possibilities for highly specialized worm behaviors.

### `ai_script` Parameter

- **Type:** String
- **Description:** Path to a Lua script file that will control the worm's AI.
- **Example:** `data/scripts/ai/my_custom_worm_ai.lua`

### `ai_script_parameters` Parameter

- **Type:** String
- **Description:** A string that can be parsed by your custom AI script to pass specific parameters or configurations. This is useful for making a single script adaptable to different worm types.
- **Example:** `{"aggression_level": 0.8, "preferred_target": "enemy_goblin"}`

### Accessing WormAIComponent Data in Lua

Within your custom AI script, you can access and modify the worm's AI parameters. The `self` object in the script context typically refers to the entity.

```lua
-- Example of a custom AI script (my_custom_worm_ai.lua)

local worm_ai = require("scripts/ai/worm_ai") -- Assuming a base worm AI library

function init(self)
    -- Access parameters passed via ai_script_parameters
    local params = self.entity.ai_script_parameters
    if params then
        self.aggression_level = params.aggression_level or 0.5
        self.preferred_target = params.preferred_target or "player"
    else
        self.aggression_level = 0.5
        self.preferred_target = "player"
    end

    -- Access and potentially modify default WormAIComponent parameters
    local worm_component = self.entity.get_component("WormAIComponent")
    if worm_component then
        self.original_speed = worm_component.speed
        worm_component.speed = self.original_speed * self.aggression_level
        print("Custom worm AI initialized. Speed adjusted to: " .. worm_component.speed)
    end
end

function update(self, dt)
    -- Implement custom AI logic here
    -- For example, finding and pursuing targets based on self.preferred_target
    -- You can use functions from the worm_ai library or Noita's Lua API
    -- Example: worm_ai.find_and_pursue_target(self.entity, self.preferred_target)
end

function on_death(self)
    -- Custom logic for when the worm dies
end
```

## Important Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure)
*   [Noita Modding Discord](https://discord.gg/noitamodding) (for community support and further questions)