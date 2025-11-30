---
title: Purple Egg Item
category: entities
---

# Purple Egg Item

This document details the configuration for the Purple Egg item in Noita, focusing on its physical properties, damage interactions, and item-specific behaviors.

## Core Entity Configuration

The Purple Egg is an `item_pickup` entity with several key tags defining its behavior:

*   `hittable`: Can be damaged by projectiles or other entities.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves according to physics simulation.
*   `egg_item`: Identifies it as a specific type of egg.
*   `item_pickup`: Can be picked up by the player.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics,egg_item,item_pickup" >
  <Base file="data/entities/base_item_projectile.xml" />
  <!-- ... other components ... -->
</Entity>
```

## Physical Properties

The egg has a physical presence defined by its `PhysicsBodyComponent` and `PhysicsImageShapeComponent`.

### PhysicsBodyComponent

Controls the fundamental physics simulation of the egg.

*   `is_bullet="1"`: Indicates it's a projectile-like object.
*   `hax_fix_going_through_ground="1"`: A fix to prevent it from falling through the ground.

```xml
<PhysicsBodyComponent
    _tags="enabled_in_world"
    uid="1"
    is_bullet="1"
    hax_fix_going_through_ground="1"
    >
</PhysicsBodyComponent>
```

### PhysicsImageShapeComponent

Defines the visual representation and collision shape.

*   `image_file="data/items_gfx/egg_purple.png"`: The sprite used for the egg.
*   `material="bone_box2d"`: The physics material, influencing its interaction with other physics objects.

```xml
<PhysicsImageShapeComponent
    body_id="1"
    centered="1"
    image_file="data/items_gfx/egg_purple.png"
    material="bone_box2d"
>
</PhysicsImageShapeComponent>
```

### PhysicsThrowableComponent

Enables the egg to be thrown by the player.

*   `max_throw_speed="180"`: The maximum speed it can be thrown.
*   `throw_force_coeff="1.5"`: A coefficient affecting throw force.

```xml
<PhysicsThrowableComponent
    max_throw_speed="180"
    throw_force_coeff="1.5"
>
</PhysicsThrowableComponent>
```

## Damage and Destruction Logic

The egg has specific behaviors when damaged or colliding with materials.

### DamageModelComponent

Defines how the egg reacts to damage and environmental effects.

*   `hp="0.6"`: The egg has low health.
*   `materials_damage="1"`: It can be damaged by certain materials.
*   `materials_that_damage="lava"`: Specifically, lava damages the egg.
*   `materials_how_much_damage="0.001"`: Lava deals minimal damage per tick.
*   `fire_damage_amount="0.2"`: Deals a small amount of fire damage if ignited.

```xml
<DamageModelComponent
    _tags="enabled_in_world"
    hp="0.6"
    materials_damage="1"
    materials_that_damage="lava"
    materials_how_much_damage="0.001"
    fire_damage_amount="0.2"
    >
</DamageModelComponent>
```

### ExplodeOnDamageComponent

Configures the explosion that occurs when the egg is destroyed.

*   `explode_on_death_percent="1"`: The egg always explodes upon death.
*   `physics_body_destruction_required="0.61"`: The explosion is triggered when 61% of its physics body is destroyed.
*   `load_this_entity="data/entities/projectiles/egg_purple.xml"`: This specifies the entity to spawn upon explosion, which is a separate projectile entity.
*   `damage="0"`: The explosion itself does not deal direct damage.
*   `camera_shake="10"`: Causes significant camera shake.
*   `explosion_radius="3"`: The radius of the explosion effect.
*   `physics_explosion_power.min="5"` / `physics_explosion_power.max="10"`: The force of the physics-based explosion.
*   `sparks_enabled="1"`: Sparks are generated.
*   `spark_material="bone"`: The sparks are of the "bone" material type.

```xml
<ExplodeOnDamageComponent
    _tags="enabled_in_world"
    explode_on_death_percent="1"
    physics_body_destruction_required="0.61"
    physics_body_modified_death_probability="1" >
    <config_explosion
      damage="0"
      camera_shake="10"
      explosion_radius="3"
      load_this_entity="data/entities/projectiles/egg_purple.xml"
      physics_explosion_power.min="5"
      physics_explosion_power.max="10"
      sparks_enabled="1"
      spark_material="bone"
      >
    </config_explosion>
