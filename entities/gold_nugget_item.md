---
title: Gold Nugget Item
category: entities
---

# Gold Nugget Item

This document details the configuration for the Gold Nugget item in Noita, focusing on its properties and behaviors relevant to AI-assisted modding.

## Core Entity Definition

The Gold Nugget is defined as an entity with specific tags that dictate its interaction within the game world.

```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >
```

*   **`name`**: "unknown" - This is a placeholder and typically not critical for functionality.
*   **`tags`**: `item_physics`, `gold_nugget` - These tags are crucial for identifying the entity as a physics-enabled item and specifically as a gold nugget.

## UI and Visual Components

These components define how the item is presented to the player and its visual representation in the game.

### UIInfoComponent

Provides information for the user interface.

```xml
<UIInfoComponent
    _tags="enabled_in_world"
    name="$item_goldnugget">
</UIInfoComponent>
```

*   **`name`**: `$item_goldnugget` - Refers to a localized string for the item's name.

### PhysicsBodyComponent

Defines the physical properties of the gold nugget.

```xml
<PhysicsBodyComponent
    _tags="enabled_in_world"
    uid="1"
    allow_sleep="1"
    angular_damping="0"
    fixed_rotation="0"
    is_bullet="0"
    linear_damping="0"
    auto_clean="0"
    hax_fix_going_through_ground="1"
    on_death_leave_physics_body="1" >
</PhysicsBodyComponent>
```

*   **`uid`**: `1` - Unique identifier for this physics body.
*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive to save performance.
*   **`hax_fix_going_through_ground`**: `1` - A specific fix to prevent the item from falling through the ground.

### PhysicsImageShapeComponent

Defines the visual shape and material of the item in the physics world.

```xml
<PhysicsImageShapeComponent
    _tags="enabled_in_world"
    body_id="1"
    centered="1"
    image_file="data/items_gfx/goldnugget_01.png"
    material="gold_box2d" >
</PhysicsImageShapeComponent>
```

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`image_file`**: `data/items_gfx/goldnugget_01.png` - The sprite used for the gold nugget.
*   **`material`**: `gold_box2d` - The physics material applied, influencing its interaction with other physics objects.

## Item Properties

These components define the item's behavior as a collectible in the game.

### VariableStorageComponent

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
    _tags="enabled_in_world"
    name="gold_value"
    value_int="10" >
</VariableStorageComponent>
```

*   **`name`**: `gold_value` - The name of the variable.
*   **`value_int`**: `10` - The integer value assigned to `gold_value`, representing the nugget's worth.

### ItemComponent

Defines the item's core collectible properties.

```xml
<ItemComponent
    _tags="enabled_in_world"
    auto_pickup="1"
    item_name="$item_goldnugget_10"
    stats_count_as_item_pick_up="0"
    max_child_items="0"
    is_pickable="1"
    ui_sprite="data/ui_gfx/items/goldnugget.png"
    ui_description="Lorem ipsum"
    play_pick_sound="0"
    preferred_inventory="FULL" >
</ItemComponent>
```

*   **`auto_pickup`**: `1` - The item will be automatically picked up by the player if they are close enough.
*   **`item_name`**: `$item_goldnugget_10` - Localized string for the item's name, likely indicating its value.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards statistics related to picking up items.
*   **`is_pickable`**: `1` - The item can be picked up by the player.
*   **`ui_sprite`**: `data/ui_gfx/items/goldnugget.png` - The sprite used in the UI inventory.
*   **`preferred_inventory`**: `FULL` - Suggests the item should be placed in the main inventory.

### HitboxComponent

Defines the collision area for the item.

```xml
<HitboxComponent
    _tags="enabled_in_world"
    aabb_min_x="-3"
    aabb_max_x="3"
    aabb_min_y="-5"
    aabb_max_y="0" >
</HitboxComponent>
```

*   **`aabb_min_x`**, **`aabb_max_x`**, **`aabb_min_y`**, **`aabb_max_y`**: Define the bounding box of the item's hitbox.

### LifetimeComponent

Determines how long the item persists in the world.

```xml
<LifetimeComponent
    _tags="enabled_in_world"
    lifetime="900" >
</LifetimeComponent>
```

*   **`lifetime`**: `900` - The item will disappear after 900 game frames (approximately 15 seconds).

## Scripted Behaviors

These components attach Lua scripts to the entity, enabling custom logic.

### LuaComponent (Item Picked Up)

Executes a script when the item is picked up.

```xml
<LuaComponent
    _tags="enabled_in_world"
    script_item_picked_up="data/scripts/items/gold_pickup.lua" >
</LuaComponent>
```

*   **`script_item_picked_up`**: `data/scripts/items/gold_pickup.lua` - This script handles logic specifically when the gold nugget is collected.

### LuaComponent (Gold Explosion)

Executes a script upon the entity's creation.

```xml
<LuaComponent
    _tags="enabled_in_world"
    script_source_file="data/scripts/perks/gold_explosion.lua"
    execute_on_added="1"
    remove_after_executed="1" >
</LuaComponent>
```

*   **`script_source_file`**: `data/scripts/perks/gold_explosion.lua` - This script is executed immediately when the gold nugget is spawned.
*   **`execute_on_added`**: `1` - Ensures the script runs when the entity is added to the game world.
*   **`remove_after_executed`**: `1` - The Lua component itself is removed after its script has run.

## Particle Effects

This component adds visual particle effects to the entity.

### SpriteParticleEmitterComponent

Emits particles to create visual effects.

```xml
<SpriteParticleEmitterComponent
    _tags="enabled_in_world"
    sprite_file="data/particles/shine_08.xml"
    lifetime="0.2"
    randomize_lifetime.min="0.1"
    randomize_lifetime.max="0.8"
    emission_interval_min_frames="50"
    emission_interval_max_frames="250"
    count_min="1"
    count_max="1"
    additive="1"
    emissive="0"
    scale.x="1.0"
    scale.y="1.0"
    sprite_random_rotation="1"
    randomize_scale.min_x="-0.1"
    randomize_scale.max_x="0.1"
    randomize_scale.min_y="-0.1"
    randomize_scale.max_y="0.1"
    randomize_position.min_y="-3"
    randomize_position.max_y="3"
    randomize_position.min_x="-3"
    randomize_position.max_x="3"
    velocity_slowdown="6"
    randomize_animation_speed_coeff.min="0.667"
    randomize_animation_speed_coeff.max="1.0" >
</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: `data/particles/shine_08.xml` - Specifies the particle effect sprite to use.
*   **`lifetime`**: `0.2` - The duration of each emitted particle.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: Control the timing between particle emissions.
*   **`count_min`**, **`count_max`**: Determine the number of particles emitted per interval.
*   **`additive`**: `1` - Particles are rendered additively, often used for glowing effects.
*   **`randomize_scale`**, **`randomize_position`**: Introduce variations in particle size and spawn location.
*   **`velocity_slowdown`**: `6` - Controls how quickly particles lose velocity.