---
title: Powder Stash Item
category: entities
---

# Powder Stash Item

This document details the `powder_stash.xml` entity, which represents a collectible item in Noita that functions as a portable material storage and dispensing unit.

## Core Functionality

The Powder Stash is designed to store and dispense various powdered materials. It has physics properties for interaction in the world and Lua scripts to manage its behavior when picked up or used.

## Key Components and Attributes

### `Entity` Tags

*   `hittable`: Can be damaged by projectiles or other means.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves like a physics-enabled item.
*   `item_pickup`: Can be picked up by the player.
*   `powder_stash`: Identifies this entity as a powder stash.

### `PhysicsBodyComponent`

*   `allow_sleep`: `1` - Allows the physics body to sleep when not in motion.
*   `is_bullet`: `1` - Treats this as a bullet for collision purposes.
*   `hax_fix_going_through_ground`: `1` - A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`

*   `image_file`: `data/items_gfx/material_pouch.png` - The visual representation of the item.
*   `material`: `cloth_box2d` - The physics material used for collision.

### `LuaComponent` (for item pickup)

*   `remove_after_executed`: `1` - The script will be removed after execution.
*   `script_item_picked_up`: `data/scripts/items/potion_effect.lua` - This script is executed when the item is picked up.

### `PotionComponent`

*   `spray_velocity_coeff`: `75` - Controls the velocity of sprayed materials.
*   `spray_velocity_normalized_min`: `0.75` - Minimum normalized velocity for sprayed materials.
*   `never_color`: `1` - Prevents the sprayed material from being recolored.

### `MaterialSuckerComponent`

*   `material_type`: `1` - Specifies the type of material it can suck (likely powdered materials).
*   `barrel_size`: `1500` - The effective range or capacity for sucking materials.
*   `num_cells_sucked_per_frame`: `10` - How many material units are sucked per frame.
*   `randomized_position`: Defines a randomized area around the player for sucking.

### `MaterialInventoryComponent`

*   `drop_as_item`: `0` - When destroyed, it doesn't drop as a separate item.
*   `on_death_spill`: `1` - Spills its contents upon death.
*   `leak_on_damage_percent`: `1` - Will leak materials when damaged.
*   `min_damage_to_leak`: `0.0` - Leaks even with minimal damage.

### `DamageModelComponent`

*   `hp`: `2.5` - The health of the powder stash.
*   `materials_damage`: `1` - Can be damaged by certain materials.
*   `materials_that_damage`: `lava` - Lava is one of the materials that can damage it.
*   `materials_how_much_damage`: `0.001` - The amount of damage taken from specific materials.

### `ExplodeOnDamageComponent`

*   `explode_on_death_percent`: `1` - Explodes when its health reaches zero.
*   `config_explosion`: Defines the parameters of the explosion.
    *   `damage`: `0` - The explosion itself does no direct damage.
    *   `camera_shake`: `10` - Causes significant camera shake.
    *   `explosion_radius`: `3` - The radius of the explosion.
    *   `ray_energy`: `100000` - High energy for the explosion's effects.
    *   `physics_explosion_power.max`: `5` - Maximum physics force applied by the explosion.
    *   `sparks_enabled`: `1` - Sparks are generated.
    *   `stains_enabled`: `1` - Leaves stains on surfaces.

### `LuaComponent` (for item logic)

*   `script_source_file`: `data/scripts/items/powder_stash.lua` - The main script for the powder stash's functionality.

### `SpriteComponent`

*   `image_file`: `data/items_gfx/material_pouch.png` - The sprite shown when held in hand.
*   `_enabled`: `0` - This sprite is disabled by default, likely overridden by `enabled_in_hand` tags.

### `ItemComponent`

*   `item_name`: `$item_powder_stash_3` - The in-game name of the item.
*   `is_pickable`: `1` - Can be picked up.
*   `is_equipable_forced`: `1` - Can be equipped directly.
*   `ui_sprite`: `data/ui_gfx/items/material_pouch.png` - The sprite shown in the UI.
*   `ui_description`: `$itemdesc_powder_stash_3` - The in-game description.
*   `preferred_inventory`: `QUICK` - Defaults to the quick inventory.

### `AbilityComponent`

*   `throw_as_item`: `1` - Can be thrown as an item.

### `SpriteParticleEmitterComponent`

*   This component is responsible for visual effects, likely related to the spraying or sucking of materials. It defines particle properties like sprite, color, velocity, and emission patterns.

### `AudioLoopComponent`

*   `event_name`: `materials/spray_powder` - Triggers a sound effect when spraying powder.

### `AudioComponent`

*   `event_root`: `collision/wood_crate` - Likely plays a collision sound when interacting with certain objects.

## Summary

The Powder Stash is a versatile item that allows players to collect, store, and dispense powdered materials. Its physics properties, material interaction capabilities, and Lua scripting enable it to function as a portable tool for managing these resources. The item is designed to be durable but will explode and spill its contents when destroyed, adding a risk-reward element to its use.