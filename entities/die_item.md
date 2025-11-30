---
title: Die Item
category: entities
---

# Die Item

This entity represents the "Die" item in Noita, a physics-based object with unique interactions.

## Core Components

### PhysicsBodyComponent
Manages the physical properties of the die.

*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive.
*   **`is_bullet`**: `1` - Indicates it's treated as a projectile in physics simulations.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent it from clipping through the ground.

### PhysicsImageShapeComponent
Defines the visual shape and material for physics interactions.

*   **`image_file`**: `data/props_gfx/die.png` - The texture used for the die's shape.
*   **`material`**: `rock_box2d_hard` - The physical material properties.

### SpriteComponent (World)
Handles the visual representation of the die when it's in the game world.

*   **`image_file`**: `data/props_gfx/die_pips.xml` - The graphical asset for the die's pips.
*   **`rect_animation`**: `stand` - The default animation state.
*   **`z_index`**: `-1` - Controls rendering order.

### HitboxComponent
Defines the collision area for the die.

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: `-6` to `6` - Defines a square hitbox.

### DamageModelComponent
Manages the die's health and damage interactions.

*   **`hp`**: `9999` - Very high health, making it difficult to destroy through direct damage.
*   **`invincibility_frames`**: `40` - Provides a short period of invulnerability after taking damage.
*   **`falling_damages`**: `1` - The die can take damage from falling.
*   **`damage_multipliers`**: Defines how much damage it takes from different sources. Notably, it has reduced damage from melee, projectiles, and drills, and zero damage from explosions and fire.

### LuaComponent (Scripting)
These components link the die to Lua scripts for custom behavior.

*   **`script_damage_received`**: `data/scripts/items/die_roll.lua` - Handles events when the die receives damage.
*   **`script_enabled_changed`**: `data/scripts/items/die_roll.lua` - Handles events when the die's enabled state changes.
*   **`script_kick`**: `data/scripts/items/die_roll.lua` - Handles events when the die is kicked.
*   **`script_source_file`**: `data/scripts/items/die_status.lua` - A script likely managing the die's status or state.

### VariableStorageComponent
Stores internal variables for the die.

*   **`name`**: `rolling`
*   **`value_int`**: `0` - Likely indicates the die is not currently in a "rolling" state.

### PhysicsThrowableComponent
Enables the die to be thrown.

*   **`max_throw_speed`**: `180`
*   **`throw_force_coeff`**: `1.5`

### PhysicsBodyCollisionDamageComponent
Deals damage to other entities upon collision.

*   **`speed_threshold`**: `140.0` - The speed at which collisions start dealing damage.

### ItemComponent
Defines the item properties for inventory and UI.

*   **`item_name`**: `$item_die` - The in-game name.
*   **`is_pickable`**: `1` - Can be picked up by the player.
*   **`is_equipable_forced`**: `1` - Can be equipped.
*   **`ui_sprite`**: `data/ui_gfx/items/die.png` - The UI icon.
*   **`ui_description`**: `$itemdesc_die` - The in-game description.
*   **`preferred_inventory`**: `QUICK` - Its default inventory slot.

### UIInfoComponent
Provides information for the UI.

*   **`name`**: `$item_die`

### AbilityComponent
Grants abilities to the entity.

*   **`ui_name`**: `$item_die`
*   **`throw_as_item`**: `1` - Can be thrown as an item.

### SpriteComponent (In Hand)
Handles the visual representation of the die when held by the player.

*   **`_enabled`**: `0` - This sprite is initially disabled, likely activated when equipped.
*   **`image_file`**: `data/items_gfx/in_hand/die.png` - The texture for when held.