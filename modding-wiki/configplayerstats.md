---
title: ConfigPlayerStats
source: https://noita.wiki.gg/wiki/Documentation:impl::ConfigPlayerStats
category: modding-wiki
---

# ConfigPlayerStats

This documentation page details the `ConfigPlayerStats` component in Noita, which is crucial for defining and modifying player statistics. Understanding this component allows modders to alter core player attributes like health, mana, stamina, and more, enabling significant gameplay changes and custom character builds.

## Overview of `ConfigPlayerStats`

The `ConfigPlayerStats` component is an entity component that holds and manages the player's fundamental statistics. These statistics are used throughout the game to determine player capabilities and limitations. Modifying these values directly impacts how the player interacts with the game world.

## Player Stat Definitions

The following table outlines common player statistics that can be configured. These are typically defined within the `ConfigPlayerStats` component.

| Stat Name | Description |
|---|---|
| `max_hp` | Maximum health points. |
| `hp` | Current health points. |
| `max_mana` | Maximum mana points. |
| `mana` | Current mana points. |
| `stamina` | Stamina for actions like sprinting or dodging. |
| `max_stamina` | Maximum stamina. |
| `mana_regeneration_rate` | How quickly mana regenerates. |
| `stamina_regeneration_rate` | How quickly stamina regenerates. |
| `damage_min` | Minimum damage dealt by the player. |
| `damage_max` | Maximum damage dealt by the player. |
| `knockback_resistance` | Resistance to being knocked back by attacks. |
| `movement_speed` | Base movement speed of the player. |
| `jump_height` | The height the player can jump. |
| `luck` | Player's luck stat, affecting various random outcomes. |
| `mana_charge_speed` | Speed at which mana charges for certain spells. |
| `fire_rate_multiplier` | Multiplier for the player's fire rate. |
| `projectile_speed_multiplier` | Multiplier for the speed of projectiles fired by the player. |
| `projectile_lifetime_multiplier` | Multiplier for the lifespan of projectiles. |
| `projectile_count_multiplier` | Multiplier for the number of projectiles fired. |
| `explosion_radius_multiplier` | Multiplier for the radius of explosions caused by the player. |
| `explosion_damage_multiplier` | Multiplier for the damage of explosions caused by the player. |
| `explosion_lifetime_multiplier` | Multiplier for the lifespan of explosions. |
| `explosion_force_multiplier` | Multiplier for the force of explosions. |
| `explosion_speed_multiplier` | Multiplier for the speed of explosions. |
| `explosion_count_multiplier` | Multiplier for the number of explosions. |
| `explosion_knockback_multiplier` | Multiplier for the knockback of explosions. |
| `explosion_pierce_multiplier` | Multiplier for the piercing ability of explosions. |
| `explosion_homing_multiplier` | Multiplier for the homing ability of explosions. |
| `explosion_gravity_multiplier` | Multiplier for the gravity effect on explosions. |
| `explosion_spread_multiplier` | Multiplier for the spread of explosions. |
| `explosion_delay_multiplier` | Multiplier for the delay of explosions. |
| `explosion_damage_type` | The damage type of explosions. |
| `explosion_material` | The material of explosions. |
| `explosion_effect` | The visual effect of explosions. |
| `explosion_sound` | The sound effect of explosions. |
| `explosion_particle_count` | The number of particles in explosions. |
| `explosion_particle_speed` | The speed of particles in explosions. |
| `explosion_particle_lifetime` | The lifespan of particles in explosions. |
| `explosion_particle_size` | The size of particles in explosions. |
| `explosion_particle_color` | The color of particles in explosions. |
| `explosion_particle_gravity` | The gravity effect on particles in explosions. |
| `explosion_particle_spread` | The spread of particles in explosions. |
| `explosion_particle_material` | The material of particles in explosions. |
| `explosion_particle_effect` | The visual effect of particles in explosions. |
| `explosion_particle_sound` | The sound effect of particles in explosions. |
| `explosion_particle_count_multiplier` | Multiplier for the number of particles in explosions. |
| `explosion_particle_speed_multiplier` | Multiplier for the speed of particles in explosions. |
| `explosion_particle_lifetime_multiplier` | Multiplier for the lifespan of particles in explosions. |
| `explosion_particle_size_multiplier` | Multiplier for the size of particles in explosions. |
| `explosion_particle_color_multiplier` | Multiplier for the color of particles in explosions. |
| `explosion_particle_gravity_multiplier` | Multiplier for the gravity effect on particles in explosions. |
| `explosion_particle_spread_multiplier` | Multiplier for the spread of particles in explosions. |
| `explosion_particle_material_multiplier` | Multiplier for the material of particles in explosions. |
| `explosion_particle_effect_multiplier` | Multiplier for the visual effect of particles in explosions. |
| `explosion_particle_sound_multiplier` | Multiplier for the sound effect of particles in explosions. |

## Modifying Player Stats

Player stats are typically modified by adding or modifying the `ConfigPlayerStats` component on the player entity. This can be done through various modding techniques, such as:

### Using Entity Factories

When creating custom entities or modifying existing ones, you can directly add or set the `ConfigPlayerStats` component.

**Example (XML):**

```xml
<Entity name="my_custom_player">
    <ConfigPlayerStats
        max_hp="200"
        hp="200"
        max_mana="100"
        mana="100"
        movement_speed="1.5"
    />
    <!-- Other components -->
</Entity>
```

### Using Lua Scripting

Lua scripts can dynamically modify entity components, including `ConfigPlayerStats`. This is useful for in-game effects or conditional stat changes.

**Example (Lua):**

```lua
-- Get the player entity
local player = Game.GetPlayer()

-- Get the ConfigPlayerStats component
local stats_component = player:GetComponent("ConfigPlayerStats")

if stats_component then
    -- Modify existing stats
    stats_component.max_hp = stats_component.max_hp * 1.2 -- Increase max HP by 20%
    stats_component.mana_regeneration_rate = stats_component.mana_regeneration_rate + 0.1 -- Increase mana regen

    -- Add new stats if they don't exist (though most common ones are pre-defined)
    -- For example, if you wanted to add a custom stat, you might need to ensure it's handled by the game logic.
    -- For standard stats, direct modification is usually sufficient.
end
```

## Important Considerations

*   **Component Existence:** Ensure the `ConfigPlayerStats` component exists on the player entity before attempting to modify it. If it doesn't, you might need to add it.
*   **Stat Ranges:** Be mindful of the intended ranges for certain stats. Extremely high or low values might lead to unexpected game behavior or crashes.
*   **Game Updates:** Game updates can sometimes alter component names, properties, or their behavior. Always test your mods thoroughly after game updates.
*   **Other Components:** Player stats are often influenced by other components and game systems (e.g., buffs, debuffs, equipment). Consider how your changes interact with these.

For more advanced modding techniques and a deeper understanding of Noita's entity system, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) and the [Entity Component System](https://noita.wiki.gg/wiki/Modding:_Entity_Component_System) documentation.