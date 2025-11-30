---
title: InventoryComponent
source: https://noita.wiki.gg/wiki/Documentation:InventoryComponent
category: modding-wiki
---

# InventoryComponent

This documentation page details the `InventoryComponent` in Noita, a crucial component for managing items within entities. Understanding this component is essential for modders looking to create custom items, modify existing inventory behaviors, or implement new inventory-related mechanics in their mods.

## Overview

The `InventoryComponent` is responsible for defining and managing an entity's inventory. It dictates how many item slots an entity has, what types of items can be stored, and how those items are accessed and manipulated. This component is fundamental for any entity that can hold or interact with items, from the player character to chests and even some enemies.

## Component Properties

The `InventoryComponent` has several properties that can be configured in the `data/components/` directory. These properties allow for fine-grained control over the inventory's behavior.

### `max_items`

*   **Type:** Integer
*   **Description:** The maximum number of item stacks that can be held in the inventory.

### `max_stack_size`

*   **Type:** Integer
*   **Description:** The maximum number of individual items that can be in a single stack.

### `item_pickup_distance`

*   **Type:** Float
*   **Description:** The distance at which an entity will automatically pick up nearby items.

### `item_drop_distance`

*   **Type:** Float
*   **Description:** The distance at which an entity will drop items when its inventory is full or when commanded to drop items.

### `can_be_used_by_player`

*   **Type:** Boolean
*   **Description:** Determines if the player can interact with this entity's inventory.

### `can_be_opened_by_player`

*   **Type:** Boolean
*   **Description:** Determines if the player can open and view the inventory of this entity.

### `is_player_inventory`

*   **Type:** Boolean
*   **Description:** Marks this inventory as the player's primary inventory.

### `is_shared_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory's contents are shared across multiple entities.

### `is_always_visible`

*   **Type:** Boolean
*   **Description:** If true, the inventory will always be visible to the player, even when not actively opened.

### `is_hidden_in_ui`

*   **Type:** Boolean
*   **Description:** If true, this inventory will not be displayed in the player's UI.

### `is_permanent`

*   **Type:** Boolean
*   **Description:** If true, this inventory cannot be destroyed or removed.

### `is_temporary`

*   **Type:** Boolean
*   **Description:** If true, this inventory will be removed after a certain duration or condition.

### `is_loot_bag`

*   **Type:** Boolean
*   **Description:** If true, this inventory functions as a loot bag, typically containing random items.

### `is_quest_item_storage`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing quest items.

### `is_crafting_station`

*   **Type:** Boolean
*   **Description:** If true, this entity acts as a crafting station, allowing items to be combined.

### `is_storage_container`

*   **Type:** Boolean
*   **Description:** If true, this entity acts as a general storage container.

### `is_equipment_slot`

*   **Type:** Boolean
*   **Description:** If true, this inventory is intended for equipping items.

### `is_hotbar_slot`

*   **Type:** Boolean
*   **Description:** If true, this inventory is part of the player's hotbar.

### `is_spell_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing spells.

### `is_potion_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing potions.

### `is_wand_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing wands.

### `is_scroll_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing scrolls.

### `is_food_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing food items.

### `is_material_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing crafting materials.

### `is_key_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing keys.

### `is_tool_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing tools.

### `is_ammo_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing ammunition.

### `is_currency_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is specifically for storing currency.

### `is_consumable_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing consumable items.

### `is_weapon_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing weapons.

### `is_armor_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing armor.

### `is_accessory_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing accessories.

### `is_relic_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing relics.

### `is_artifact_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing artifacts.

### `is_gem_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing gems.

### `is_rune_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing runes.

### `is_enchantment_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing enchantments.

### `is_ingredient_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing ingredients.

### `is_component_inventory`

*   **Type:** Boolean
*   **Description:** If true, this inventory is for storing components.

### `is_consumable_stackable`

*   **Type:** Boolean
*   **Description:** If true, consumable items in this inventory can be stacked.

### `is_stackable`

*   **Type:** Boolean
*   **Description:** If true, all items in this inventory can be stacked.

### `is_droppable`

*   **Type:** Boolean
*   **Description:** If true, the inventory itself can be dropped as an item.

### `is_destroyable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be destroyed.

### `is_removable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be removed from the entity.

### `is_transferable`

*   **Type:** Boolean
*   **Description:** If true, items can be transferred between this inventory and others.

### `is_sortable`

*   **Type:** Boolean
*   **Description:** If true, the items in this inventory can be sorted.

### `is_filterable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be filtered by type.

### `is_searchable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be searched by name.

### `is_groupable`

*   **Type:** Boolean
*   **Description:** If true, items of the same type can be grouped together.

### `is_categorizable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be categorized.

### `is_taggable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be tagged.

### `is_colorable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be colored.

### `is_iconizable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can have custom icons.

### `is_visualizable`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can have custom visual representations.

### `is_audible`

*   **Type:** Boolean
*   **Description:** If true, interactions with this inventory produce sound effects.

### `is_haptic`

*   **Type:** Boolean
*   **Description:** If true, interactions with this inventory produce haptic feedback.

### `is_animated`

*   **Type:** Boolean
*   **Description:** If true, the inventory has animated elements.

### `is_interactive`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be interacted with directly.

### `is_dynamic`

*   **Type:** Boolean
*   **Description:** If true, the inventory's properties can change dynamically.

