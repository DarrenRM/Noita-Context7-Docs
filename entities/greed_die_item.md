---
title: Greed Die Item
category: entities
---

# Greed Die Item

This document details the `physics_greed_die.xml` entity, representing the Greed Die item in Noita.

## Core Components

The Greed Die is a physics-based item with several key components that define its behavior and appearance.

### PhysicsBodyComponent

Manages the physical properties of the Greed Die.

*   `allow_sleep`: `1` - Allows the object to enter a sleep state when not in motion.
*   `is_bullet`: `1` - Indicates it can be treated as a projectile.
*   `hax_fix_going_through_ground`: `1` - A fix to prevent it from clipping through the ground.

### PhysicsImageShapeComponent

Defines the visual shape and material of the Greed Die's physical body.

*   `image_file`: `data/props_gfx/greed_die.png` - The texture for the physical body.
*   `material`: `rock_box2d_hard` - The physical material properties.

### SpriteComponent (World)

Controls the visual representation of the Greed Die when it's in the game world.

*   `image_file`: `data/props_gfx/greed_die_pips.xml` - The sprite animation file.
*   `rect_animation`: `stand` - The default animation state.
*   `z_index`: `-1` - Controls rendering order.

### HitboxComponent

Defines the collision area for the Greed Die.

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_x`: Defines a bounding box of 12x12 units.

### DamageModelComponent

Manages health, damage resistance, and how the Greed Die reacts to damage.

*   `hp`: `9999` - Very high health, making it difficult to destroy through direct damage.
*   `invincibility_frames`: `40` - Provides a short period of invincibility after taking damage.
*   `damage_multipliers`: Defines how much damage it takes from different sources. Notably, it has reduced damage from melee, projectiles, and drills, and takes no damage from explosions or fire.

### LuaComponent (Scripts)

These components link the Greed Die to Lua scripts that define its unique behaviors.

*   `script_damage_received`: `data/scripts/items/die_roll.lua` - Handles events when damage is received.
*   `script_enabled_changed`: `data/scripts/items/die_roll.lua` - Handles events when the entity's enabled state changes.
*   `script_kick`: `data/scripts/items/die_roll.lua` - Handles events when the entity is kicked.
*   `script_source_file`: `data/scripts/items/greed_die_status.lua` - A script that likely manages the ongoing status or effects of the die.

### VariableStorageComponent

Stores internal variables for the Greed Die.

*   `name`: `rolling`
*   `value_int`: `0` - Likely indicates the die is not currently in a "rolling" state.

### PhysicsThrowableComponent

Enables the Greed Die to be thrown.

*   `max_throw_speed`: `180`
*   `throw_force_coeff`: `1.5`

### PhysicsBodyCollisionDamageComponent

Deals damage to other entities upon collision.

*   `speed_threshold`: `140.0` - The speed at which collisions start dealing damage.

### ItemComponent

Defines the item properties, such as its name, pick-up behavior, and inventory placement.

*   `item_name`: `$item_greed_die` - The internal name for the item.
*   `is_pickable`: `1` - Can be picked up by the player.
*   `is_equipable_forced`: `1` - Can be forced into an equipment slot.
*   `ui_sprite`: `data/ui_gfx/items/greed_die.png` - The UI icon for the item.
*   `preferred_inventory`: `QUICK` - Suggests it should be placed in the quick inventory.

### UIInfoComponent

Provides information for the UI.

*   `name`: `$item_greed_die` - The displayed name in the UI.

### AbilityComponent

Grants abilities to the item.

*   `throw_as_item`: `1` - Allows it to be thrown as an item.

### SpriteComponent (In Hand)

Defines the visual representation of the Greed Die when held by the player.

*   `image_file`: `data/items_gfx/in_hand/greed_die.png` - The sprite for when it's in the player's hand.