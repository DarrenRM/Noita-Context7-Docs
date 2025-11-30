---
title: ManaReloaderComponent
source: https://noita.wiki.gg/wiki/Documentation:ManaReloaderComponent
category: modding-wiki
---

# ManaReloaderComponent

This documentation page explains the `ManaReloaderComponent` in Noita, a crucial component for modifying how mana regeneration works. Understanding this component is essential for modders who wish to alter or create custom mana-recharging items, spells, or effects.

## Overview

The `ManaReloaderComponent` is attached to entities in Noita to define their mana-recharging properties. It dictates how quickly and under what conditions an entity can restore the player's mana. This component is fundamental for creating custom items that provide mana regeneration, such as potions, wands with passive recharge, or even environmental effects.

## Component Properties

The `ManaReloaderComponent` has several properties that can be configured to customize its behavior. These properties are typically defined within an entity's XML definition.

### `mana_recharge_amount`

*   **Type:** float
*   **Description:** The amount of mana restored per recharge tick.
*   **Default:** `0.0`

### `mana_recharge_tick_interval`

*   **Type:** float
*   **Description:** The time in seconds between each mana recharge tick. A smaller value means faster recharging.
*   **Default:** `0.0`

### `mana_recharge_start_delay`

*   **Type:** float
*   **Description:** The delay in seconds before mana recharging begins after the component is activated.
*   **Default:** `0.0`

### `mana_recharge_while_casting`

*   **Type:** boolean
*   **Description:** If `true`, mana will recharge even while the player is actively casting a spell. If `false`, recharging pauses during casting.
*   **Default:** `false`

### `mana_recharge_while_moving`

*   **Type:** boolean
*   **Description:** If `true`, mana will recharge while the player is moving. If `false`, recharging pauses while moving.
*   **Default:** `false`

### `mana_recharge_while_standing_still`

*   **Type:** boolean
*   **Description:** If `true`, mana will recharge only when the player is standing still. If `false`, this condition is ignored.
*   **Default:** `false`

### `mana_recharge_only_when_empty`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player's mana is completely depleted.
*   **Default:** `false`

### `mana_recharge_only_when_full`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player's mana is completely full. This is an unusual condition and might be used for specific effects.
*   **Default:** `false`

### `mana_recharge_only_when_low`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player's mana is below a certain threshold (often implicitly defined by other game mechanics or a separate component).
*   **Default:** `false`

### `mana_recharge_only_when_high`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player's mana is above a certain threshold.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_alive`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge if the player character is alive.
*   **Default:** `true`

### `mana_recharge_only_when_player_is_dead`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge if the player character is dead. This is a highly unusual condition and likely not intended for standard gameplay.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_air`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in the air.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_on_ground`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is on the ground.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_water`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in water.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_not_in_water`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is not in water.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_fire`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in fire.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_not_in_fire`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is not in fire.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_poison`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in poison.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_not_in_poison`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is not in poison.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_acid`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in acid.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_not_in_acid`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is not in acid.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_magic_liquid`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is in a magic liquid (e.g., potion, slime).
*   **Default:** `false`

### `mana_recharge_only_when_player_is_not_in_magic_liquid`

*   **Type:** boolean
*   **Description:** If `true`, mana will only recharge when the player character is not in a magic liquid.
*   **Default:** `false`

### `mana_recharge_only_when_player_is_in_material`

*   **Type:** string
*   **Description:** If set to a material tag (e.g., `data/materials/water.material`), mana will only recharge when the player is in that specific material.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_not_in_material`

*   **Type:** string
*   **Description:** If set to a material tag, mana will only recharge when the player is *not* in that specific material.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_in_biome`

*   **Type:** string
*   **Description:** If set to a biome tag (e.g., `biomes/coal_pit.xml`), mana will only recharge when the player is in that biome.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_not_in_biome`

*   **Type:** string
*   **Description:** If set to a biome tag, mana will only recharge when the player is *not* in that biome.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_in_area`