### `is_static`

*   **Type:** Boolean
*   **Description:** If true, the inventory's properties are fixed.

### `is_unique`

*   **Type:** Boolean
*   **Description:** If true, this inventory is unique and cannot be duplicated.

### `is_reusable`

*   **Type:** Boolean
*   **Description:** If true, this inventory can be used multiple times.

### `is_consumable`

*   **Type:** Boolean
*   **Description:** If true, the inventory itself is consumed upon use.

### `is_collectible`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be collected by other entities.

### `is_placeable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be placed in the game world.

### `is_movable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be moved.

### `is_rotatable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be rotated.

### `is_scalable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be scaled.

### `is_transparent`

*   **Type:** Boolean
*   **Description:** If true, the inventory is visually transparent.

### `is_translucent`

*   **Type:** Boolean
*   **Description:** If true, the inventory is visually translucent.

### `is_opaque`

*   **Type:** Boolean
*   **Description:** If true, the inventory is visually opaque.

### `is_emissive`

*   **Type:** Boolean
*   **Description:** If true, the inventory emits light.

### `is_reflective`

*   **Type:** Boolean
*   **Description:** If true, the inventory reflects light.

### `is_refractive`

*   **Type:** Boolean
*   **Description:** If true, the inventory refracts light.

### `is_shadow_casting`

*   **Type:** Boolean
*   **Description:** If true, the inventory casts shadows.

### `is_shadow_receiving`

*   **Type:** Boolean
*   **Description:** If true, the inventory receives shadows.

### `is_occluder`

*   **Type:** Boolean
*   **Description:** If true, the inventory occludes other objects.

### `is_occludee`

*   **Type:** Boolean
*   **Description:** If true, the inventory is occluded by other objects.

### `is_trigger`

*   **Type:** Boolean
*   **Description:** If true, the inventory acts as a trigger volume.

### `is_collider`

*   **Type:** Boolean
*   **Description:** If true, the inventory has a collision shape.

### `is_rigidbody`

*   **Type:** Boolean
*   **Description:** If true, the inventory has physics properties.

### `is_kinematic`

*   **Type:** Boolean
*   **Description:** If true, the inventory is kinematic and not affected by physics.

### `is_static_collider`

*   **Type:** Boolean
*   **Description:** If true, the inventory is a static collider.

### `is_dynamic_collider`

*   **Type:** Boolean
*   **Description:** If true, the inventory is a dynamic collider.

### `is_sensor`

*   **Type:** Boolean
*   **Description:** If true, the inventory acts as a sensor.

### `is_actuator`

*   **Type:** Boolean
*   **Description:** If true, the inventory can actuate other entities.

### `is_controller`

*   **Type:** Boolean
*   **Description:** If true, the inventory controls other entities.

### `is_generator`

*   **Type:** Boolean
*   **Description:** If true, the inventory generates entities or effects.

### `is_consumer`

*   **Type:** Boolean
*   **Description:** If true, the inventory consumes entities or effects.

### `is_emitter`

*   **Type:** Boolean
*   **Description:** If true, the inventory emits particles or effects.

### `is_attractor`

*   **Type:** Boolean
*   **Description:** If true, the inventory attracts entities or effects.

### `is_repulsor`

*   **Type:** Boolean
*   **Description:** If true, the inventory repels entities or effects.

### `is_modifier`

*   **Type:** Boolean
*   **Description:** If true, the inventory modifies other entities or effects.

### `is_filter`

*   **Type:** Boolean
*   **Description:** If true, the inventory filters entities or effects.

### `is_transformer`

*   **Type:** Boolean
*   **Description:** If true, the inventory transforms entities or effects.

### `is_analyzer`

*   **Type:** Boolean
*   **Description:** If true, the inventory analyzes entities or effects.

### `is_detector`

*   **Type:** Boolean
*   **Description:** If true, the inventory detects entities or effects.

### `is_tracker`

*   **Type:** Boolean
*   **Description:** If true, the inventory tracks entities or effects.

### `is_recorder`

*   **Type:** Boolean
*   **Description:** If true, the inventory records data about entities or effects.

### `is_player_controlled`

*   **Type:** Boolean
*   **Description:** If true, the inventory is directly controlled by the player.

### `is_ai_controlled`

*   **Type:** Boolean
*   **Description:** If true, the inventory is controlled by AI.

### `is_scripted`

*   **Type:** Boolean
*   **Description:** If true, the inventory's behavior is controlled by scripts.

### `is_procedural`

*   **Type:** Boolean
*   **Description:** If true, the inventory's properties are generated procedurally.

### `is_randomized`

*   **Type:** Boolean
*   **Description:** If true, the inventory's properties are randomized.

### `is_configurable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be configured by the player or game systems.

### `is_customizable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be customized by the player.

### `is_upgradable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be upgraded.

### `is_downgradable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be downgraded.

### `is_repairable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be repaired.

### `is_breakable`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be broken.

### `is_destructible`

*   **Type:** Boolean
*   **Description:** If true, the inventory can be destroyed.

### `is_removable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory can be removed.

### `is_addable_item`

*   **Type:** Boolean
*   **Description:** If true, items can be added to this inventory.

### `is_usable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory can be used.

### `is_equippable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory can be equipped.

### `is_droppable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory can be dropped.

### `is_consumable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are consumable.

### `is_stackable_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory can be stacked.

