---
title: Mana Card Entity
category: entities
---

# Mana Card Entity

This document describes the `mana.xml` entity, which represents a custom card in Noita that provides mana.

## Base Entity Configuration

The entity inherits from `base_custom_card.xml`, indicating it's a custom item.

### Sprite Component

*   **`image_file`**: `data/ui_gfx/gun_actions/mana.png` - Specifies the visual representation of the mana card in the UI.

### Item Action Component

*   **`action_id`**: `MANA` - This unique identifier links the card to its specific in-game function.
*   **`_tags`**: `enabled_in_world` - The action is active when the card is in the game world.

## Transform Component

This component defines the card's position relative to its parent when held.

### Inherit Transform Component

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The transform is applied when the card is in the world and specifically when held by the player.
*   **`Transform`**:
    *   `position.x`: `8`
    *   `position.y`: `0` - Offsets the card slightly when held.

## Particle Emitter Component

This component generates visual effects when the card is identified and held.

### Key Attributes

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Particles are emitted only when the item is held and has been identified by the player.
*   **`emitted_material_name`**: `spark_blue` - The type of particle to emit.
*   **`offset.x`, `offset.y`**: `0` - Particles originate from the center of the card.
*   **`x_pos_offset_min`/`max`**: `-3` to `3` - Horizontal spread of emitted particles.
*   **`y_pos_offset_min`/`max`**: `1` to `-1` - Vertical spread of emitted particles.
*   **`gravity.y`**: `0` - Particles are not affected by gravity.
*   **`x_vel_min`/`max`**: `-12` to `12` - Horizontal velocity range for particles.
*   **`y_vel_min`/`max`**: `-12` to `-12` - Vertical velocity range for particles (moving upwards).
*   **`count_min`/`max`**: `1` - Number of particles emitted per burst.
*   **`lifetime_min`/`max`**: `0.2` to `0.9` - Duration each particle exists.
*   **`create_real_particles`**: `0` - Indicates these are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles`**: `1` - Enables the emission of cosmetic particles.
*   **`emission_interval_min`/`max_frames`**: `5` to `15` - Controls the timing between particle bursts.
*   **`is_emitting`**: `1` - The particle emitter is active.

## Light Component

This component adds a light source when the card is identified and held.

### Key Attributes

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The light is active when the item is held and identified.
*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `40` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `20`, `80`, `180` - Defines the blueish color of the light.