*   **Type:** string
*   **Description:** If set to an area tag (e.g., `areas/boss_room.xml`), mana will only recharge when the player is in that area.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_not_in_area`

*   **Type:** string
*   **Description:** If set to an area tag, mana will only recharge when the player is *not* in that area.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_in_tag`

*   **Type:** string
*   **Description:** If set to a tag (e.g., `tag_boss`), mana will only recharge when the player is in an entity with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_is_not_in_tag`

*   **Type:** string
*   **Description:** If set to a tag, mana will only recharge when the player is *not* in an entity with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_tag`

*   **Type:** string
*   **Description:** If set to a tag, mana will only recharge when the player character has that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_tag`

*   **Type:** string
*   **Description:** If set to a tag, mana will only recharge when the player character does *not* have that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_item_tag`

*   **Type:** string
*   **Description:** If set to an item tag, mana will only recharge when the player is holding an item with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_item_tag`

*   **Type:** string
*   **Description:** If set to an item tag, mana will only recharge when the player is *not* holding an item with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_equipped_item_tag`

*   **Type:** string
*   **Description:** If set to an item tag, mana will only recharge when the player has an item with that tag equipped.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_equipped_item_tag`

*   **Type:** string
*   **Description:** If set to an item tag, mana will only recharge when the player does *not* have an item with that tag equipped.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_tag`

*   **Type:** string
*   **Description:** If set to a wand tag, mana will only recharge when the player is holding a wand with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_tag`

*   **Type:** string
*   **Description:** If set to a wand tag, mana will only recharge when the player is *not* holding a wand with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_tag`

*   **Type:** string
*   **Description:** If set to a spell tag, mana will only recharge when the player is holding a spell with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_tag`

*   **Type:** string
*   **Description:** If set to a spell tag, mana will only recharge when the player is *not* holding a spell with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_perk_tag`

*   **Type:** string
*   **Description:** If set to a perk tag, mana will only recharge when the player has that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_perk_tag`

*   **Type:** string
*   **Description:** If set to a perk tag, mana will only recharge when the player does *not* have that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_buff_tag`

*   **Type:** string
*   **Description:** If set to a buff tag, mana will only recharge when the player has that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_buff_tag`

*   **Type:** string
*   **Description:** If set to a buff tag, mana will only recharge when the player does *not* have that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_debuff_tag`

*   **Type:** string
*   **Description:** If set to a debuff tag, mana will only recharge when the player has that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_debuff_tag`

*   **Type:** string
*   **Description:** If set to a debuff tag, mana will only recharge when the player does *not* have that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_status_effect_tag`

*   **Type:** string
*   **Description:** If set to a status effect tag, mana will only recharge when the player has that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_status_effect_tag`

*   **Type:** string
*   **Description:** If set to a status effect tag, mana will only recharge when the player does *not* have that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_projectile_tag`

*   **Type:** string
*   **Description:** If set to a projectile tag, mana will only recharge when the player has fired a projectile with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_projectile_tag`

*   **Type:** string
*   **Description:** If set to a projectile tag, mana will only recharge when the player has *not* fired a projectile with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_explosion_tag`

*   **Type:** string
*   **Description:** If set to an explosion tag, mana will only recharge when the player has caused an explosion with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_explosion_tag`

*   **Type:** string
*   **Description:** If set to an explosion tag, mana will only recharge when the player has *not* caused an explosion with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_type_tag`

*   **Type:** string
*   **Description:** If set to a damage type tag, mana will only recharge when the player has dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_type_tag`

*   **Type:** string
*   **Description:** If set to a damage type tag, mana will only recharge when the player has *not* dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_modifier_tag`

*   **Type:** string
*   **Description:** If set to a damage modifier tag, mana will only recharge when the player has applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_modifier_tag`

*   **Type:** string
*   **Description:** If set to a damage modifier tag, mana will only recharge when the player has *not* applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_action_tag`

*   **Type:** string
*   **Description:** If set to a wand action tag, mana will only recharge when the player has performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_action_tag`

*   **Type:** string
*   **Description:** If set to a wand action tag, mana will only recharge when the player has *not* performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_action_tag`