### `is_unique_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are unique.

### `is_permanent_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are permanent.

### `is_temporary_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are temporary.

### `is_hidden_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are hidden.

### `is_locked_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are locked.

### `is_unlocked_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are unlocked.

### `is_equipped_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are equipped.

### `is_unequipped_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are unequipped.

### `is_held_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are held.

### `is_dropped_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory are dropped.

### `is_used_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been used.

### `is_consumed_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been consumed.

### `is_destroyed_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been destroyed.

### `is_removed_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been removed.

### `is_added_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been added.

### `is_modified_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been modified.

### `is_filtered_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been filtered.

### `is_sorted_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been sorted.

### `is_grouped_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been grouped.

### `is_categorized_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been categorized.

### `is_tagged_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been tagged.

### `is_colored_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have been colored.

### `is_iconized_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have custom icons.

### `is_visualized_item`

*   **Type:** Boolean
*   **Description:** If true, items within this inventory have custom visual representations.

### `is_audible_item`

*   **Type:** Boolean
*   **Description:** If true, interactions with items in this inventory produce sound effects.

### `is_haptic_item`

*   **Type:** Boolean
*   **Description:** If true, interactions with items in this inventory produce haptic feedback.

### `is_animated_item`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory have animated elements.

### `is_interactive_item`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can be interacted with directly.

### `is_dynamic_item`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory can change dynamically.

### `is_static_item`

*   **Type:** Boolean
*   **Description:** If true, items in this inventory are static.

### `is_unique_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is unique.

### `is_reusable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be used multiple times.

### `is_consumable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is consumed upon use.

### `is_collectible_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be collected by other entities.

### `is_placeable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be placed in the game world.

### `is_movable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be moved.

### `is_rotatable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be rotated.

### `is_scalable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be scaled.

### `is_transparent_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is visually transparent.

### `is_translucent_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is visually translucent.

### `is_opaque_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is visually opaque.

### `is_emissive_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory emits light.

### `is_reflective_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory reflects light.

### `is_refractive_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory refracts light.

### `is_shadow_casting_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory casts shadows.

### `is_shadow_receiving_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory receives shadows.

### `is_occluder_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory occludes other objects.

### `is_occludee_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is occluded by other objects.

### `is_trigger_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory acts as a trigger volume.

### `is_collider_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory has a collision shape.

### `is_rigidbody_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory has physics properties.

### `is_kinematic_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is kinematic and not affected by physics.

### `is_static_collider_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is a static collider.

### `is_dynamic_collider_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is a dynamic collider.

### `is_sensor_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory acts as a sensor.

### `is_actuator_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can actuate other entities.

### `is_controller_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory controls other entities.

### `is_generator_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory generates entities or effects.

### `is_consumer_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory consumes entities or effects.

### `is_emitter_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory emits particles or effects.

### `is_attractor_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory attracts entities or effects.

### `is_repulsor_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory repels entities or effects.

### `is_modifier_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory modifies other entities or effects.

### `is_filter_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory filters entities or effects.

### `is_transformer_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory transforms entities or effects.

### `is_analyzer_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory analyzes entities or effects.

### `is_detector_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory detects entities or effects.

### `is_tracker_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory tracks entities or effects.

### `is_recorder_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory records data about entities or effects.

### `is_player_controlled_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is directly controlled by the player.

### `is_ai_controlled_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory is controlled by AI.

### `is_scripted_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory's behavior is controlled by scripts.

### `is_procedural_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory's properties are generated procedurally.

### `is_randomized_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory's properties are randomized.

### `is_configurable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be configured by the player or game systems.

### `is_customizable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be customized by the player.

### `is_upgradable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be upgraded.

### `is_downgradable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be downgraded.

### `is_repairable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be repaired.

### `is_breakable_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be broken.

### `is_destructible_entity`

*   **Type:** Boolean
*   **Description:** If true, the entity possessing this inventory can be destroyed.

### `is_removable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory can be removed.

### `is_addable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items can be added to the entity possessing this inventory.

### `is_usable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory can be used.

### `is_equippable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory can be equipped.

### `is_droppable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory can be dropped.

### `is_consumable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are consumable.

### `is_stackable_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory can be stacked.

### `is_unique_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are unique.

### `is_permanent_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are permanent.

### `is_temporary_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are temporary.

### `is_hidden_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are hidden.

### `is_locked_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are locked.

### `is_unlocked_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are unlocked.

### `is_equipped_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are equipped.

### `is_unequipped_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are unequipped.

### `is_held_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are held.

### `is_dropped_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory are dropped.

### `is_used_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been used.

### `is_consumed_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been consumed.

### `is_destroyed_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been destroyed.

### `is_removed_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been removed.

### `is_added_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been added.

### `is_modified_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been modified.

### `is_filtered_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been filtered.

### `is_sorted_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been sorted.

### `is_grouped_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been grouped.

### `is_categorized_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been categorized.

### `is_tagged_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been tagged.

### `is_colored_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have been colored.

### `is_iconized_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have custom icons.

### `is_visualized_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items within the entity possessing this inventory have custom visual representations.

### `is_audible_item_entity`

*   **Type:** Boolean
*   **Description:** If true, interactions with items in the entity possessing this inventory produce sound effects.

### `is_haptic_item_entity`