</ExplodeOnDamageComponent>
```

### PhysicsBodyCollisionDamageComponent

Deals damage to other entities upon collision.

*   `speed_threshold="80.0"`: Damage is applied when the egg's speed exceeds 80.0.

```xml
<PhysicsBodyCollisionDamageComponent
    _tags="enabled_in_world"
    speed_threshold="80.0"
>
</PhysicsBodyCollisionDamageComponent>
```

## Item and UI Configuration

These components define the egg as a usable item in the player's inventory and UI.

### SpriteComponent

The sprite displayed when the item is held in hand.

*   `_enabled="0"`: This sprite is disabled by default, likely because it's primarily a projectile/throwable.
*   `image_file="data/items_gfx/egg_purple.png"`: The same sprite as its physical form.

```xml
<SpriteComponent
    _tags="enabled_in_hand"
    _enabled="0"
    offset_x="4"
    offset_y="4"
    image_file="data/items_gfx/egg_purple.png"
>
</SpriteComponent>
```

### ItemComponent

Defines the item's properties for inventory and gameplay.

*   `item_name="$item_egg_purple"`: The internal name for localization.
*   `is_pickable="1"`: Can be picked up.
*   `is_equipable_forced="1"`: Can be equipped directly.
*   `ui_sprite="data/ui_gfx/items/egg_purple.png"`: The icon displayed in the UI.
*   `ui_description="$item_description_egg_purple"`: The description text for localization.
*   `preferred_inventory="QUICK"`: Defaults to the quick inventory slot.

```xml
<ItemComponent
    _tags="enabled_in_world"
    item_name="$item_egg_purple"
    is_pickable="1"
    is_equipable_forced="1"
    ui_sprite="data/ui_gfx/items/egg_purple.png"
    ui_description="$item_description_egg_purple"
    preferred_inventory="QUICK"
>
</ItemComponent>
```

### UIInfoComponent

Provides basic UI information, primarily the name.

```xml
<UIInfoComponent
    _tags="enabled_in_world"
    name="$item_egg_purple" >
</UIInfoComponent>
```

### AbilityComponent

Grants the ability to be thrown as an item.

*   `throw_as_item="1"`: Enables throwing behavior.

```xml
<AbilityComponent
    ui_name="$item_egg_purple"
    throw_as_item="1"
>
</AbilityComponent>
```

## Visual Effects

### SpriteParticleEmitterComponent

Responsible for visual effects, likely related to its active state or when thrown.

*   `sprite_file="data/particles/ray.xml"`: Uses a "ray" particle effect.
*   `color.r="1" color.g="0.5" color.b="1" color.a="1.0"`: A purplish-pink color.
*   `color_change.a="-3.5"`: The alpha fades out over time.
*   `scale_velocity.x="-0.3" scale_velocity.y="3"`: The scale changes over its lifetime.
*   `emissive="1"` / `additive="1"`: The particles are emissive and use additive blending for a glowing effect.
*   `velocity_always_away_from_center="1"`: Particles are emitted outwards from the egg's center.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/ray.xml"
    color.r="1" color.g="0.5" color.b="1" color.a="1.0"
    color_change.a="-3.5"
    scale_velocity.x="-0.3" scale_velocity.y="3"
    emissive="1"
    additive="1"
    velocity_always_away_from_center="1">
</SpriteParticleEmitterComponent>
```

## Audio

### AudioComponent

Defines the sound effects associated with the item.

*   `file="data/audio/Desktop/projectiles.bank"`: Uses sounds from the projectiles audio bank.
*   `event_root="player_projectiles/throwable"`: Specifically uses sounds related to throwable player projectiles.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/throwable"
>
</AudioComponent>
```