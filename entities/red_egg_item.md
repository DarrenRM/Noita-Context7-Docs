---
title: Red Egg Item
category: entities
---

# Red Egg Item

This document details the configuration of the Red Egg item in Noita, focusing on its physical properties, interaction mechanics, and visual/audio components.

## Core Entity Configuration

The Red Egg is an `item_pickup` entity with several key tags defining its behavior:

*   `hittable`: Can be damaged by projectiles or other entities.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves according to physics simulation.
*   `egg_item`: Specific tag for egg-type items.
*   `item_pickup`: Indicates it can be picked up by the player.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics,egg_item,item_pickup" >
  <Base file="data/entities/base_item_projectile.xml" />
  <!-- ... other components ... -->
</Entity>
```

## Physics and Collision

The egg has standard physics properties for an item that can be thrown and interact with the world.

### PhysicsBodyComponent

Defines the physical presence and behavior in the world.

*   `is_bullet="1"`: Allows it to be treated as a projectile in some physics contexts.
*   `hax_fix_going_through_ground="1"`: A fix to prevent it from falling through the ground.
*   `auto_clean="0"`: Prevents automatic removal from the world.

```xml
<PhysicsBodyComponent
    _tags="enabled_in_world"
    uid="1"
    allow_sleep="1"
    angular_damping="0"
    fixed_rotation="0"
    is_bullet="1"
    linear_damping="0"
    auto_clean="0"
    on_death_leave_physics_body="0"
    hax_fix_going_through_ground="1"
  ></PhysicsBodyComponent>
```

### PhysicsImageShapeComponent

Defines the visual shape and material for physics interactions.

*   `image_file="data/items_gfx/egg_red.png"`: The sprite used for the egg's physical form.
*   `material="bone_box2d"`: The physics material, influencing friction and other properties.

```xml
<PhysicsImageShapeComponent
    body_id="1"
    centered="1"
    image_file="data/items_gfx/egg_red.png"
    material="bone_box2d"
  ></PhysicsImageShapeComponent>
```

### PhysicsThrowableComponent

Enables the egg to be thrown by the player.

*   `max_throw_speed="180"`: The maximum speed the egg can be thrown.
*   `throw_force_coeff="1.5"`: A coefficient affecting the force applied when throwing.

```xml
<PhysicsThrowableComponent
    max_throw_speed="180"
    throw_force_coeff="1.5"
  ></PhysicsThrowableComponent>
```

### PhysicsBodyCollisionDamageComponent

Applies damage to other entities upon collision if a certain speed threshold is met.

*   `speed_threshold="80.0"`: The minimum speed required to deal collision damage.

```xml
<PhysicsBodyCollisionDamageComponent
    _tags="enabled_in_world"
    speed_threshold="80.0"
  ></PhysicsBodyCollisionDamageComponent>
```

## Damage and Destruction

The egg has a low health pool and can explode when damaged.

### DamageModelComponent

Defines the health and damage resistances of the egg.

*   `hp="0.6"`: The egg's health.
*   `fire_damage_amount="0.2"`: Amount of fire damage it can take.
*   `materials_damage="1"`: Indicates it can be damaged by certain materials.
*   `materials_that_damage="lava"`: Specifies that lava is one of the damaging materials.
*   `materials_how_much_damage="0.001"`: The rate of damage from specified materials.

```xml
<DamageModelComponent
    _tags="enabled_in_world"
    air_needed="0"
    blood_material=""
    drop_items_on_death="0"
    falling_damages="0"
    fire_damage_amount="0.2"
    fire_probability_of_ignition="0"
    critical_damage_resistance="1"
    hp="0.6"
    is_on_fire="0"
    materials_create_messages="0"
    materials_damage="1"
    materials_that_damage="lava"
    materials_how_much_damage="0.001"
    ragdoll_filenames_file=""
    ragdoll_material=""
  ></DamageModelComponent>
```

### ExplodeOnDamageComponent

Configures the explosion behavior when the egg is damaged.

*   `explode_on_death_percent="1"`: The egg will always explode upon reaching 0 HP.
*   `physics_body_destruction_required="0.61"`: The threshold of physics body destruction that triggers the explosion.
*   `load_this_entity="data/entities/projectiles/egg_red.xml"`: Specifies the entity to spawn upon explosion (likely a projectile or effect).
*   `camera_shake="10"`: The intensity of camera shake during the explosion.
*   `explosion_radius="3"`: The radius of the explosion effect.
*   `physics_explosion_power.min="5"` and `physics_explosion_power.max="10"`: The range of physics force applied by the explosion.
*   `sparks_enabled="1"`: Enables sparks as part of the explosion effect.
*   `spark_material="bone"`: The material of the sparks.

```xml
<ExplodeOnDamageComponent
    _tags="enabled_in_world"
    explode_on_death_percent="1"
    explode_on_damage_percent="0"
    physics_body_destruction_required="0.61"
    physics_body_modified_death_probability="1" >
    <config_explosion
      never_cache="0"
      damage="0"
      camera_shake="10"
      explosion_radius="3"
      explosion_sprite=""
      explosion_sprite_lifetime="10"
	  load_this_entity="data/entities/projectiles/egg_red.xml"
      hole_destroy_liquid="0"
      hole_enabled="0"
      ray_energy="100000"
      particle_effect="0"
      damage_mortals="1"
      physics_explosion_power.min="5"
      physics_explosion_power.max="10"
      shake_vegetation="1"
      sparks_count_min="10"
      sparks_count_max="20"
      sparks_enabled="1"
	  spark_material="bone"
      stains_enabled="1"
      stains_radius="0" >
    </config_explosion>
  </ExplodeOnDamageComponent>