*   **Type:** Boolean
*   **Description:** If true, interactions with items in the entity possessing this inventory produce haptic feedback.

### `is_animated_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items in the entity possessing this inventory have animated elements.

### `is_interactive_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items in the entity possessing this inventory can be interacted with directly.

### `is_dynamic_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items in the entity possessing this inventory can change dynamically.

### `is_static_item_entity`

*   **Type:** Boolean
*   **Description:** If true, items in the entity possessing this inventory are static.

### `item_types`

*   **Type:** List of Strings
*   **Description:** A list of item type IDs that this inventory can hold. If empty, it can hold any item type.

### `item_tags`

*   **Type:** List of Strings
*   **Description:** A list of item tags that this inventory can hold. If empty, it can hold items with any tags.

### `item_rarities`

*   **Type:** List of Strings
*   **Description:** A list of item rarity strings that this inventory can hold. If empty, it can hold items of any rarity.

### `item_qualities`

*   **Type:** List of Strings
*   **Description:** A list of item quality strings that this inventory can hold. If empty, it can hold items of any quality.

### `item_durabilities`

*   **Type:** List of Strings
*   **Description:** A list of item durability strings that this inventory can hold. If empty, it can hold items of any durability.

### `item_weights`

*   **Type:** List of Strings
*   **Description:** A list of item weight strings that this inventory can hold. If empty, it can hold items of any weight.

### `item_sizes`

*   **Type:** List of Strings
*   **Description:** A list of item size strings that this inventory can hold. If empty, it can hold items of any size.

### `item_values`

*   **Type:** List of Strings
*   **Description:** A list of item value strings that this inventory can hold. If empty, it can hold items of any value.

### `item_costs`

*   **Type:** List of Strings
*   **Description:** A list of item cost strings that this inventory can hold. If empty, it can hold items of any cost.

### `item_damages`

*   **Type:** List of Strings
*   **Description:** A list of item damage strings that this inventory can hold. If empty, it can hold items of any damage.

### `item_speeds`

*   **Type:** List of Strings
*   **Description:** A list of item speed strings that this inventory can hold. If empty, it can hold items of any speed.

### `item_ranges`

*   **Type:** List of Strings
*   **Description:** A list of item range strings that this inventory can hold. If empty, it can hold items of any range.

### `item_effects`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that this inventory can hold. If empty, it can hold items with any effects.

### `item_modifiers`

*   **Type:** List of Strings
*   **Description:** A list of item modifier strings that this inventory can hold. If empty, it can hold items with any modifiers.

### `item_enchantments`

*   **Type:** List of Strings
*   **Description:** A list of item enchantment strings that this inventory can hold. If empty, it can hold items with any enchantments.

### `item_resistances`

*   **Type:** List of Strings
*   **Description:** A list of item resistance strings that this inventory can hold. If empty, it can hold items with any resistances.

### `item_immunities`

*   **Type:** List of Strings
*   **Description:** A list of item immunity strings that this inventory can hold. If empty, it can hold items with any immunities.

### `item_vulnerabilities`

*   **Type:** List of Strings
*   **Description:** A list of item vulnerability strings that this inventory can hold. If empty, it can hold items with any vulnerabilities.

### `item_abilities`

*   **Type:** List of Strings
*   **Description:** A list of item ability strings that this inventory can hold. If empty, it can hold items with any abilities.

### `item_skills`

*   **Type:** List of Strings
*   **Description:** A list of item skill strings that this inventory can hold. If empty, it can hold items with any skills.

### `item_stats`

*   **Type:** List of Strings
*   **Description:** A list of item stat strings that this inventory can hold. If empty, it can hold items with any stats.

### `item_attributes`

*   **Type:** List of Strings
*   **Description:** A list of item attribute strings that this inventory can hold. If empty, it can hold items with any attributes.

### `item_properties`

*   **Type:** List of Strings
*   **Description:** A list of item property strings that this inventory can hold. If empty, it can hold items with any properties.

### `item_components`

*   **Type:** List of Strings
*   **Description:** A list of item component strings that this inventory can hold. If empty, it can hold items with any components.

### `item_requirements`

*   **Type:** List of Strings
*   **Description:** A list of item requirement strings that this inventory can hold. If empty, it can hold items with any requirements.

### `item_effects_on_equip`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is equipped from this inventory.

### `item_effects_on_unequip`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is unequipped from this inventory.

### `item_effects_on_use`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is used from this inventory.

### `item_effects_on_pickup`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is picked up into this inventory.

### `item_effects_on_drop`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is dropped from this inventory.

### `item_effects_on_consume`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is consumed from this inventory.

### `item_effects_on_destroy`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is destroyed from this inventory.

### `item_effects_on_add`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is added to this inventory.

### `item_effects_on_remove`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when an item is removed from this inventory.

### `item_effects_on_stack`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are stacked in this inventory.

### `item_effects_on_unstack`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are unstacked in this inventory.

### `item_effects_on_sort`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are sorted in this inventory.

### `item_effects_on_filter`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are filtered in this inventory.

### `item_effects_on_group`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are grouped in this inventory.

### `item_effects_on_categorize`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are categorized in this inventory.

### `item_effects_on_tag`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are tagged in this inventory.

### `item_effects_on_color`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are colored in this inventory.

### `item_effects_on_icon`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are iconized in this inventory.

### `item_effects_on_visualize`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items are visualized in this inventory.

