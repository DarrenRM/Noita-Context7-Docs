---
title: White Hole Big Custom Card
category: entities
---

# White Hole Big Custom Card

This document describes the `white_hole_big.xml` entity, which defines a custom spell card in Noita. This card, when held, visually represents a "White Hole" effect with particle emissions and a light source.

## Base Entity

The core of this entity is built upon `base_custom_card.xml`, providing fundamental properties for custom spell cards.

### Sprite Component

Defines the visual representation of the card when it's in the player's hand or inventory.

*   **`image_file`**: `data/ui_gfx/gun_actions/white_hole_big.png` - Specifies the texture used for the card's icon.

### Item Action Component

This component links the card to a specific in-game action.

*   **`action_id`**: `WHITE_HOLE_BIG` - The unique identifier for the action this card triggers.
*   **`_tags`**: `enabled_in_world` - Indicates that this action is available when the card is in the game world.

## Inherited Transform Component

This component handles the positioning and orientation of the card's visual elements when held.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - Ensures these transformations apply when the card is in the world and being held.
*   **`Transform`**:
    *   **`position.x`**: `8` - Offset on the X-axis.
    *   **`position.y`**: `0` - Offset on the Y-axis.

## Particle Emitter Component

Responsible for generating visual particle effects associated with the "White Hole" card.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The particles are emitted when the card is held and has been identified.
*   **`emitted_material_name`**: `spark_white` - The type of material used for the emitted particles.
*   **`offset.x`**, **`offset.y`**: `0` - The center point for particle emission.
*   **`x_pos_offset_min`** to **`y_pos_offset_max`**: Defines a small area around the offset from which particles can originate.
*   **`x_vel_min`** to **`y_vel_max`**: Sets the initial velocity range for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`count_min`** to **`count_max`**: Determines the number of particles emitted per burst.
*   **`lifetime_min`** to **`lifetime_max`**: Controls how long each particle exists.
*   **`create_real_particles`**: `0` - Indicates that these are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles`**: `1` - Confirms that cosmetic particles are being emitted.
*   **`emission_interval_min_frames`** to **`emission_interval_max_frames`**: Sets the delay between particle emission bursts.
*   **`is_emitting`**: `1` - The particle emitter is active.

## Light Component

Adds a dynamic light source to the card when it's held, enhancing its visual presence.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The light is active when the card is held and identified.
*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long it takes for the light to fade out.
*   **`r`**, **`g`**, **`b`**: `120`, `40`, `120` - Defines the color of the light (a purplish hue).