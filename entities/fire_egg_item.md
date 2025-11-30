---
title: Fire Egg Item
category: entities
---

# Fire Egg Item

This document details the `egg_fire.xml` entity, representing a throwable fire egg item in Noita.

## Core Functionality

The Fire Egg is a projectile item that, upon impact or destruction, triggers an explosion with fire-based effects. It's designed to be thrown and deals damage upon collision or when its health is depleted.

## Key Components

### `PhysicsBodyComponent`
Manages the physical properties of the egg, including its interaction with the game world.
- `is_bullet`: Set to `1`, indicating it behaves as a projectile.
- `hax_fix_going_through_ground`: Set to `1` to prevent it from falling through terrain.

### `PhysicsImageShapeComponent`
Defines the visual representation and collision shape of the egg.
- `image_file`: `data/items_gfx/egg_red.png` - Specifies the sprite for the egg.
- `material`: `bone_box2d` - The physics material used for collision.

### `PhysicsThrowableComponent`
Enables the egg to be thrown by the player.
- `max_throw_speed`: `180` - Maximum speed when thrown.
- `throw_force_coeff`: `1.5` - Coefficient affecting throw force.

### `DamageModelComponent`
Handles damage-related aspects of the egg.
- `fire_damage_amount`: `0.2` - The amount of fire damage dealt by the egg.
- `hp`: `0.6` - The health of the egg before it breaks.
- `materials_damage`: `lava` - Specifies that certain materials can damage the egg.
- `materials_how_much_damage`: `0.001` - The damage taken from specified materials.

### `ExplodeOnDamageComponent`
Defines the explosion behavior when the egg is damaged or destroyed.
- `explode_on_death_percent`: `1` - The egg will always explode when its health reaches zero.
- `physics_body_destruction_required`: `0.61` - The threshold of damage required to trigger the explosion.
- `load_this_entity`: `data/entities/projectiles/egg_fire.xml` - The entity to spawn upon explosion, creating a secondary fire projectile.
- `damage`: `0` - The direct damage of the explosion itself (the spawned projectile handles damage).
- `camera_shake`: `10` - The intensity of camera shake upon explosion.
- `explosion_radius`: `3` - The radius of the explosion.
- `physics_explosion_power.min`/`max`: `5`/`10` - The minimum and maximum force of the physics-based explosion.
- `sparks_enabled`: `1` - Enables sparks to be emitted from the explosion.
- `spark_material`: `bone` - The material of the sparks.

### `ItemComponent`
Defines the item's properties for inventory and interaction.
- `item_name`: `$item_egg_fire` - The internal name for the item.
- `is_pickable`: `1` - Allows the item to be picked up.
- `is_equipable_forced`: `1` - Can be equipped directly.
- `ui_sprite`: `data/ui_gfx/items/egg_red.png` - The sprite displayed in the UI.
- `ui_description`: `$item_description_egg_fire` - The description text for the item.
- `preferred_inventory`: `QUICK` - The preferred inventory slot.

### `SpriteParticleEmitterComponent`
Responsible for visual particle effects associated with the egg.
- `sprite_file`: `data/particles/ray.xml` - The sprite used for particles.
- `lifetime`: `1.5` - Duration of the particle effect.
- `color.r`/`g`/`b`/`a`: `1`/`0.5`/`1`/`1.0` - Initial color of the particles.
- `color_change.a`: `-3.5` - Alpha fade rate of the particles.
- `scale_velocity.x`/`y`: `-0.3`/`3` - How the scale of particles changes over time.
- `emission_interval_min_frames`/`max_frames`: `3`/`6` - Controls the rate of particle emission.
- `emissive`: `1` - Particles emit light.
- `additive`: `1` - Particles use additive blending.
- `randomize_position`/`velocity`: Various settings to distribute particles randomly around the egg.

### `AudioComponent`
Manages sound effects for the item.
- `file`: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
- `event_root`: `player_projectiles/throwable` - The root event for throwable projectile sounds.