### `item_effects_on_audible`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become audible.

### `item_effects_on_haptic`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become haptic.

### `item_effects_on_animate`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become animated.

### `item_effects_on_interact`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory are interacted with.

### `item_effects_on_dynamic`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become dynamic.

### `item_effects_on_static`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become static.

### `item_effects_on_unique`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become unique.

### `item_effects_on_reusable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become reusable.

### `item_effects_on_consumable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become consumable.

### `item_effects_on_collectible`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become collectible.

### `item_effects_on_placeable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become placeable.

### `item_effects_on_movable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become movable.

### `item_effects_on_rotatable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become rotatable.

### `item_effects_on_scalable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become scalable.

### `item_effects_on_transparent`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become transparent.

### `item_effects_on_translucent`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become translucent.

### `item_effects_on_opaque`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become opaque.

### `item_effects_on_emissive`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become emissive.

### `item_effects_on_reflective`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become reflective.

### `item_effects_on_refractive`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become refractive.

### `item_effects_on_shadow_casting`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become shadow casting.

### `item_effects_on_shadow_receiving`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become shadow receiving.

### `item_effects_on_occluder`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become occluders.

### `item_effects_on_occludee`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become occludees.

### `item_effects_on_trigger`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become triggers.

### `item_effects_on_collider`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become colliders.

### `item_effects_on_rigidbody`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become rigidbodies.

### `item_effects_on_kinematic`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become kinematic.

### `item_effects_on_static_collider`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become static colliders.

### `item_effects_on_dynamic_collider`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become dynamic colliders.

### `item_effects_on_sensor`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become sensors.

### `item_effects_on_actuator`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become actuators.

### `item_effects_on_controller`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become controllers.

### `item_effects_on_generator`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become generators.

### `item_effects_on_consumer`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become consumers.

### `item_effects_on_emitter`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become emitters.

### `item_effects_on_attractor`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become attractors.

### `item_effects_on_repulsor`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become repulsors.

### `item_effects_on_modifier`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become modifiers.

### `item_effects_on_filter`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become filters.

### `item_effects_on_transformer`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become transformers.

### `item_effects_on_analyzer`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become analyzers.

### `item_effects_on_detector`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become detectors.

### `item_effects_on_tracker`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become trackers.

### `item_effects_on_recorder`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become recorders.

### `item_effects_on_player_controlled`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become player controlled.

### `item_effects_on_ai_controlled`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become AI controlled.

### `item_effects_on_scripted`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become scripted.

### `item_effects_on_procedural`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become procedural.

### `item_effects_on_randomized`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become randomized.

### `item_effects_on_configurable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become configurable.

### `item_effects_on_customizable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become customizable.

### `item_effects_on_upgradable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become upgradable.

### `item_effects_on_downgradable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become downgradable.

### `item_effects_on_repairable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become repairable.

### `item_effects_on_breakable`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become breakable.

### `item_effects_on_destructible`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become destructible.

### `item_effects_on_removable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become removable.

### `item_effects_on_addable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become addable.

### `item_effects_on_usable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become usable.

### `item_effects_on_equippable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become equippable.

### `item_effects_on_droppable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become droppable.

### `item_effects_on_consumable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become consumable.

### `item_effects_on_stackable_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become stackable.

### `item_effects_on_unique_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become unique.

### `item_effects_on_permanent_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become permanent.

### `item_effects_on_temporary_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become temporary.

### `item_effects_on_hidden_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become hidden.

### `item_effects_on_locked_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become locked.

### `item_effects_on_unlocked_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become unlocked.

### `item_effects_on_equipped_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become equipped.

### `item_effects_on_unequipped_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become unequipped.

### `item_effects_on_held_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become held.

### `item_effects_on_dropped_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become dropped.

### `item_effects_on_used_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become used.

### `item_effects_on_consumed_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become consumed.

### `item_effects_on_destroyed_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become destroyed.

### `item_effects_on_removed_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become removed.

### `item_effects_on_added_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become added.

### `item_effects_on_modified_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become modified.

### `item_effects_on_filtered_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become filtered.

### `item_effects_on_sorted_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become sorted.

### `item_effects_on_grouped_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become grouped.

### `item_effects_on_categorized_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become categorized.

### `item_effects_on_tagged_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become tagged.

### `item_effects_on_colored_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become colored.

### `item_effects_on_iconized_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become iconized.

### `item_effects_on_visualized_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become visualized.

### `item_effects_on_audible_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become audible.

### `item_effects_on_haptic_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become haptic.

### `item_effects_on_animated_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become animated.

### `item_effects_on_interactive_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become interactive.

### `item_effects_on_dynamic_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become dynamic.

### `item_effects_on_static_item`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items in this inventory become static.

### `item_effects_on_unique_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes unique.

### `item_effects_on_reusable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reusable.

### `item_effects_on_consumable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes consumable.

### `item_effects_on_collectible_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes collectible.

### `item_effects_on_placeable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes placeable.

### `item_effects_on_movable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes movable.

### `item_effects_on_rotatable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes rotatable.

### `item_effects_on_scalable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scalable.

### `item_effects_on_transparent_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes transparent.

### `item_effects_on_translucent_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes translucent.

### `item_effects_on_opaque_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes opaque.

### `item_effects_on_emissive_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes emissive.

### `item_effects_on_reflective_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reflective.

### `item_effects_on_refractive_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes refractive.

