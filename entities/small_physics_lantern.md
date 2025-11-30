---
title: Small Physics Lantern
category: entities
---

# Small Physics Lantern

This document details the configuration of the `physics_lantern_small.xml` entity, designed for AI-assisted modding of Noita. This entity represents a small, breakable lantern that can spill oil and explode when damaged.

## Core Components

The `physics_lantern_small` entity is built upon several key components that define its behavior and appearance.

### Base Item Physics

```xml
<Base file="data/entities/base_item_physics.xml" >
  <PhysicsImageShapeComponent
    image_file="data/props_gfx/lantern_small.png"
    material="glass_box2d" >
  </PhysicsImageShapeComponent>

  <PhysicsBodyComponent allow_sleep="1" angular_damping="0.01" gridworld_box2d="1" linear_damping="0.1" >
  </PhysicsBodyComponent>
</Base>
```

*   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape of the lantern.
    *   `image_file`: Specifies the sprite for the lantern (`data/props_gfx/lantern_small.png`).
    *   `material`: Sets the physics material to `glass_box2d`, influencing its interaction with the physics engine.
*   **`PhysicsBodyComponent`**: Configures the physical properties of the lantern's body.
    *   `allow_sleep`: Enables the body to go to sleep when inactive, optimizing performance.
    *   `angular_damping`: Controls how quickly rotational velocity decreases.
    *   `gridworld_box2d`: Indicates it's a Box2D physics body within the grid world.
    *   `linear_damping`: Controls how quickly linear velocity decreases.

### Physics Joint Component

```xml
<PhysicsJointComponent
  nail_to_wall="1"
  breakable="1"
  pos_x="4.5"
  pos_y="4" >
</PhysicsJointComponent>
```

*   This component attaches the lantern to its environment, simulating it being nailed to a wall.
    *   `nail_to_wall`: When true, attempts to fix the entity to a wall.
    *   `breakable`: Allows the joint to break under stress.
    *   `pos_x`, `pos_y`: Offset from the entity's origin for the joint's position.

### Light Component

```xml
<LightComponent
  _enabled="1"
  radius="240" >
</LightComponent>
```

*   Provides illumination.
    *   `_enabled`: Controls whether the light is active.
    *   `radius`: The range of the light source.

### Material Inventory Component

```xml
<MaterialInventoryComponent
  _enabled="1"
  drop_as_item="0"
  on_death_spill="1"
  leak_on_damage_percent="0.999"
  >
  <count_per_material_type>
    <Material material="oil" count="4"  />
  </count_per_material_type>
</MaterialInventoryComponent>
```

*   Manages the materials contained within the lantern.
    *   `drop_as_item`: Prevents the contained material from dropping as a separate item on death.
    *   `on_death_spill`: Causes the contained material to spill out when the entity dies.
    *   `leak_on_damage_percent`: Defines the damage threshold at which the material starts leaking.
    *   `count_per_material_type`: Specifies the types and amounts of materials.
        *   `Material material="oil" count="4"`: The lantern contains 4 units of oil.

### DamageModelComponent

```xml
<DamageModelComponent
  air_needed="0"
  blood_material="oil"
  drop_items_on_death="0"
  falling_damage_damage_max="1.2"
  falling_damage_damage_min="0.1"
  falling_damage_height_max="250"
  falling_damage_height_min="70"
  falling_damages="0"
  fire_damage_amount="0.2"
  fire_probability_of_ignition="0"
  hp="0.15"
  is_on_fire="0"
  materials_create_messages="0"
  materials_damage="0"
  ragdoll_filenames_file=""
  ragdoll_material=""
  critical_damage_resistance="1"
  ui_report_damage="0" >
</DamageModelComponent>
```

*   Handles damage and its effects.
    *   `air_needed`: Whether air is required for damage calculations (0 = no).
    *   `blood_material`: The material that spills when damaged (set to `oil`).
    *   `falling_damage_...`: Parameters related to damage taken from falling.
    *   `hp`: The health points of the lantern.
    *   `fire_damage_amount`: The amount of damage taken from fire.
    *   `fire_probability_of_ignition`: Probability of igniting from fire.
    *   `materials_damage`: Whether materials within the entity can cause damage.
    *   `critical_damage_resistance`: Resistance to critical hits.

