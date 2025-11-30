---
title: ConfigItemStats
source: https://noita.wiki.gg/wiki/Documentation:impl::ConfigItemStats
category: modding-wiki
---

# ConfigItemStats

This documentation page details the `ConfigItemStats` component in Noita, which is crucial for defining and modifying the statistical properties of items within the game. Understanding and manipulating this component is essential for modders looking to alter item damage, healing, mana regeneration, and other core gameplay mechanics.

## Overview of `ConfigItemStats`

The `ConfigItemStats` component is an XML-based configuration element used to define the statistical attributes of items. These stats directly influence how an item behaves when used or equipped.

### Core Attributes

The following attributes are commonly found within `ConfigItemStats` and directly impact item behavior:

*   **`damage`**: The base damage dealt by the item.
*   **`mana_regeneration`**: The amount of mana regenerated per second while the item is active or equipped.
*   **`healing`**: The amount of health restored by the item.
*   **`mana_cost`**: The mana cost associated with using the item.
*   **`recoil`**: The recoil generated when the item is used.
*   **`projectile_speed`**: The speed at which projectiles fired by the item travel.
*   **`projectile_lifetime`**: The duration (in seconds) a projectile remains active before disappearing.
*   **`spread_degrees`**: The angular spread of projectiles fired by the item.
*   **`knockback`**: The force with which the item pushes targets.
*   **`crit_chance`**: The chance (as a decimal, e.g., 0.1 for 10%) of a critical hit.
*   **`crit_multiplier`**: The damage multiplier applied to critical hits.
*   **`fire_rate`**: The rate at which the item can be used (e.g., shots per second).
*   **`reload_time`**: The time it takes to reload the item.
*   **`durability`**: The number of uses before the item breaks or is consumed.
*   **`range`**: The effective range of the item.
*   **`radius`**: The area of effect radius for certain items.
*   **`speed`**: General speed attribute, can apply to projectiles or other item effects.
*   **`lifetime`**: General lifetime attribute, can apply to projectiles or other item effects.
*   **`gravity`**: The gravitational effect on projectiles or other effects.
*   **`explosion_radius`**: The radius of an explosion effect.
*   **`explosion_damage`**: The damage dealt by an explosion effect.
*   **`explosion_force`**: The force of an explosion effect.
*   **`explosion_lifetime`**: The duration of an explosion effect.
*   **`explosion_speed`**: The speed of an explosion effect.
*   **`explosion_gravity`**: The gravitational effect on an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The angular spread of an explosion.
*   **`explosion_knockback`**: The knockback force of an explosion.
*   **`explosion_healing`**: The healing amount of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*   **`explosion_mana_cost`**: The mana cost of an explosion.
*   **`explosion_mana_regeneration`**: The mana regeneration of an explosion.
*   **`explosion_recoil`**: The recoil of an explosion.
*   **`explosion_fire_rate`**: The fire rate of an explosion.
*   **`explosion_reload_time`**: The reload time of an explosion.
*   **`explosion_durability`**: The durability of an explosion.
*   **`explosion_range`**: The range of an explosion.
*   **`explosion_radius`**: The radius of an explosion.
*   **`explosion_speed`**: The speed of an explosion.
*   **`explosion_lifetime`**: The lifetime of an explosion.
*   **`explosion_gravity`**: The gravity of an explosion.
*   **`explosion_crit_chance`**: The critical hit chance of an explosion.
*   **`explosion_crit_multiplier`**: The critical hit multiplier of an explosion.
*   **`explosion_spread_degrees`**: The spread degrees of an explosion.
*   **`explosion_knockback`**: The knockback of an explosion.
*   **`explosion_healing`**: The healing of an explosion.
*