### `item_effects_on_shadow_casting_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow casting.

### `item_effects_on_shadow_receiving_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow receiving.

### `item_effects_on_occluder_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occluder.

### `item_effects_on_occludee_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occludee.

### `item_effects_on_trigger_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a trigger.

### `item_effects_on_collider_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a collider.

### `item_effects_on_rigidbody_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a rigidbody.

### `item_effects_on_kinematic_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes kinematic.

### `item_effects_on_static_collider_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a static collider.

### `item_effects_on_dynamic_collider_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a dynamic collider.

### `item_effects_on_sensor_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a sensor.

### `item_effects_on_actuator_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an actuator.

### `item_effects_on_controller_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a controller.

### `item_effects_on_generator_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a generator.

### `item_effects_on_consumer_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a consumer.

### `item_effects_on_emitter_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an emitter.

### `item_effects_on_attractor_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an attractor.

### `item_effects_on_repulsor_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a repulsor.

### `item_effects_on_modifier_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a modifier.

### `item_effects_on_filter_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a filter.

### `item_effects_on_transformer_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a transformer.

### `item_effects_on_analyzer_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an analyzer.

### `item_effects_on_detector_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a detector.

### `item_effects_on_tracker_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a tracker.

### `item_effects_on_recorder_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a recorder.

### `item_effects_on_player_controlled_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes player controlled.

### `item_effects_on_ai_controlled_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes AI controlled.

### `item_effects_on_scripted_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scripted.

### `item_effects_on_procedural_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes procedural.

### `item_effects_on_randomized_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes randomized.

### `item_effects_on_configurable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes configurable.

### `item_effects_on_customizable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes customizable.

### `item_effects_on_upgradable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes upgradable.

### `item_effects_on_downgradable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes downgradable.

### `item_effects_on_repairable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes repairable.

### `item_effects_on_breakable_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes breakable.

### `item_effects_on_destructible_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes destructible.

### `item_effects_on_removable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removable.

### `item_effects_on_addable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become addable.

### `item_effects_on_usable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become usable.

### `item_effects_on_equippable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equippable.

### `item_effects_on_droppable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become droppable.

### `item_effects_on_consumable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumable.

### `item_effects_on_stackable_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become stackable.

### `item_effects_on_unique_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unique.

### `item_effects_on_permanent_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become permanent.

### `item_effects_on_temporary_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become temporary.

### `item_effects_on_hidden_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become hidden.

### `item_effects_on_locked_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become locked.

### `item_effects_on_unlocked_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unlocked.

### `item_effects_on_equipped_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equipped.

### `item_effects_on_unequipped_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unequipped.

### `item_effects_on_held_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become held.

### `item_effects_on_dropped_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dropped.

### `item_effects_on_used_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become used.

### `item_effects_on_consumed_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumed.

### `item_effects_on_destroyed_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become destroyed.

### `item_effects_on_removed_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removed.

### `item_effects_on_added_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become added.

### `item_effects_on_modified_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become modified.

### `item_effects_on_filtered_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become filtered.

### `item_effects_on_sorted_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become sorted.

### `item_effects_on_grouped_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become grouped.

### `item_effects_on_categorized_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become categorized.

### `item_effects_on_tagged_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become tagged.

### `item_effects_on_colored_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become colored.

### `item_effects_on_iconized_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become iconized.

### `item_effects_on_visualized_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become visualized.

### `item_effects_on_audible_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become audible.

### `item_effects_on_haptic_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become haptic.

### `item_effects_on_animated_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become animated.

### `item_effects_on_interactive_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become interactive.

### `item_effects_on_dynamic_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dynamic.

### `item_effects_on_static_item_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become static.

### `item_effects_on_unique_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes unique.

### `item_effects_on_reusable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reusable.

### `item_effects_on_consumable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes consumable.

### `item_effects_on_collectible_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes collectible.

### `item_effects_on_placeable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes placeable.

### `item_effects_on_movable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes movable.

### `item_effects_on_rotatable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes rotatable.

### `item_effects_on_scalable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scalable.

### `item_effects_on_transparent_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes transparent.

### `item_effects_on_translucent_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes translucent.

### `item_effects_on_opaque_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes opaque.

### `item_effects_on_emissive_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes emissive.

### `item_effects_on_reflective_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reflective.

### `item_effects_on_refractive_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes refractive.

### `item_effects_on_shadow_casting_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow casting.

### `item_effects_on_shadow_receiving_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow receiving.

### `item_effects_on_occluder_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occluder.

### `item_effects_on_occludee_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occludee.

### `item_effects_on_trigger_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a trigger.

### `item_effects_on_collider_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a collider.

### `item_effects_on_rigidbody_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a rigidbody.

### `item_effects_on_kinematic_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes kinematic.

### `item_effects_on_static_collider_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a static collider.

### `item_effects_on_dynamic_collider_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a dynamic collider.

### `item_effects_on_sensor_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a sensor.

### `item_effects_on_actuator_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an actuator.

### `item_effects_on_controller_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a controller.

### `item_effects_on_generator_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a generator.

### `item_effects_on_consumer_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a consumer.

### `item_effects_on_emitter_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an emitter.

### `item_effects_on_attractor_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an attractor.

### `item_effects_on_repulsor_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a repulsor.

### `item_effects_on_modifier_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a modifier.

### `item_effects_on_filter_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a filter.

### `item_effects_on_transformer_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a transformer.

