---
title: Holy Giga Bomb Custom Card
category: data/entities
---

---

# Holy Giga Bomb Custom Card

This document details the configuration for the "Holy Giga Bomb" custom card in Noita, intended for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the base object.

### Base Component (`<Base>`)

This component inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

*   **`<ItemComponent>`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - Makes the card usable in the game world and when held.
    *   `is_equipable_forced="1"`: Ensures the card can be equipped.

*   **`<SpriteComponent>`**:
    *   `image_file`: `data/ui_gfx/gun_actions/bomb_holy_giga.png` - Specifies the UI icon for the card.

*   **`<ItemActionComponent>`**:
    *   `_tags`: `enabled_in_world` - Links the card to its action in the game world.
    *   `action_id`: `BOMB_HOLY_GIGA` - A unique identifier for this action.

### Transform Component (`<InheritTransformComponent>`)

*   `_tags`: `enabled_in_world`, `enabled_in_hand` - Applies transform properties when the card is in the world or hand.
*   `parent_hotspot_tag`: `shoot_pos` - Defines the origin point for actions related to shooting or throwing.

### In-Hand Sprite (`<SpriteComponent>`)

This component defines the visual representation of the card when held by the player.

*   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` - Visible when held, not when part of a wand.
*   `_enabled="0"`: This sprite is initially disabled, likely to be overridden by the `base_custom_card.xml` logic.
*   `offset_x="11"`, `offset_y="26"`: Adjusts the sprite's position relative to the hand.
*   `image_file`: `data/items_gfx/in_hand/bomb_holy_giga_in_hand.png` - The specific sprite for the card in hand.

### Ability Component (`<AbilityComponent>`)

This is the primary component defining the card's functionality.

*   `_tags`: `enabled_in_hand` - The ability is active when the card is held.
*   `ui_name`: `$action_bomb_holy_giga` - The in-game name displayed to the player (localized).
*   `entity_file`: `data/entities/projectiles/bomb_holy_giga.xml` - Specifies the entity file for the projectile that is spawned.
*   `rotate_hand_amount`: `0.05` - Controls how much the player's hand rotates when using the card.
*   `throw_as_item`: `1` - Indicates the projectile is thrown like an item.
*   `simulate_throw_as_item`: `1` - Simulates the physics of throwing an item.
*   `use_entity_file_as_projectile_info_proxy`: `1` - Uses the projectile's entity file for its properties.
*   **`<gun_config>`**:
    *   `deck_capacity`: `0` - This card does not contribute to wand deck capacity.

## Particle Effects

These components add visual flair to the card.

### Spark Particle Emitter (`<SpriteParticleEmitterComponent>`)

*   `_tags`: `enabled_in_hand`, `item_identified`, `enabled_in_world` - Active when held, identified, or in the world.
*   `sprite_file`: `data/particles/spark_particle.xml` - Uses a predefined spark particle effect.
*   `delay`, `lifetime`, `color`, `velocity`, `gravity`, `scale`: Standard particle emission parameters.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the rate of particle emission.
*   `count_min`, `count_max`: Number of particles emitted per burst.
*   `randomize_rotation`, `randomize_position`, `randomize_velocity`: Parameters for varying particle behavior.

### Smoke Particle Emitter (`<ParticleEmitterComponent>`)

*   `_tags`: `enabled_in_hand`, `item_identified` - Active when held and identified.
*   `emitted_material_name`: `smoke` - Specifies the material for the emitted particles.
*   `offset.x`, `offset.y`: Position offset for particle emission.
*   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Range for particle spawn position.
*   `x_vel_min/max`, `y_vel_min/max`: Velocity range for emitted particles.
*   `count_min`, `count_max`: Number of particles emitted.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters related to airflow affecting particles.
*   `lifetime_min`, `lifetime_max`: Duration particles exist.
*   `create_real_particles`: `1` - Creates actual game particles.
*   `emit_cosmetic_particles`: `1` - Emits cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls emission frequency.
*   `is_emitting`: `1` - The emitter is active.