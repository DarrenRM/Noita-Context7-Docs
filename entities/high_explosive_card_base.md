---
title: High Explosive Card Base
category: entities
---

---

# High Explosive Card Base

This document details the base configuration for the "High Explosive" custom card entity in Noita, focusing on its visual and particle effects when held.

## Entity Structure

The entity is defined by the `<Entity>` tag.

## Key Components

### InheritTransformComponent

This component handles the entity's position and visibility.

*   **`_tags`**: `enabled_in_world,enabled_in_hand` - The entity is active both in the game world and when held by the player.
*   **`Transform`**:
    *   `position.x`: `8` - Relative X-axis offset.
    *   `position.y`: `0` - Relative Y-axis offset.

### SpriteParticleEmitterComponent

This component defines a particle effect that uses a sprite.

*   **`_tags`**: `enabled_in_hand,item_identified` - The effect is active when the item is held and identified.
*   **`sprite_file`**: `data/particles/tinyspark_01.xml` - Specifies the sprite used for the particles.
*   **`delay`**: `0` - No initial delay before emission.
*   **`lifetime`**: `0` - Particles have no inherent lifetime from this component.
*   **`color`**: `r="1" g="1" b="1" a="1"` - White color.
*   **`color_change`**: `r="0" g="0" b="0" a="0"` - No color change over time.
*   **`velocity`**: `x="0" y="0"` - Initial velocity is zero.
*   **`gravity`**: `x="0" y="-40"` - Particles are affected by gravity pulling them downwards.
*   **`emission_interval_min_frames`**: `4` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `15` - Maximum frames between particle emissions.
*   **`count_min`**: `1` - Minimum particles emitted per interval.
*   **`count_max`**: `1` - Maximum particles emitted per interval.
*   **`randomize_rotation`**: `min="-3.1415" max="3.1415"` - Randomizes particle rotation within a full circle.
*   **`randomize_position`**: `min_x="-2" max_x="2" min_y="-2" max_y="2"` - Randomizes particle spawn position within a small area.
*   **`randomize_velocity`**: `min_x="-8" max_x="8" min_y="-24" max_y="8"` - Randomizes particle velocity, with a strong downward bias.

### ParticleEmitterComponent

This component defines a more general particle effect.

*   **`_tags`**: `enabled_in_hand,item_identified` - The effect is active when the item is held and identified.
*   **`emitted_material_name`**: `spark` - The material type of the emitted particles.
*   **`offset`**: `x="0" y="0"` - Emission origin relative to the entity.
*   **`x_pos_offset_min`**: `-3`
*   **`x_pos_offset_max`**: `3`
*   **`y_pos_offset_min`**: `1`
*   **`y_pos_offset_max`**: `-1` - Defines the area where particles are emitted.
*   **`x_vel_min`**: `-2`
*   **`x_vel_max`**: `2`
*   **`y_vel_min`**: `-20`
*   **`y_vel_max`**: `-10` - Defines the velocity range for emitted particles, with a strong downward component.
*   **`count_min`**: `1` - Minimum particles emitted per interval.
*   **`count_max`**: `2` - Maximum particles emitted per interval.
*   **`lifetime_min`**: `0.6` - Minimum particle lifetime in seconds.
*   **`lifetime_max`**: `0.8` - Maximum particle lifetime in seconds.
*   **`create_real_particles`**: `0` - These are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles`**: `1` - Explicitly marks these as cosmetic.
*   **`emission_interval_min_frames`**: `5` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `12` - Maximum frames between particle emissions.
*   **`is_emitting`**: `1` - The emitter is active.