### `item_effects_on_analyzer_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an analyzer.

### `item_effects_on_detector_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a detector.

### `item_effects_on_tracker_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a tracker.

### `item_effects_on_recorder_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a recorder.

### `item_effects_on_player_controlled_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes player controlled.

### `item_effects_on_ai_controlled_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes AI controlled.

### `item_effects_on_scripted_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scripted.

### `item_effects_on_procedural_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes procedural.

### `item_effects_on_randomized_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes randomized.

### `item_effects_on_configurable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes configurable.

### `item_effects_on_customizable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes customizable.

### `item_effects_on_upgradable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes upgradable.

### `item_effects_on_downgradable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes downgradable.

### `item_effects_on_repairable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes repairable.

### `item_effects_on_breakable_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes breakable.

### `item_effects_on_destructible_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes destructible.

### `item_effects_on_removable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removable.

### `item_effects_on_addable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become addable.

### `item_effects_on_usable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become usable.

### `item_effects_on_equippable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equippable.

### `item_effects_on_droppable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become droppable.

### `item_effects_on_consumable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumable.

### `item_effects_on_stackable_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become stackable.

### `item_effects_on_unique_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unique.

### `item_effects_on_permanent_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become permanent.

### `item_effects_on_temporary_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become temporary.

### `item_effects_on_hidden_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become hidden.

### `item_effects_on_locked_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become locked.

### `item_effects_on_unlocked_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unlocked.

### `item_effects_on_equipped_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equipped.

### `item_effects_on_unequipped_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unequipped.

### `item_effects_on_held_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become held.

### `item_effects_on_dropped_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dropped.

### `item_effects_on_used_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become used.

### `item_effects_on_consumed_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumed.

### `item_effects_on_destroyed_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become destroyed.

### `item_effects_on_removed_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removed.

### `item_effects_on_added_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become added.

### `item_effects_on_modified_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become modified.

### `item_effects_on_filtered_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become filtered.

### `item_effects_on_sorted_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become sorted.

### `item_effects_on_grouped_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become grouped.

### `item_effects_on_categorized_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become categorized.

### `item_effects_on_tagged_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become tagged.

### `item_effects_on_colored_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become colored.

### `item_effects_on_iconized_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become iconized.

### `item_effects_on_visualized_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become visualized.

### `item_effects_on_audible_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become audible.

### `item_effects_on_haptic_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become haptic.

### `item_effects_on_animated_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become animated.

### `item_effects_on_interactive_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become interactive.

### `item_effects_on_dynamic_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dynamic.

### `item_effects_on_static_item_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become static.

### `item_effects_on_unique_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes unique.

### `item_effects_on_reusable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reusable.

### `item_effects_on_consumable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes consumable.

### `item_effects_on_collectible_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes collectible.

### `item_effects_on_placeable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes placeable.

### `item_effects_on_movable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes movable.

### `item_effects_on_rotatable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes rotatable.

### `item_effects_on_scalable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scalable.

### `item_effects_on_transparent_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes transparent.

### `item_effects_on_translucent_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes translucent.

### `item_effects_on_opaque_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes opaque.

### `item_effects_on_emissive_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes emissive.

### `item_effects_on_reflective_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reflective.

### `item_effects_on_refractive_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes refractive.

### `item_effects_on_shadow_casting_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow casting.

### `item_effects_on_shadow_receiving_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow receiving.

### `item_effects_on_occluder_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occluder.

### `item_effects_on_occludee_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occludee.

### `item_effects_on_trigger_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a trigger.

### `item_effects_on_collider_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a collider.

### `item_effects_on_rigidbody_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a rigidbody.

### `item_effects_on_kinematic_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes kinematic.

### `item_effects_on_static_collider_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a static collider.

### `item_effects_on_dynamic_collider_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a dynamic collider.

### `item_effects_on_sensor_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a sensor.

### `item_effects_on_actuator_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an actuator.

### `item_effects_on_controller_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a controller.

### `item_effects_on_generator_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a generator.

### `item_effects_on_consumer_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a consumer.

### `item_effects_on_emitter_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an emitter.

### `item_effects_on_attractor_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an attractor.

### `item_effects_on_repulsor_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a repulsor.

### `item_effects_on_modifier_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a modifier.

### `item_effects_on_filter_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a filter.

### `item_effects_on_transformer_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a transformer.

### `item_effects_on_analyzer_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an analyzer.

### `item_effects_on_detector_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a detector.

### `item_effects_on_tracker_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a tracker.

### `item_effects_on_recorder_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a recorder.

### `item_effects_on_player_controlled_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes player controlled.

### `item_effects_on_ai_controlled_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes AI controlled.

### `item_effects_on_scripted_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scripted.

### `item_effects_on_procedural_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes procedural.

### `item_effects_on_randomized_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes randomized.

### `item_effects_on_configurable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes configurable.

### `item_effects_on_customizable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes customizable.

### `item_effects_on_upgradable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes upgradable.

### `item_effects_on_downgradable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes downgradable.

### `item_effects_on_repairable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes repairable.

### `item_effects_on_breakable_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes breakable.

### `item_effects_on_destructible_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes destructible.

### `item_effects_on_removable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removable.

### `item_effects_on_addable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become addable.

### `item_effects_on_usable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become usable.

### `item_effects_on_equippable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equippable.

### `item_effects_on_droppable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become droppable.