*   **Type:** string
*   **Description:** If set to a spell action tag, mana will only recharge when the player has performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_action_tag`

*   **Type:** string
*   **Description:** If set to a spell action tag, mana will only recharge when the player has *not* performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_entity_tag`

*   **Type:** string
*   **Description:** If set to an entity tag, mana will only recharge when the player is near an entity with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_entity_tag`

*   **Type:** string
*   **Description:** If set to an entity tag, mana will only recharge when the player is *not* near an entity with that tag.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_item_type`

*   **Type:** string
*   **Description:** If set to an item type (e.g., `wand`, `spell`), mana will only recharge when the player is holding an item of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_item_type`

*   **Type:** string
*   **Description:** If set to an item type, mana will only recharge when the player is *not* holding an item of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_type`

*   **Type:** string
*   **Description:** If set to a wand type (e.g., `wand_basic`, `wand_advanced`), mana will only recharge when the player is holding a wand of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_type`

*   **Type:** string
*   **Description:** If set to a wand type, mana will only recharge when the player is *not* holding a wand of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_type`

*   **Type:** string
*   **Description:** If set to a spell type (e.g., `spell_damage`, `spell_utility`), mana will only recharge when the player is holding a spell of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_type`

*   **Type:** string
*   **Description:** If set to a spell type, mana will only recharge when the player is *not* holding a spell of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_perk_type`

*   **Type:** string
*   **Description:** If set to a perk type (e.g., `perk_damage`, `perk_utility`), mana will only recharge when the player has that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_perk_type`

*   **Type:** string
*   **Description:** If set to a perk type, mana will only recharge when the player does *not* have that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_buff_type`

*   **Type:** string
*   **Description:** If set to a buff type (e.g., `buff_speed`, `buff_strength`), mana will only recharge when the player has that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_buff_type`

*   **Type:** string
*   **Description:** If set to a buff type, mana will only recharge when the player does *not* have that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_debuff_type`

*   **Type:** string
*   **Description:** If set to a debuff type (e.g., `debuff_poison`, `debuff_slow`), mana will only recharge when the player has that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_debuff_type`

*   **Type:** string
*   **Description:** If set to a debuff type, mana will only recharge when the player does *not* have that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_status_effect_type`

*   **Type:** string
*   **Description:** If set to a status effect type (e.g., `status_burning`, `status_frozen`), mana will only recharge when the player has that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_status_effect_type`

*   **Type:** string
*   **Description:** If set to a status effect type, mana will only recharge when the player does *not* have that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_projectile_type`

*   **Type:** string
*   **Description:** If set to a projectile type (e.g., `projectile_fire`, `projectile_ice`), mana will only recharge when the player has fired a projectile of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_projectile_type`

*   **Type:** string
*   **Description:** If set to a projectile type, mana will only recharge when the player has *not* fired a projectile of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_explosion_type`

*   **Type:** string
*   **Description:** If set to an explosion type (e.g., `explosion_fire`, `explosion_ice`), mana will only recharge when the player has caused an explosion of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_explosion_type`

*   **Type:** string
*   **Description:** If set to an explosion type, mana will only recharge when the player has *not* caused an explosion of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_type`

*   **Type:** string
*   **Description:** If set to a damage type (e.g., `damage_fire`, `damage_ice`), mana will only recharge when the player has dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_type`

*   **Type:** string
*   **Description:** If set to a damage type, mana will only recharge when the player has *not* dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_modifier_type`

*   **Type:** string
*   **Description:** If set to a damage modifier type (e.g., `damage_modifier_piercing`), mana will only recharge when the player has applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_modifier_type`

*   **Type:** string
*   **Description:** If set to a damage modifier type, mana will only recharge when the player has *not* applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_action_type`

*   **Type:** string
*   **Description:** If set to a wand action type (e.g., `wand_action_cast`), mana will only recharge when the player has performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_action_type`

*   **Type:** string
*   **Description:** If set to a wand action type, mana will only recharge when the player has *not* performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_action_type`

