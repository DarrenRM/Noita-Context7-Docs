---
title: Custom Card - Slow Bullet
category: entities
---

# Custom Card - Slow Bullet

This entity defines a custom spell card in Noita that, when cast, applies a "slow" effect to projectiles.

## Base Entity

The card inherits from `base_custom_card.xml`, providing core functionality for custom spell cards.

### Sprite Component

*   **`image_file`**: `data/ui_gfx/gun_actions/slow_bullet.png` - Specifies the visual representation of the card on the UI.

### Item Action Component

*   **`action_id`**: `SLOW_BULLET` - This unique identifier links the card to its specific in-game effect.
*   **`_tags`**: `enabled_in_world` - Indicates the card is active and usable within the game world.

## Inherit Transform Component

This component positions the card when held by the player.

*   **`_tags`**: `enabled_in_world,enabled_in_hand` - The card is active both in the world and when held.
*   **`Transform`**:
    *   **`position.x`**: `8` - Horizontal offset from the player's hand.
    *   **`position.y`**: `0` - Vertical offset from the player's hand.

## Particle Emitter Component

This component generates cosmetic particles when the card is identified and held.

*   **`_tags`**: `enabled_in_hand,item_identified` - Particles are emitted when the item is held and its effect is known.
*   **`emitted_material_name`**: `plasma_fading` - The type of particle material to emit.
*   **`offset.x` / `offset.y`**: `0` - Particles originate from the center of the card.
*   **`x_pos_offset_min` / `x_pos_offset_max`**: `-3` to `3` - Controls the horizontal spread of particles.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: `-3` to `3` - Controls the vertical spread of particles.
*   **`gravity.y`**: `50` - The gravitational pull on the emitted particles.
*   **`x_vel_min` / `x_vel_max`**: `-8` to `8` - The minimum and maximum horizontal velocity of particles.
*   **`y_vel_min` / `y_vel_max`**: `-8` to `8` - The minimum and maximum vertical velocity of particles.
*   **`count_min` / `count_max`**: `1` to `2` - The number of particles emitted per burst.
*   **`lifetime_min` / `lifetime_max`**: `0.2` to `0.5` - The duration each particle exists.
*   **`create_real_particles`**: `0` - Particles are cosmetic and do not interact physically.
*   **`emit_cosmetic_particles`**: `1` - Enables the emission of cosmetic particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `10` to `25` - The frame delay between particle emissions.
*   **`is_emitting`**: `1` - The particle emitter is active.

## Light Component

This component adds a light source when the card is identified and held.

*   **`_tags`**: `enabled_in_hand,item_identified` - The light is active when the item is held and identified.
*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `30` - The radius of the light effect.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.
*   **`r`**: `10` - Red component of the light color.
*   **`g`**: `50` - Green component of the light color.
*   **`b`**: `60` - Blue component of the light color.