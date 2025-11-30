---
title: Moon Item
category: entities
---

# Moon Item

This document details the `moon.xml` entity, which represents the "Moon" item in Noita. This item is a projectile that can be thrown and has unique visual and auditory effects.

## Core Components

### `Entity`
The root element for the Moon item. Key tags include:
- `hittable`: Allows the item to be affected by projectiles.
- `teleportable_NOT`: Prevents the item from being teleported.
- `item_pickup`: Identifies it as an item that can be picked up.
- `moon_energy`: A custom tag likely used for game logic related to this item.

### `Base`
- `file="data/entities/base_item_projectile.xml"`: Inherits fundamental properties of a projectile item.

## Physics and Movement

### `PhysicsBodyComponent`
Defines the physical properties of the Moon item.
- `uid="1"`: Unique identifier for the physics body.
- `allow_sleep="1"`: Allows the physics body to enter a sleep state when inactive.
- `angular_damping="0.6"`: Reduces rotational velocity over time.
- `linear_damping="0.2"`: Reduces linear velocity over time.
- `is_bullet="1"`: Indicates it's a projectile.
- `hax_fix_going_through_ground="1"`: A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`
Defines the visual shape and collision properties.
- `body_id="1"`: Links to the `PhysicsBodyComponent`.
- `is_circle="1"`: The collision shape is a circle.
- `image_file="data/items_gfx/moon.png"`: The sprite used for the item's physical representation.
- `material="item_box2d"`: The physics material.

### `PhysicsThrowableComponent`
Enables the item to be thrown.
- `max_throw_speed="90"`: Maximum speed when thrown.
- `throw_force_coeff="1.25"`: Coefficient for throw force.
- `min_torque="4"`: Minimum rotational force when thrown.
- `max_torque="10"`: Maximum rotational force when thrown.

### `VelocityComponent`
Controls the item's velocity and air resistance.
- `air_friction="0.8"`: How much air slows down the item.
- `terminal_velocity="150"`: The maximum falling speed.

## Item Properties

### `SpriteComponent`
Defines the visual representation when held in hand.
- `_enabled="0"`: Initially disabled, likely enabled by `LuaComponent`.
- `offset_x="4"`, `offset_y="4"`: Adjusts the sprite's position.
- `image_file="data/items_gfx/moon.png"`: The sprite for the held item.

### `ItemComponent`
Defines the item's behavior and metadata.
- `item_name="$item_moon"`: The internal name for the item (localized).
- `is_pickable="1"`: Allows the player to pick it up.
- `is_equipable_forced="1"`: Can be equipped directly.
- `ui_sprite="data/ui_gfx/items/moon.png"`: The sprite shown in the UI.
- `ui_description="$item_description_moon"`: The localized description.
- `preferred_inventory="QUICK"`: Suggests it should be placed in the quick inventory.

### `UIInfoComponent`
Provides information for the UI.
- `name="$item_moon"`: The name displayed in the UI.

### `AbilityComponent`
Grants abilities to the item.
- `throw_as_item="1"`: Allows it to be thrown as an item.
- `gun_config deck_capacity="0"`: Indicates it doesn't use a deck for spells.

## Visual Effects (FX)

### `SpriteParticleEmitterComponent`
Emits particles to create visual effects.
- `sprite_file="data/particles/ray.xml"`: Uses a ray particle sprite.
- `lifetime="1.5"`: Duration of emitted particles.
- `color.r="1" color.g="0.5" color.b="1" color.a="1.0"`: Initial color (pinkish).
- `color_change.a="-3.5"`: Alpha decreases over time.
- `scale.x="1" scale.y="0"`: Initial scale.
- `scale_velocity.x="-0.3" scale.y="3"`: Scale changes over time.
- `emissive="1"`, `additive="1"`: Particles are emissive and additive.
- `velocity_always_away_from_center="1"`: Particles move away from the item's center.

### `LightComponent`
Adds a light source.
- `radius="96"`: The radius of the light.
- `r="255" g="255" b="255"`: White light.
- `fade_out_time="0.2"`: How quickly the light fades.

### `ParticleEmitterComponent` (Multiple instances)
These components create various particle effects:
- **Attracted Particles**: Emits `spark_white` particles that are attracted to the item.
  - `emitted_material_name="spark_white"`
  - `area_circle_radius.max="96"`: Particles are emitted within this radius.
  - `attractor_force="12"`: Particles are pulled towards the item.
- **Outer Ring**: Emits `spark_white` particles in a ring around the item.
  - `area_circle_radius.min="96"`, `area_circle_radius.max="96"`: Emits particles at a specific radius.
- **Small Ring**: Emits `spark_white` particles in a smaller ring, with gravity.
  - `gravity.y="160.0"`: Particles are affected by gravity.
  - `area_circle_radius.min="4"`, `area_circle_radius.max="4"`: Emits particles close to the item.

## Scripting and Audio

### `LuaComponent`
Executes custom Lua scripts.
- `script_source_file="data/scripts/items/moon.lua"`: The script controlling the item's behavior.
- `execute_every_n_frame="1"`: The script runs every frame.

### `AudioLoopComponent` (Two instances)
Plays looping audio effects.
- One for when the item is in the world (`event_name="misc/moon/movement_loop_world"`).
- One for when the item is held in hand (`event_name="misc/moon/movement_loop_hand"`).
- `file="data/audio/Desktop/misc.bank"`: The audio bank containing the sounds.
- `auto_play="1"`: Audio starts automatically.
- `play_on_component_enable="1"`: Audio plays when the component is enabled.