*   **Type:** string
*   **Description:** If set to a spell action type (e.g., `spell_action_cast`), mana will only recharge when the player has performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_action_type`

*   **Type:** string
*   **Description:** If set to a spell action type, mana will only recharge when the player has *not* performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_entity_type`

*   **Type:** string
*   **Description:** If set to an entity type (e.g., `enemy`, `item`), mana will only recharge when the player is near an entity of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_entity_type`

*   **Type:** string
*   **Description:** If set to an entity type, mana will only recharge when the player is *not* near an entity of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_rarity`

*   **Type:** string
*   **Description:** If set to a wand rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player is holding a wand of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_rarity`

*   **Type:** string
*   **Description:** If set to a wand rarity, mana will only recharge when the player is *not* holding a wand of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_rarity`

*   **Type:** string
*   **Description:** If set to a spell rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player is holding a spell of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_rarity`

*   **Type:** string
*   **Description:** If set to a spell rarity, mana will only recharge when the player is *not* holding a spell of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_perk_rarity`

*   **Type:** string
*   **Description:** If set to a perk rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_perk_rarity`

*   **Type:** string
*   **Description:** If set to a perk rarity, mana will only recharge when the player does *not* have that perk.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_buff_rarity`

*   **Type:** string
*   **Description:** If set to a buff rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_buff_rarity`

*   **Type:** string
*   **Description:** If set to a buff rarity, mana will only recharge when the player does *not* have that buff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_debuff_rarity`

*   **Type:** string
*   **Description:** If set to a debuff rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_debuff_rarity`

*   **Type:** string
*   **Description:** If set to a debuff rarity, mana will only recharge when the player does *not* have that debuff active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_status_effect_rarity`

*   **Type:** string
*   **Description:** If set to a status effect rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_status_effect_rarity`

*   **Type:** string
*   **Description:** If set to a status effect rarity, mana will only recharge when the player does *not* have that status effect active.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_projectile_rarity`

*   **Type:** string
*   **Description:** If set to a projectile rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has fired a projectile of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_projectile_rarity`

*   **Type:** string
*   **Description:** If set to a projectile rarity, mana will only recharge when the player has *not* fired a projectile of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_explosion_rarity`

*   **Type:** string
*   **Description:** If set to an explosion rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has caused an explosion of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_explosion_rarity`

*   **Type:** string
*   **Description:** If set to an explosion rarity, mana will only recharge when the player has *not* caused an explosion of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_type_rarity`

*   **Type:** string
*   **Description:** If set to a damage type rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_type_rarity`

*   **Type:** string
*   **Description:** If set to a damage type rarity, mana will only recharge when the player has *not* dealt damage of that type.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_damage_modifier_rarity`

*   **Type:** string
*   **Description:** If set to a damage modifier rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_damage_modifier_rarity`

*   **Type:** string
*   **Description:** If set to a damage modifier rarity, mana will only recharge when the player has *not* applied that damage modifier.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_action_rarity`

*   **Type:** string
*   **Description:** If set to a wand action rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_wand_action_rarity`

*   **Type:** string
*   **Description:** If set to a wand action rarity, mana will only recharge when the player has *not* performed that wand action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_spell_action_rarity`

*   **Type:** string
*   **Description:** If set to a spell action rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player has performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_spell_action_rarity`

*   **Type:** string
*   **Description:** If set to a spell action rarity, mana will only recharge when the player has *not* performed that spell action.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_entity_rarity`

*   **Type:** string
*   **Description:** If set to an entity rarity (e.g., `common`, `uncommon`, `rare`), mana will only recharge when the player is near an entity of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_does_not_have_entity_rarity`

*   **Type:** string
*   **Description:** If set to an entity rarity, mana will only recharge when the player is *not* near an entity of that rarity.
*   **Default:** `""`

### `mana_recharge_only_when_player_has_wand_level`

*   **Type:** integer
*   **Description:** If set to a wand level (e.g., `1`, `2`, `3`), mana will only recharge when the player is holding a wand of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_wand_level`