```

## Item and UI Integration

This section covers how the egg is presented and interacted with as an item in the player's inventory and hand.

### SpriteComponent

Defines the visual representation of the egg when held in the hand.

*   `_enabled="0"`: This sprite is disabled by default, likely because the `enabled_in_world` tag controls its visibility.
*   `image_file="data/items_gfx/egg_red.png"`: The sprite for the egg when held.

```xml
<SpriteComponent
    _tags="enabled_in_hand"
    _enabled="0"
    offset_x="4"
    offset_y="4"
    image_file="data/items_gfx/egg_red.png"
  ></SpriteComponent>
```

### ItemComponent

Core component for defining item properties, including its name, pickability, and UI representation.

*   `item_name="$item_egg"`: The internal name for the item, likely linked to a localization string.
*   `is_pickable="1"`: Allows the player to pick up the item.
*   `is_equipable_forced="1"`: Can be equipped directly.
*   `ui_sprite="data/ui_gfx/items/egg_red.png"`: The sprite displayed in the UI.
*   `ui_description="$item_description_egg"`: The description text, linked to localization.
*   `preferred_inventory="QUICK"`: Suggests it should be placed in the quick inventory.

```xml
<ItemComponent
    _tags="enabled_in_world"
    item_name="$item_egg"
    max_child_items="0"
    is_pickable="1"
    is_equipable_forced="1"
    ui_sprite="data/ui_gfx/items/egg_red.png"
    ui_description="$item_description_egg"
    preferred_inventory="QUICK"
  ></ItemComponent>
```

### UIInfoComponent

Provides information for UI elements, such as the item's name.

*   `name="$item_egg"`: The name displayed in UI elements.

```xml
<UIInfoComponent
    _tags="enabled_in_world"
    name="$item_egg" >
  </UIInfoComponent>
```

### AbilityComponent

Grants the item abilities, in this case, the ability to be thrown as an item.

*   `throw_as_item="1"`: Allows the item to be thrown.

```xml
<AbilityComponent
		ui_name="$item_egg"
		throw_as_item="1"
		><gun_config
			deck_capacity="0"
		></gun_config>
	</AbilityComponent>
```

## Visual and Audio Effects

### SpriteParticleEmitterComponent

Responsible for emitting particles, likely for a visual effect when the egg is active or interacting.

*   `sprite_file="data/particles/ray.xml"`: Uses a "ray" particle effect.
*   `lifetime="1.5"`: The duration of the particle effect.
*   `color.r="1" color.g="0.5" color.b="1" color.a="1.0"`: Initial color (pinkish).
*   `color_change.a="-3.5"`: The alpha value decreases over time.
*   `scale_velocity.y="3"`: The scale of the particles increases over time.
*   `emissive="1"` and `additive="1"`: The particles are emissive and additive, making them bright.
*   `randomize_velocity`: Particles are emitted with randomized velocities.

```xml
<SpriteParticleEmitterComponent
		sprite_file="data/particles/ray.xml"
		delay="0"
		lifetime="1.5"
		color.r="1" color.g="0.5" color.b="1" color.a="1.0"
		color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-3.5"
		velocity.x="0" velocity.y="0"
		gravity.x="0" gravity.y="0"
		velocity_slowdown="0"
		rotation="0"
		angular_velocity="0"
		scale.x="1" scale.y="0"
		scale_velocity.x="-0.3" scale_velocity.y="3"
		emission_interval_min_frames="3"
		emission_interval_max_frames="6"
		emissive="1"
		additive="1"
		count_min="1" count_max="1"
		use_velocity_as_rotation="1"
		randomize_position.min_x="-2"
		randomize_position.max_x="2"
		randomize_position.min_y="-2"
		randomize_position.max_y="2"
		randomize_velocity.min_x="-30"
		randomize_velocity.max_x="30"
		randomize_velocity.min_y="-30"
		randomize_velocity.max_y="30"
		velocity_always_away_from_center="1">
	</SpriteParticleEmitterComponent>
```

### AudioComponent

Defines the sound effects associated with the egg.

*   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
*   `event_root="player_projectiles/throwable"`: Sets the root event for throwable projectiles.

```xml
<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/throwable"
		>
	</AudioComponent>
```