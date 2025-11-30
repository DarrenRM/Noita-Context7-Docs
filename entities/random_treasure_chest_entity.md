---
title: Random Treasure Chest Entity
category: entities
---

# Random Treasure Chest Entity

This document describes the entity definition for a random treasure chest in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity tags="teleportable_NOT,item_physics,chest">
  <!-- Components -->
</Entity>
```

### Key Tags:

*   `teleportable_NOT`: Prevents the chest from being teleported.
*   `item_physics`: Indicates that the entity has physics properties and can interact with the game world.
*   `chest`: A general tag identifying this entity as a chest.

## Components

This section details the key components that define the behavior and appearance of the treasure chest.

### UIInfoComponent

Provides information for the user interface, such as the item name.

```xml
<UIInfoComponent
  name="$item_chest_treasure"
>
</UIInfoComponent>
```

*   `name`: `$item_chest_treasure` - This is a localization key for the chest's name, which will appear in the game's UI.

### PositionSeedComponent

Ensures consistent placement across different game sessions.

```xml
<PositionSeedComponent />
```

### PhysicsBodyComponent

Defines the physical properties of the chest.

```xml
<PhysicsBodyComponent
  _tags="enabled_in_world"
  uid="1"
  allow_sleep="1"
  angular_damping="0"
  fixed_rotation="0"
  is_bullet="1"
  linear_damping="0"
  auto_clean="1"
  hax_fix_going_through_ground="1"
  on_death_leave_physics_body="0"
  on_death_really_leave_body="0"
>
</PhysicsBodyComponent>
```

*   `uid`: `1` - Unique identifier for this physics body.
*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when not in motion to save performance.
*   `is_bullet`: `1` - Treats this entity as a projectile for physics interactions.
*   `auto_clean`: `1` - Automatically removes the physics body when it's no longer needed.
*   `hax_fix_going_through_ground`: `1` - A workaround to prevent the entity from falling through the ground.

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the chest.

```xml
<PhysicsImageShapeComponent
  body_id="1"
  centered="1"
  image_file="data/buildings_gfx/chest_random.png"
  material="wood_prop"
>
</PhysicsImageShapeComponent>
```

*   `body_id`: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   `image_file`: `data/buildings_gfx/chest_random.png` - The sprite used for the chest.
*   `material`: `wood_prop` - The material type, influencing physics interactions.

### ItemComponent

Marks this entity as an item that can be picked up.

```xml
<ItemComponent
  item_name="$item_chest_treasure"
  play_spinning_animation="0"
  stats_count_as_item_pick_up="0"
  play_pick_sound="0"
>
</ItemComponent>
```

*   `item_name`: `$item_chest_treasure` - Links to the UI name.
*   `stats_count_as_item_pick_up`: `0` - This item pickup does not contribute to collection statistics.
*   `play_pick_sound`: `0` - Disables the default item pickup sound.

### LuaComponent (Physics Modified)

Executes a Lua script when the physics body is modified.

```xml
<LuaComponent
  script_physics_body_modified="data/scripts/items/chest_random.lua"
  execute_times="1"
>
</LuaComponent>
```

*   `script_physics_body_modified`: `data/scripts/items/chest_random.lua` - The script file to execute.
*   `execute_times`: `1` - The script will execute only once.

### LuaComponent (Item Picked Up)

Executes a Lua script when the item is picked up.

```xml
<LuaComponent
  script_item_picked_up="data/scripts/items/chest_random.lua"
>
</LuaComponent>
```

*   `script_item_picked_up`: `data/scripts/items/chest_random.lua` - The same script file is used for item pickup logic.

### LightComponent

Adds a light source to the chest.

```xml
<LightComponent
  _tags="enabled_in_world"
  r="255"
  g="255"
  b="255"
  radius="64"
  fade_out_time="0.75"
>
</LightComponent>
```

*   `r`, `g`, `b`: `255` - Sets the light color to white.
*   `radius`: `64` - The range of the light.
*   `fade_out_time`: `0.75` - How long it takes for the light to fade out.