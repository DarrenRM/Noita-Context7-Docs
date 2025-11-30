---
title: Random Chest Item
category: entities
---

# Random Chest Item

This entity represents a random chest that can be found in the game. When interacted with, it will spawn a random item.

## Key Components

### `UIInfoComponent`
- `name`: `$item_chest_treasure` - Defines the in-game name for the chest.

### `PhysicsBodyComponent`
- `is_bullet`: `1` - Allows the chest to interact with physics as a projectile.
- `auto_clean`: `1` - Automatically cleans up the physics body when no longer needed.
- `hax_fix_going_through_ground`: `1` - A fix to prevent the chest from falling through the ground.

### `PhysicsImageShapeComponent`
- `image_file`: `data/buildings_gfx/chest_random.png` - Specifies the visual sprite for the chest.
- `material`: `wood_prop` - The physics material applied to the chest.

### `ItemComponent`
- `item_name`: `$item_chest_treasure` - Links the chest to its in-game name.
- `custom_pickup_string`: `$itempickup_open` - The text displayed when the player can interact with the chest.

### `LuaComponent` (for physics body modification)
- `script_physics_body_modified`: `data/scripts/items/chest_random.lua` - Executes a Lua script when the physics body is modified.
- `execute_times`: `1` - The script will execute only once.

### `LuaComponent` (for item pickup)
- `script_item_picked_up`: `data/scripts/items/chest_random.lua` - Executes a Lua script when the item is picked up. This is likely where the random item generation logic resides.

### `LightComponent`
- `r`, `g`, `b`: `255` - Sets the light color to white.
- `radius`: `64` - The radius of the light emitted by the chest.
- `fade_out_time`: `0.75` - How long it takes for the light to fade out.