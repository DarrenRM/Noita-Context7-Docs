---
title: Slime Egg Item
category: entities
---

# Slime Egg Item

This document details the `egg_slime.xml` entity, representing a throwable slime egg item in Noita.

## Core Functionality

The Slime Egg is a throwable item that, upon taking sufficient damage or colliding with sufficient force, explodes. This explosion spawns a new entity defined by `data/entities/projectiles/egg_slime.xml`, which is likely the actual slime projectile.

## Key Components and Attributes

### `Entity` Tags
- `hittable`: Can be damaged by projectiles and other entities.
- `teleportable_NOT`: Cannot be teleported.
- `item_physics`: Behaves like a physics-enabled item.
- `egg_item`: Identifies it as an egg-type item.
- `item_pickup`: Can be picked up by the player.

### `PhysicsBodyComponent`
- `is_bullet="1"`: Indicates it's a projectile-like physics object.
- `hax_fix_going_through_ground="1"`: A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`
- `image_file="data/items_gfx/egg_slime.png"`: The visual sprite for the egg when it's in the world.
- `material="bone_box2d"`: The physics material used for collision.

### `PhysicsThrowableComponent`
- `max_throw_speed="180"`: The maximum speed it can be thrown.
- `throw_force_coeff="1.5"`: The coefficient for calculating throw force.

### `DamageModelComponent`
- `hp="0.6"`: The health of the egg before it breaks.
- `fire_damage_amount="0.2"`: Small amount of damage taken from fire.
- `materials_that_damage="lava"`: Specifies that lava damages this entity.
- `materials_how_much_damage="0.001"`: The rate at which lava damages it.

### `ExplodeOnDamageComponent`
- `explode_on_death_percent="1"`: Guarantees an explosion when its HP reaches zero.
- `physics_body_destruction_required="0.61"`: The threshold of physics body destruction needed to trigger the explosion.
- `load_this_entity="data/entities/projectiles/egg_slime.xml"`: **Crucially, this defines the entity that is spawned upon explosion.**

#### `config_explosion`
- `camera_shake="10"`: The intensity of camera shake upon explosion.
- `explosion_radius="3"`: The radius of the explosion effect.
- `physics_explosion_power.min="5"` and `physics_explosion_power.max="10"`: The force of the physics-based explosion.
- `sparks_enabled="1"`: Enables spark effects.
- `spark_material="bone"`: The material used for sparks.
- `stains_enabled="1"`: Enables stain effects on the ground.

### `PhysicsBodyCollisionDamageComponent`
- `speed_threshold="80.0"`: Triggers damage to itself if it collides with enough speed.

### `SpriteComponent` (for hand/inventory)
- `image_file="data/items_gfx/egg_slime.png"`: The visual sprite when held or in the inventory.

### `ItemComponent`
- `item_name="$item_egg_slime"`: The internal name for the item.
- `is_pickable="1"`: Allows the player to pick it up.
- `is_equipable_forced="1"`: Can be equipped directly.
- `ui_sprite="data/ui_gfx/items/egg_slime.png"`: The sprite shown in the UI.
- `ui_description="$item_description_egg_slime"`: The description text for the item.
- `preferred_inventory="QUICK"`: Suggests it should be placed in the quick inventory.

### `AbilityComponent`
- `throw_as_item="1"`: Confirms it can be thrown as an item.

### `SpriteParticleEmitterComponent`
- This component is responsible for the visual particle effects associated with the egg, likely a subtle glow or trail.

### `AudioComponent`
- `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
- `event_root="player_projectiles/throwable"`: The root event for throwable projectile sounds.