*   **Type:** integer
*   **Description:** If set to a wand level, mana will only recharge when the player is *not* holding a wand of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_spell_level`

*   **Type:** integer
*   **Description:** If set to a spell level (e.g., `1`, `2`, `3`), mana will only recharge when the player is holding a spell of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_spell_level`

*   **Type:** integer
*   **Description:** If set to a spell level, mana will only recharge when the player is *not* holding a spell of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_perk_level`

*   **Type:** integer
*   **Description:** If set to a perk level (e.g., `1`, `2`, `3`), mana will only recharge when the player has that perk.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_perk_level`

*   **Type:** integer
*   **Description:** If set to a perk level, mana will only recharge when the player does *not* have that perk.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_buff_level`

*   **Type:** integer
*   **Description:** If set to a buff level (e.g., `1`, `2`, `3`), mana will only recharge when the player has that buff active.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_buff_level`

*   **Type:** integer
*   **Description:** If set to a buff level, mana will only recharge when the player does *not* have that buff active.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_debuff_level`

*   **Type:** integer
*   **Description:** If set to a debuff level (e.g., `1`, `2`, `3`), mana will only recharge when the player has that debuff active.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_debuff_level`

*   **Type:** integer
*   **Description:** If set to a debuff level, mana will only recharge when the player does *not* have that debuff active.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_status_effect_level`

*   **Type:** integer
*   **Description:** If set to a status effect level (e.g., `1`, `2`, `3`), mana will only recharge when the player has that status effect active.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_status_effect_level`

*   **Type:** integer
*   **Description:** If set to a status effect level, mana will only recharge when the player does *not* have that status effect active.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_projectile_level`

*   **Type:** integer
*   **Description:** If set to a projectile level (e.g., `1`, `2`, `3`), mana will only recharge when the player has fired a projectile of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_projectile_level`

*   **Type:** integer
*   **Description:** If set to a projectile level, mana will only recharge when the player has *not* fired a projectile of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_explosion_level`

*   **Type:** integer
*   **Description:** If set to an explosion level (e.g., `1`, `2`, `3`), mana will only recharge when the player has caused an explosion of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_explosion_level`

*   **Type:** integer
*   **Description:** If set to an explosion level, mana will only recharge when the player has *not* caused an explosion of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_damage_type_level`

*   **Type:** integer
*   **Description:** If set to a damage type level (e.g., `1`, `2`, `3`), mana will only recharge when the player has dealt damage of that type.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_damage_type_level`

*   **Type:** integer
*   **Description:** If set to a damage type level, mana will only recharge when the player has *not* dealt damage of that type.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_damage_modifier_level`

*   **Type:** integer
*   **Description:** If set to a damage modifier level (e.g., `1`, `2`, `3`), mana will only recharge when the player has applied that damage modifier.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_damage_modifier_level`

*   **Type:** integer
*   **Description:** If set to a damage modifier level, mana will only recharge when the player has *not* applied that damage modifier.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_wand_action_level`

*   **Type:** integer
*   **Description:** If set to a wand action level (e.g., `1`, `2`, `3`), mana will only recharge when the player has performed that wand action.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_wand_action_level`

*   **Type:** integer
*   **Description:** If set to a wand action level, mana will only recharge when the player has *not* performed that wand action.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_spell_action_level`

*   **Type:** integer
*   **Description:** If set to a spell action level (e.g., `1`, `2`, `3`), mana will only recharge when the player has performed that spell action.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_spell_action_level`

*   **Type:** integer
*   **Description:** If set to a spell action level, mana will only recharge when the player has *not* performed that spell action.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_entity_level`

*   **Type:** integer
*   **Description:** If set to an entity level (e.g., `1`, `2`, `3`), mana will only recharge when the player is near an entity of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_does_not_have_entity_level`

*   **Type:** integer
*   **Description:** If set to an entity level, mana will only recharge when the player is *not* near an entity of that level.
*   **Default:** `0`

