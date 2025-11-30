---
title: Base Explosive Card Components
category: data/entities
---

# Base Explosive Card Components

This document details the components used in the `base_explosive.xml` entity, which serves as a foundational element for explosive-related cards in Noita modding. It focuses on particle emitters that create visual and cosmetic effects when the card is held or identified.

## Entity Structure

The `base_explosive.xml` entity primarily utilizes two particle emitter components to generate visual feedback.

```xml
<Entity>
	<!-- InheritTransformComponent -->
	<!-- SpriteParticleEmitterComponent -->
	<!-- ParticleEmitterComponent -->
</Entity>
```

## Key Components

### InheritTransformComponent

This component is crucial for defining how the entity's transform (position, rotation, scale) is inherited from its parent.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - Indicates the entity is active when in the game world or held by the player.
*   **`parent_hotspot_tag`**: `shoot_pos` - Specifies that the entity's transform should align with the `shoot_pos` hotspot of its parent. This is common for items held in hand.

### SpriteParticleEmitterComponent

This component is responsible for emitting sprite-based particles, contributing to visual effects like sparks.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The emitter is active when the item is held or identified.
*   **`sprite_file`**: `data/particles/spark_particle.xml` - References the sprite definition for the emitted particles.
*   **`delay`**: `0` - No initial delay before emission starts.
*   **`lifetime`**: `0` - Particles have a very short or instantaneous lifetime, suggesting they are for immediate visual flair.
*   **Color Properties**:
    *   `color.r="1" color.g="1" color.b="1" color.a="1"` - Sets the initial color to white.
    *   `color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="0"` - No color change over the particle's lifetime.
*   **Velocity Properties**:
    *   `velocity.x="0" velocity.y="0"` - Initial velocity is zero.
    *   `gravity.x="0" gravity.y="-40"` - Particles are affected by gravity, pulling them downwards.
*   **Emission Control**:
    *   `emission_interval_min_frames="4"`
    *   `emission_interval_max_frames="15"` - Controls the timing between particle emissions.
    *   `count_min="1"`
    *   `count_max="1"` - Emits a single particle per emission cycle.
*   **Randomization**:
    *   `randomize_rotation.min="-3.1415"`
    *   `randomize_rotation.max="3.1415"` - Randomizes particle rotation.
    *   `randomize_position.min_x="-2"`
    *   `randomize_position.max_x="2"`
    *   `randomize_position.min_y="-2"`
    *   `randomize_position.max_y="2"` - Randomizes particle spawn position within a small area.
    *   `randomize_velocity.min_x="-8"`
    *   `randomize_velocity.max_x="8"`
    *   `randomize_velocity.min_y="-24"`
    *   `randomize_velocity.max_y="8"` - Randomizes particle initial velocity, giving them upward and outward motion.

### ParticleEmitterComponent

This component emits material-based particles, often used for effects like smoke or fire.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The emitter is active when the item is held or identified.
*   **`emitted_material_name`**: `smoke` - Specifies that the emitted particles are of the "smoke" material type.
*   **Offset and Position**:
    *   `offset.x="0" offset.y="0"` - No base offset from the emitter's origin.
    *   `x_pos_offset_min="-3"`
    *   `x_pos_offset_max="3"`
    *   `y_pos_offset_min="1"`
    *   `y_pos_offset_max="-1"` - Randomizes the spawn position of smoke particles around the emitter.
*   **Velocity**:
    *   `x_vel_min="-2"`
    *   `x_vel_max="2"`
    *   `y_vel_min="-20"`
    *   `y_vel_max="-10"` - Gives smoke particles an upward and slightly outward velocity.
*   **Emission Control**:
    *   `count_min="1"`
    *   `count_max="1"` - Emits a single particle per emission cycle.
    *   `lifetime_min="0.2"`
    *   `lifetime_max="0.3"` - Smoke particles have a short lifespan.
    *   `emission_interval_min_frames="5"`
    *   `emission_interval_max_frames="12"` - Controls the timing between smoke particle emissions.
*   **Particle Type**:
    *   `create_real_particles="1"` - Creates actual game particles.
    *   `emit_cosmetic_particles="1"` - Also emits cosmetic particles, potentially for visual enhancement.
*   **`is_emitting`**: `1` - The emitter is active.