---
title: Modding: Special Tags
source: https://noita.wiki.gg/wiki/Modding:_Special_tags
category: modding-wiki
---

# Modding: Special Tags

This page details "special" tags in Noita modding, which are specifically recognized by the game engine to trigger custom functionalities beyond simple categorization. Understanding these tags is crucial for implementing unique behaviors, interactions, and effects in your mods.

## Entity Tags

Entity tags are attributes applied to entities that grant them specific in-engine behaviors or properties.

| Tag | Description |
|---|---|
| `boss_centipede` | Plays `music/boss_arena/battle` when the entity is nearby. |
| `firemage` | Affects the behavior of `AnimalAIComponent`. Makes [Brimstone](https://noita.wiki.gg/wiki/Brimstone) neutral in player's hands. |
| `fish_attractor` | Attracts any entities with `AdvancedFishAIComponent`. |
| `gold_nugget` | Entity is attracted by `TelekinesisComponent`. Also attracted by the Attract Items perk (on Lua side, `data/scripts/perks/attract_items.lua`). |
| `miniboss` | Plays `music/miniboss/00` when the entity is nearby. |
| `necromancer_shop` | Plays `music/temple/necromancer_shop` when the entity is nearby. |
| `player_unit` | `IsPlayer()` returns true for this Entity. Gets more stains than other entities. This tag has many random things tied to it. |
| `polymorphable_NOT` | Makes the entity not polymorphable. |
| `teleportable_NOT` | Supposedly makes the entity not teleportable, but the in-engine code is complex. |
| `thundermage` | Affects the behavior of `AnimalAIComponent`. Makes [Thunder stone](https://noita.wiki.gg/wiki/Thunder_stone) neutral in player's hands. |
| `touchmagic_immunity` | Prevents [MagicConvertMaterialComponent](https://noita.wiki.gg/wiki/Documentation:_MagicConvertMaterialComponent) from affecting the entity. |
| `ui_use_raw_name` | Prevents the game from attempting to look up a translation string for the entity name, displaying the name as is. |
| `wand` | Forces the Entity's name to "$item\_wand" (a translation string). |
| `workshop` | If an entity with this tag also has a `HitboxComponent`, it allows wand editing in the area defined by that component. |
| `workshop_aabb` | Plays `music/temple/enter` when the entity is nearby. |
| `workshop_untouched` | When used with the `workshop` tag, will force open the player's inventory if no wands have been edited and the player walks into the hitbox. |

The following are additional entity tags referenced in-engine:

*   `drone`
*   `enemy`
*   `prey`
*   `effectable_prop`
*   `hiteffect_enabled`
*   `HAX_polymorph_death`
*   `prop`
*   `polymorphed`
*   `hittable`
*   `player_ragdoll`
*   `player_projectile`
*   `music_energy_100_near`
*   `music_energy_100`
*   `music_energy_050_near`
*   `music_energy_050`
*   `music_energy_000_near`
*   `music_energy_000`
*   `ending_sampo_spot_underground`
*   `ending_sampo_spot_mountain`
*   `coop_respawn`
*   `mortal`

## Component Tags

Component tags are attributes applied to components that modify their behavior or enable specific functionalities.

### State Toggles

*   `enabled_in_hand`, `enabled_in_world`, `enabled_in_inventory`
    *   These tags control the enabled/disabled status of a component. They require an `ItemComponent` to be present on the entity.
    *   These are useful for defining different sprites for a Wand's inventory icon, world model, etc.

### Shop Interactions

*   `shop_cost`
    *   Components with this tag are removed from the entity when it is picked up in a shop.

### Conditional Behavior

*   `fire`
    *   Used by `TorchComponent`. This tag will toggle the enabled/disabled status of all components tagged with `fire` based on the lit status of the torch.

The following are additional component tags referenced in-engine:

*   `item_identified`
*   `item_unidentified`
*   `item_unlocked`
*   `item_locked`
*   `not_enabled_in_wand`
*   `tablet`
*   `charge_indicator`
*   `turret_rotate_sound` (for `AudioLoopComponent`)
*   `sound_jetpack` (for `AudioLoopComponent`)
*   `sound_underwater` (for `AudioLoopComponent`)
*   `sound_suffocating` (for `AudioLoopComponent`)
*   `sound_damage_curse` (for `AudioLoopComponent`)
*   `sound_pick_gold_sand` (for `AudioLoopComponent`)
*   `sound_spray` (for `AudioLoopComponent`)
*   `sound_air_whoosh` (for `AudioLoopComponent`)
*   `sound_telekinesis_move` (for `AudioLoopComponent`)
*   `sound_telekinesis_hold` (for `AudioLoopComponent`)
*   `jetpack`
*   `ingestion`
*   `digger`
*   `no_hitbox`
*   `shield_ring`
*   `shield_hit`
*   `shoot_pos` (for `HotspotComponent`)
*   `crouch_sensor` (for `HotspotComponent`)
*   `hand` (for `HotspotComponent`)
*   `kick_pos` (for `HotspotComponent`)
*   `spray_pos` (for `HotspotComponent`)
*   `item_bg`
*   `fart`
*   `smoke`
*   `aiming_reticle`
*   `character`
*   `laser_sight`
*   `gun`
*   `health_bar`
*   `item`

See also: [Modding Basics § Tags](https://noita.wiki.gg/wiki/Modding:_Basics#Tags)