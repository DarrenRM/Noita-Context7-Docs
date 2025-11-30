---
title: Berserk Card
category: data/entities
---

# Berserk Card

This document describes the `berserk.xml` entity, which defines the "Berserk" wand card in Noita. This card, when equipped, visually enhances the wand with a particle effect and is associated with the `BERSERK` action ID.

## Base Entity

The `Berserk` card inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

### Sprite Component

This component defines the visual representation of the Berserk card in the UI.

*   **`image_file`**: `data/ui_gfx/gun_actions/berserk.png` - Specifies the image used for the card's icon.

### Item Action Component

This component links the card to a specific in-game action.

*   **`_tags`**: `enabled_in_world` - Indicates that this action is available when the item is in the game world.
*   **`action_id`**: `BERSERK` - The unique identifier for the Berserk action.

## Inherit Transform Component

This component handles the positioning and visibility of the card when held.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - Ensures the transform is active when the item is in the world and being held.
*   **`Transform`**:
    *   **`position.x`**: `8` - X-axis offset.
    *   **`position.y`**: `0` - Y-axis offset.

## Sprite Particle Emitter Component

This component generates a visual particle effect associated with the Berserk card when it's held and identified.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The particle effect is active when the item is held and its identity is known.
*   **`sprite_file`**: `data/particles/berserk_0$[1-4].xml` - Specifies the particle sprites to be used, with a range indicating multiple variations.
*   **`delay`**: `0` - No initial delay before emission starts.
*   **`lifetime`**: `1.5` - The duration of the particle effect in seconds.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1` - Initial color is white.
*   **`color_change.a`**: `-0.5` - The alpha (transparency) of the particles decreases over time.
*   **`gravity.y`**: `10` - Particles are affected by upward gravity.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `35` to `45` - Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: `1` - Emits one particle per emission cycle.
*   **`randomize_rotation.min`, `randomize_rotation.max`**: `-0.3415` to `0.3415` - Randomizes the initial rotation of particles.
*   **`randomize_position.min_x`, `randomize_position.max_x`**: `-5` to `5` - Randomizes the X-position of emitted particles.
*   **`randomize_position.min_y`, `randomize_position.max_y`**: `-10` to `0` - Randomizes the Y-position of emitted particles.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`**: `-10` to `10` - Randomizes the X-velocity of emitted particles.
*   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-20` to `5` - Randomizes the Y-velocity of emitted particles.