### `mana_recharge_only_when_player_has_wand_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana cost, mana will only recharge when the player is holding a wand with that exact mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana cost, mana will only recharge when the player is holding a spell with that exact mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_recharge_time`

*   **Type:** integer
*   **Description:** If set to a recharge time, mana will only recharge when the player is holding a wand with that exact recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_recharge_time`

*   **Type:** integer
*   **Description:** If set to a recharge time, mana will only recharge when the player is *not* holding a wand with that exact recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_recharge_time`

*   **Type:** integer
*   **Description:** If set to a recharge time, mana will only recharge when the player is holding a spell with that exact recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_recharge_time`

*   **Type:** integer
*   **Description:** If set to a recharge time, mana will only recharge when the player is *not* holding a spell with that exact recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_uses`

*   **Type:** integer
*   **Description:** If set to a number of uses, mana will only recharge when the player is holding a wand with that exact number of uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_uses`

*   **Type:** integer
*   **Description:** If set to a number of uses, mana will only recharge when the player is *not* holding a wand with that exact number of uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_uses`

*   **Type:** integer
*   **Description:** If set to a number of uses, mana will only recharge when the player is holding a spell with that exact number of uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_uses`

*   **Type:** integer
*   **Description:** If set to a number of uses, mana will only recharge when the player is *not* holding a spell with that exact number of uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_speed`

*   **Type:** float
*   **Description:** If set to a speed value, mana will only recharge when the player is holding a wand with that exact speed.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_does_not_have_wand_speed`

*   **Type:** float
*   **Description:** If set to a speed value, mana will only recharge when the player is *not* holding a wand with that exact speed.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_has_spell_speed`

*   **Type:** float
*   **Description:** If set to a speed value, mana will only recharge when the player is holding a spell with that exact speed.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_does_not_have_spell_speed`

*   **Type:** float
*   **Description:** If set to a speed value, mana will only recharge when the player is *not* holding a spell with that exact speed.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_has_wand_damage`

*   **Type:** float
*   **Description:** If set to a damage value, mana will only recharge when the player is holding a wand with that exact damage.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_does_not_have_wand_damage`

*   **Type:** float
*   **Description:** If set to a damage value, mana will only recharge when the player is *not* holding a wand with that exact damage.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_has_spell_damage`

*   **Type:** float
*   **Description:** If set to a damage value, mana will only recharge when the player is holding a spell with that exact damage.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_does_not_have_spell_damage`

*   **Type:** float
*   **Description:** If set to a damage value, mana will only recharge when the player is *not* holding a spell with that exact damage.
*   **Default:** `-1.0`

### `mana_recharge_only_when_player_has_wand_mana_cost_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana cost per charge, mana will only recharge when the player is holding a wand with that exact mana cost per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_cost_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana cost per charge, mana will only recharge when the player is *not* holding a wand with that exact mana cost per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_cost_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana cost per charge, mana will only recharge when the player is holding a spell with that exact mana cost per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_cost_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana cost per charge, mana will only recharge when the player is *not* holding a spell with that exact mana cost per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_capacity`

*   **Type:** integer
*   **Description:** If set to a mana capacity, mana will only recharge when the player is holding a wand with that exact mana capacity.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_capacity`

*   **Type:** integer
*   **Description:** If set to a mana capacity, mana will only recharge when the player is *not* holding a wand with that exact mana capacity.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_capacity`

*   **Type:** integer
*   **Description:** If set to a mana capacity, mana will only recharge when the player is holding a spell with that exact mana capacity.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_capacity`

*   **Type:** integer
*   **Description:** If set to a mana capacity, mana will only recharge when the player is *not* holding a spell with that exact mana capacity.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana gain per charge, mana will only recharge when the player is holding a wand with that exact mana gain per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana gain per charge, mana will only recharge when the player is *not* holding a wand with that exact mana gain per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana gain per charge, mana will only recharge when the player is holding a spell with that exact mana gain per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_charge`

*   **Type:** integer
*   **Description:** If set to a mana gain per charge, mana will only recharge when the player is *not* holding a spell with that exact mana gain per charge.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_tick`

