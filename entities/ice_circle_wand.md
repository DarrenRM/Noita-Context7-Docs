---
title: Ice Circle Wand
category: entities
---

# Ice Circle Wand

This entity defines a custom wand in Noita that casts an "Ice Circle" spell. It primarily uses a base custom card entity and adds visual effects and a light source.

## Base Entity Configuration

The wand is built upon a `base_custom_card.xml` entity, inheriting its core functionality.

### Sprite Component

Defines the visual representation of the wand in the UI.

*   **`image_file`**: `data/ui_gfx/gun_actions/icecircle.png` - Specifies the texture used for the wand's icon.

### Item Action Component

Determines the wand's behavior when used.

*   **`action_id`**: `ICECIRCLE` - A unique identifier for this wand's action.
*   **`_tags`**: `enabled_in_world` - Indicates the wand is active and usable in the game world.

## Transform Component

Controls the positioning of the wand when held.

### Inherit Transform Component

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - Ensures the transform is applied when the wand is in the world and held by the player.
*   **`Transform`**:
    *   **`position.x`**: `8` - Offsets the wand 8 units to the right.
    *   **`position.y`**: `0` - No vertical offset.

## Visual Effects

The wand emits particles and a light source when held and identified.

### Sprite Particle Emitter Component

Generates snowflake-like particles.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Activates when the wand is held and its properties are known.
*   **`sprite_file`**: `data/particles/snowflake_$[1-2].xml` - Uses snowflake particle definitions.
*   **`lifetime`**: `10` - Duration each particle exists.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1` - Initial white color.
*   **`color_change.a`**: `-0.5` - Fades out the alpha over time.
*   **`gravity.y`**: `10` - Particles are affected by gravity.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10`, `20` - Controls the rate of particle emission.
*   **`count_min`, `count_max`**: `1`, `1` - Emits one particle per emission cycle.
*   **`randomize_rotation`**: `-3.1415` to `3.1415` - Randomizes particle rotation.
*   **`randomize_angular_velocity`**: `-1` to `1` - Randomizes particle spinning.
*   **`randomize_position`**: Offsets particles within a small area.
*   **`randomize_velocity`**: Randomizes particle initial velocity.

### Particle Emitter Component

Emits cosmetic particles, likely for a magical effect.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Activates when the wand is held and identified.
*   **`emitted_material_name`**: `plasma_fading` - The material used for these particles.
*   **`count_min`, `count_max`**: `1`, `2` - Emits 1 or 2 particles per cycle.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Offsets particle emission position slightly.
*   **`x_vel_min/max`, `y_vel_min/max`**: Sets a range for particle velocity.
*   **`gravity.y`**: `0` - Particles are not affected by gravity.
*   **`lifetime_min`, `lifetime_max`**: `0.1`, `0.6` - Short lifespan for these particles.
*   **`create_real_particles`**: `0` - These are cosmetic, not physical.
*   **`emit_cosmetic_particles`**: `1` - Explicitly marks them as cosmetic.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10`, `20` - Controls emission rate.
*   **`is_emitting`**: `1` - The emitter is active.

### Light Component

Adds a light source around the wand.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Active when held and identified.
*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `10`, `30`, `60` - Sets the light color to a cool blueish hue.