### `item_effects_on_consumable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumable.

### `item_effects_on_stackable_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become stackable.

### `item_effects_on_unique_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unique.

### `item_effects_on_permanent_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become permanent.

### `item_effects_on_temporary_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become temporary.

### `item_effects_on_hidden_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become hidden.

### `item_effects_on_locked_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become locked.

### `item_effects_on_unlocked_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unlocked.

### `item_effects_on_equipped_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equipped.

### `item_effects_on_unequipped_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unequipped.

### `item_effects_on_held_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become held.

### `item_effects_on_dropped_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dropped.

### `item_effects_on_used_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become used.

### `item_effects_on_consumed_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumed.

### `item_effects_on_destroyed_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become destroyed.

### `item_effects_on_removed_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removed.

### `item_effects_on_added_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become added.

### `item_effects_on_modified_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become modified.

### `item_effects_on_filtered_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become filtered.

### `item_effects_on_sorted_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become sorted.

### `item_effects_on_grouped_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become grouped.

### `item_effects_on_categorized_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become categorized.

### `item_effects_on_tagged_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become tagged.

### `item_effects_on_colored_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become colored.

### `item_effects_on_iconized_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become iconized.

### `item_effects_on_visualized_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become visualized.

### `item_effects_on_audible_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become audible.

### `item_effects_on_haptic_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become haptic.

### `item_effects_on_animated_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become animated.

### `item_effects_on_interactive_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become interactive.

### `item_effects_on_dynamic_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dynamic.

### `item_effects_on_static_item_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become static.

### `item_effects_on_unique_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes unique.

### `item_effects_on_reusable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reusable.

### `item_effects_on_consumable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes consumable.

### `item_effects_on_collectible_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes collectible.

### `item_effects_on_placeable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes placeable.

### `item_effects_on_movable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes movable.

### `item_effects_on_rotatable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes rotatable.

### `item_effects_on_scalable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scalable.

### `item_effects_on_transparent_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes transparent.

### `item_effects_on_translucent_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes translucent.

### `item_effects_on_opaque_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes opaque.

### `item_effects_on_emissive_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes emissive.

### `item_effects_on_reflective_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes reflective.

### `item_effects_on_refractive_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes refractive.

### `item_effects_on_shadow_casting_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow casting.

### `item_effects_on_shadow_receiving_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes shadow receiving.

### `item_effects_on_occluder_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occluder.

### `item_effects_on_occludee_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an occludee.

### `item_effects_on_trigger_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a trigger.

### `item_effects_on_collider_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a collider.

### `item_effects_on_rigidbody_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a rigidbody.

### `item_effects_on_kinematic_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes kinematic.

### `item_effects_on_static_collider_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a static collider.

### `item_effects_on_dynamic_collider_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a dynamic collider.

### `item_effects_on_sensor_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a sensor.

### `item_effects_on_actuator_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an actuator.

### `item_effects_on_controller_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a controller.

### `item_effects_on_generator_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a generator.

### `item_effects_on_consumer_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a consumer.

### `item_effects_on_emitter_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an emitter.

### `item_effects_on_attractor_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an attractor.

### `item_effects_on_repulsor_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a repulsor.

### `item_effects_on_modifier_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a modifier.

### `item_effects_on_filter_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a filter.

### `item_effects_on_transformer_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a transformer.

### `item_effects_on_analyzer_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes an analyzer.

### `item_effects_on_detector_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a detector.

### `item_effects_on_tracker_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a tracker.

### `item_effects_on_recorder_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes a recorder.

### `item_effects_on_player_controlled_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes player controlled.

### `item_effects_on_ai_controlled_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes AI controlled.

### `item_effects_on_scripted_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes scripted.

### `item_effects_on_procedural_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes procedural.

### `item_effects_on_randomized_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes randomized.

### `item_effects_on_configurable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes configurable.

### `item_effects_on_customizable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes customizable.

### `item_effects_on_upgradable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes upgradable.

### `item_effects_on_downgradable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes downgradable.

### `item_effects_on_repairable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes repairable.

### `item_effects_on_breakable_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes breakable.

### `item_effects_on_destructible_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when the entity possessing this inventory becomes destructible.

### `item_effects_on_removable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removable.

### `item_effects_on_addable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become addable.

### `item_effects_on_usable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become usable.

### `item_effects_on_equippable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equippable.

### `item_effects_on_droppable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become droppable.

### `item_effects_on_consumable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumable.

### `item_effects_on_stackable_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become stackable.

### `item_effects_on_unique_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unique.

### `item_effects_on_permanent_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become permanent.

### `item_effects_on_temporary_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become temporary.

### `item_effects_on_hidden_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become hidden.

### `item_effects_on_locked_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become locked.

### `item_effects_on_unlocked_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unlocked.

### `item_effects_on_equipped_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become equipped.

### `item_effects_on_unequipped_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become unequipped.

### `item_effects_on_held_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become held.

### `item_effects_on_dropped_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become dropped.

### `item_effects_on_used_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become used.

### `item_effects_on_consumed_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become consumed.

### `item_effects_on_destroyed_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become destroyed.

### `item_effects_on_removed_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become removed.

### `item_effects_on_added_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become added.

### `item_effects_on_modified_item_entity_entity_entity_entity`

*   **Type:** List of Strings
*   **Description:** A list of item effect strings that are triggered when items within the entity possessing this inventory become modified.

### `item_effects