### ExplodeOnDamageComponent

```xml
<ExplodeOnDamageComponent
  explode_on_death_percent="1"
  explode_on_damage_percent="0.0"
  physics_body_modified_death_probability="0.75"
  physics_body_destruction_required="0.5"
  >
  <config_explosion
    never_cache="0"
    damage="0.2"
    camera_shake="1"
    explosion_radius="5"
    explosion_sprite="data/particles/explosion_008.xml"
    explosion_sprite_lifetime="8"
    create_cell_probability="50"
    hole_destroy_liquid="0"
    hole_enabled="1"
    ray_energy="10000"
    particle_effect="1"
    damage_mortals="1"
    physics_explosion_power.min="0.05"
    physics_explosion_power.max="0.1"
    physics_throw_enabled="1"
    shake_vegetation="1"
    sparks_count_min="5"
    sparks_count_max="10"
    sparks_enabled="1"
    stains_enabled="1"
    stains_radius="10" >
  </config_explosion>
</ExplodeOnDamageComponent>
```

*   Manages the explosion behavior.
    *   `explode_on_death_percent`: Probability of exploding upon death.
    *   `explode_on_damage_percent`: Probability of exploding when taking damage.
    *   `physics_body_modified_death_probability`: Probability of exploding if the physics body is modified upon death.
    *   `physics_body_destruction_required`: Threshold for physics body destruction to trigger explosion.
    *   **`config_explosion`**: Detailed settings for the explosion effect.
        *   `damage`: Base damage of the explosion.
        *   `camera_shake`: Intensity of camera shake.
        *   `explosion_radius`: The radius of the explosion.
        *   `explosion_sprite`: The particle effect used for the explosion.
        *   `damage_mortals`: Whether the explosion damages living entities.
        *   `physics_explosion_power`: The force applied to physics objects.
        *   `sparks_enabled`: Whether sparks are generated.
        *   `stains_enabled`: Whether stains are created.

### PhysicsBodyCollisionDamageComponent

```xml
<PhysicsBodyCollisionDamageComponent
  _tags="enabled_in_world"
  speed_threshold="120.0"
  >
</PhysicsBodyCollisionDamageComponent>
```

*   Applies damage based on collision speed.
    *   `speed_threshold`: The minimum speed required to inflict collision damage.

### SpriteComponent

```xml
<SpriteComponent
  _tags="character"
  alpha="1"
  image_file="data/props_gfx/lantern_small_flame.xml"
  offset_x="4.45"
  offset_y="6.5"
  emissive="0"
  additive="0"
  next_rect_animation=""
  rect_animation="stand"
  z_index="-1"
   >
</SpriteComponent>
```

*   Defines the visual sprite for the flame within the lantern.
    *   `image_file`: The sprite for the flame.
    *   `offset_x`, `offset_y`: Position offset for the flame sprite.
    *   `z_index`: Controls the rendering layer.

### TorchComponent

```xml
<TorchComponent
  _tags="enabled_in_world">
</TorchComponent>
```

*   Enables the entity to function as a torch, providing light.

### LuaComponent

```xml
<LuaComponent script_physics_body_modified="data/scripts/props/physics_lantern_damaged.lua"  />
<LuaComponent script_death="data/scripts/props/lantern_small_death.lua" />
```

*   Integrates custom Lua scripting for specific behaviors.
    *   `script_physics_body_modified`: Script executed when the physics body is modified (e.g., damaged).
    *   `script_death`: Script executed when the entity dies.

### AudioComponent

```xml
<AudioComponent
  file="data/audio/Desktop/materials.bank"
  event_root="collision/lantern" >
</AudioComponent>
```

*   Manages audio events associated with the lantern.
    *   `file`: The audio bank file.
    *   `event_root`: The root event name for audio triggers.