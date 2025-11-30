---
title: Jar Item Entity
category: entities
---

# Jar Item Entity

This document describes the `jar.xml` entity, which defines the properties and behavior of a jar item in Noita. Jars are pickable items that can be held and potentially used in various ways.

## Core Components

The `jar.xml` entity inherits from `potion.xml`, suggesting a shared base functionality for consumable or container-like items.

### `Entity`

The root element defining the entity with several key tags:
*   `hittable`: The entity can be damaged or affected by impacts.
*   `teleportable_NOT`: The entity cannot be teleported.
*   `item_physics`: The entity interacts with the physics engine.
*   `item_pickup`: The entity is designed to be picked up by the player.

### `Base`

*   `file="data/entities/items/pickup/potion.xml"`: Inherits properties and behaviors from the base potion entity.

### `PhysicsBodyComponent`

*   `on_death_leave_physics_body="0"`: When the entity is destroyed, its physics body is removed.

### `ExplodeOnDamageComponent`

*   `_tags="enabled_in_world"`: This component is active when the entity is in the game world.
*   `_enabled="0"`: The explosion behavior is disabled by default.

### `PhysicsImageShapeComponent`

Defines the physical shape and appearance of the jar in the game world.
*   `body_id="1"`: Identifier for the physics body.
*   `centered="1"`: The image is centered on the physics body.
*   `image_file="data/items_gfx/jar_normals.png"`: The texture file used for the jar's normal appearance.
*   `material="potion_glass_box2d"`: The physics material applied to the jar, likely influencing its interaction with other objects.

### `SpriteComponent`

Defines the visual representation of the jar when held by the player.
*   `_tags="enabled_in_hand"`: This sprite is visible when the item is held.
*   `_enabled="0"`: The sprite is disabled by default, likely meaning it's shown when the item is equipped.
*   `offset_x="4"`, `offset_y="4"`: Adjusts the position of the sprite relative to its origin.
*   `image_file="data/items_gfx/jar.png"`: The texture file for the jar's sprite when held.

### `ItemComponent`

Defines the item-specific properties.
*   `item_name="$item_jar"`: The internal name of the item, likely linked to localization for display.
*   `max_child_items="0"`: The jar cannot hold other items internally.
*   `is_pickable="1"`: The item can be picked up by the player.
*   `is_equipable_forced="1"`: The item can be forced into an equipment slot.
*   `ui_sprite="data/ui_gfx/items/jar.png"`: The sprite used for the item in the UI (inventory, hotbar).
*   `ui_description="$item_description_jar"`: The description text for the item, linked to localization.
*   `preferred_inventory="QUICK"`: The item is preferred to be placed in the quick inventory slot.

### `AbilityComponent`

Defines abilities associated with the item.
*   `ui_name="$item_jar_with_material"`: The UI name when the jar is associated with a material, suggesting it can hold or interact with substances.
*   `throw_as_item="1"`: The jar can be thrown as a distinct item.
*   `gun_config`: Configuration for how the item behaves when used as a "gun" (e.g., thrown).
    *   `deck_capacity="0"`: The jar does not have a deck capacity, meaning it cannot hold multiple spells or effects in this context.

### `SpriteParticleEmitterComponent`

This component is responsible for emitting particles, likely for visual effects when the jar is interacted with or used.
*   `sprite_file="data/particles/ray.xml"`: Uses a "ray" particle effect.
*   `delay="0"`: Particles are emitted immediately.
*   `lifetime="1.5"`: Particles last for 1.5 seconds.
*   `color.r="1" color.g="0.5" color.b="1" color.a="1.0"`: Initial color (pinkish-purple).
*   `color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-3.5"`: Alpha value decreases over time.
*   `velocity.x="0" velocity.y="0"`: Initial velocity is zero.
*   `gravity.x="0" gravity.y="0"`: No gravity applied to particles.
*   `scale.x="1" scale.y="0"`: Initial scale.
*   `scale_velocity.x="-0.3" scale_velocity.y="3"`: Scale changes over time.
*   `emission_interval_min_frames="3"`, `emission_interval_max_frames="6"`: Particles are emitted every 3-6 frames.
*   `emissive="1"`, `additive="1"`: Particles are emissive and use additive blending for brightness.
*   `count_min="1"`, `count_max="1"`: Emits 1 particle per emission.
*   `use_velocity_as_rotation="1"`: Particle rotation is based on their velocity.
*   `randomize_position.min_x="-2"`, `randomize_position.max_x="2"`, `randomize_position.min_y="-2"`, `randomize_position.max_y="2"`: Particles spawn within a small radius.
*   `randomize_velocity.min_x="-30"`, `randomize_velocity.max_x="30"`, `randomize_velocity.min_y="-30"`, `randomize_velocity.max_y="30"`: Particles have randomized initial velocity.
*   `velocity_always_away_from_center="1"`: Particles are always emitted away from the center of the emitter.