*   **Type:** integer
*   **Description:** If set to a mana gain per tick, mana will only recharge when the player is holding a wand with that exact mana gain per tick.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_tick`

*   **Type:** integer
*   **Description:** If set to a mana gain per tick, mana will only recharge when the player is *not* holding a wand with that exact mana gain per tick.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_tick`

*   **Type:** integer
*   **Description:** If set to a mana gain per tick, mana will only recharge when the player is holding a spell with that exact mana gain per tick.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_tick`

*   **Type:** integer
*   **Description:** If set to a mana gain per tick, mana will only recharge when the player is *not* holding a spell with that exact mana gain per tick.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_cast`

*   **Type:** integer
*   **Description:** If set to a mana gain per cast, mana will only recharge when the player is holding a wand with that exact mana gain per cast.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_cast`

*   **Type:** integer
*   **Description:** If set to a mana gain per cast, mana will only recharge when the player is *not* holding a wand with that exact mana gain per cast.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_cast`

*   **Type:** integer
*   **Description:** If set to a mana gain per cast, mana will only recharge when the player is holding a spell with that exact mana gain per cast.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_cast`

*   **Type:** integer
*   **Description:** If set to a mana gain per cast, mana will only recharge when the player is *not* holding a spell with that exact mana gain per cast.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_hit`

*   **Type:** integer
*   **Description:** If set to a mana gain per hit, mana will only recharge when the player is holding a wand with that exact mana gain per hit.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_hit`

*   **Type:** integer
*   **Description:** If set to a mana gain per hit, mana will only recharge when the player is *not* holding a wand with that exact mana gain per hit.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_hit`

*   **Type:** integer
*   **Description:** If set to a mana gain per hit, mana will only recharge when the player is holding a spell with that exact mana gain per hit.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_hit`

*   **Type:** integer
*   **Description:** If set to a mana gain per hit, mana will only recharge when the player is *not* holding a spell with that exact mana gain per hit.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_kill`

*   **Type:** integer
*   **Description:** If set to a mana gain per kill, mana will only recharge when the player is holding a wand with that exact mana gain per kill.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_kill`

*   **Type:** integer
*   **Description:** If set to a mana gain per kill, mana will only recharge when the player is *not* holding a wand with that exact mana gain per kill.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_kill`

*   **Type:** integer
*   **Description:** If set to a mana gain per kill, mana will only recharge when the player is holding a spell with that exact mana gain per kill.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_kill`

*   **Type:** integer
*   **Description:** If set to a mana gain per kill, mana will only recharge when the player is *not* holding a spell with that exact mana gain per kill.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is *not* holding a spell with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a wand with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_mana_cost`

*   **Type:** integer
*   **Description:** If set to a mana gain per mana cost, mana will only recharge when the player is *not* holding a spell with that exact mana gain per mana cost.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a wand with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_recharge_time`

*   **Type:** integer
*   **Description:** If set to a mana gain per recharge time, mana will only recharge when the player is *not* holding a spell with that exact mana gain per recharge time.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_when_player_has_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a wand with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_uses`

*   **Type:** integer
*   **Description:** If set to a mana gain per uses, mana will only recharge when the player is *not* holding a spell with that exact mana gain per uses.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a wand with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_spell_mana_gain_per_speed`

*   **Type:** integer
*   **Description:** If set to a mana gain per speed, mana will only recharge when the player is *not* holding a spell with that exact mana gain per speed.
*   **Default:** `-1`

### `mana_recharge_only_when_player_has_wand_mana_gain_per_damage`

*   **Type:** integer
*   **Description:** If set to a mana gain per damage, mana will only recharge when the player is holding a wand with that exact mana gain per damage.
*   **Default:** `-1`

### `mana_recharge_only_when_player_does_not_have_wand_mana_gain_per_damage`