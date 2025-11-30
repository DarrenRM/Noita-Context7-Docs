---
title: Holy Bomb Custom Card
category: entities
---

# Holy Bomb Custom Card

This document details the configuration for the "Holy Bomb" custom card entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The `bomb_holy.xml` file defines a custom card that, when used, throws a holy bomb projectile.

### Base Entity (`<Base>`)

This element inherits core functionality from `base_custom_card.xml`.

*   **`<ItemComponent>`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - Makes the item functional in both the game world and when held.
    *   `is_equipable_forced="1"`: Ensures the item can be equipped.

*   **`<SpriteComponent>` (for UI/World Icon)**:
    *   `image_file`: `data/ui_gfx/gun_actions/bomb_holy.png` - Specifies the visual representation of the card in the UI and world.

*   **`<ItemActionComponent>`**:
    *   `_tags`: `enabled_in_world` - Links the action to the game world.
    *   `action_id`: `BOMB_HOLY` - A unique identifier for this action.

### Transform and Handheld Sprite

*   **`<InheritTransformComponent>`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - Applies transform properties when the item is in the world or held.
    *   `parent_hotspot_tag`: `shoot_pos` - Defines the origin point for actions like throwing.

*   **`<SpriteComponent>` (for Handheld)**:
    *   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` - Controls visibility when held and prevents it from being placed in wands.
    *   `_enabled="0"`: Initially disabled, likely controlled by other tags.
    *   `offset_x`, `offset_y`: Adjusts the sprite's position when held.
    *   `image_file`: `data/items_gfx/in_hand/bomb_holy_in_hand.png` - The specific sprite for when the item is held.

## Ability and Projectile Configuration

### `<AbilityComponent>`

This component defines the primary behavior of the custom card.

*   `_tags`: `enabled_in_hand` - Activates the ability when the item is held.
*   `ui_name`: `$action_bomb_holy` - The display name for the action (localized).
*   `entity_file`: `data/entities/projectiles/bomb_holy.xml` - **Crucially**, this links the card to the actual holy bomb projectile entity that will be spawned.
*   `rotate_hand_amount`: `0.05` - Slight rotation applied to the hand when using the item.
*   `throw_as_item`: `1` - Indicates the projectile is thrown like an item.
*   `simulate_throw_as_item`: `1` - Simulates the physics of throwing an item.
*   `use_entity_file_as_projectile_info_proxy`: `1` - Uses the projectile's entity file for additional information.
*   **`<gun_config>`**:
    *   `deck_capacity`: `0` - This card does not contribute to wand deck capacity.

## Particle Effects

The following components define visual particle effects associated with the card.

### `<SpriteParticleEmitterComponent>`

Generates spark-like particles.

*   `_tags`: `enabled_in_hand`, `item_identified`, `enabled_in_world` - Controls when these particles are active.
*   `sprite_file`: `data/particles/spark_particle.xml` - The particle sprite to use.
*   `delay`, `lifetime`: Set to `0`, suggesting these are instantaneous or managed by other components.
*   `color.r`, `color.g`, `color.b`, `color.a`: White color.
*   `velocity.x`, `velocity.y`, `gravity.x`, `gravity.y`: Defines initial movement and gravity.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the rate of particle emission.
*   `count_min`, `count_max`: Emits a single particle per emission cycle.
*   `randomize_rotation`, `randomize_position`, `randomize_velocity`: Adds variation to particle appearance and movement.

### `<ParticleEmitterComponent>`

Generates smoke particles.

*   `_tags`: `enabled_in_hand`, `item_identified` - Controls when these particles are active.
*   `emitted_material_name`: `smoke` - Specifies the type of particle material.
*   `offset.x`, `offset.y`, `x_pos_offset_min/max`, `y_pos_offset_min/max`: Defines the emission area relative to the card.
*   `x_vel_min/max`, `y_vel_min/max`: Sets the initial velocity range for smoke particles.
*   `count_min`, `count_max`: Emits a single particle per emission cycle.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Influences how particles interact with air.
*   `lifetime_min`, `lifetime_max`: Duration of the smoke particles.
*   `create_real_particles`, `emit_cosmetic_particles`: Indicates these are visible, functional particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the rate of smoke emission.
*   `is_emitting`: `1` - Ensures the emitter is active.