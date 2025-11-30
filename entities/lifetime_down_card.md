---
title: Lifetime Down Card
category: entities
---

# Lifetime Down Card

This entity defines a custom card in Noita that, when used, reduces the lifetime of the player's current spell.

## Key Components

### Base Entity
The card inherits from `base_custom_card.xml`, providing its fundamental structure and behavior as a usable item.

### Sprite Component
*   `image_file`: `data/ui_gfx/gun_actions/lifetime_down.png` - Specifies the visual representation of the card in the game's UI.

### Item Action Component
*   `_tags`: `enabled_in_world` - Indicates that this action is available when the item is in the game world.
*   `action_id`: `LIFETIME_DOWN` - The unique identifier for this specific card's action.

### Inherit Transform Component
*   `_tags`: `enabled_in_world,enabled_in_hand` - The card is active when in the world and when held by the player.
*   `parent_hotspot_tag`: `shoot_pos` - Defines the point from which the card's effects originate when used.

### Particle Emitter Component
This component creates visual effects when the card is held and identified.
*   `_tags`: `enabled_in_hand,item_identified` - The emitter is active when the item is held and has been identified by the player.
*   `emitted_material_name`: `spark_green` - The type of particle to emit.
*   `offset.x`, `offset.y`: `0` - The particles are emitted from the item's origin.
*   `x_pos_offset_min`, `x_pos_offset_max`: `-3` to `3` - Controls the horizontal spread of emitted particles.
*   `y_pos_offset_min`, `y_pos_offset_max`: `1` to `-1` - Controls the vertical spread of emitted particles.
*   `x_vel_min`, `x_vel_max`: `-2` to `2` - Sets the horizontal velocity range for particles.
*   `y_vel_min`, `y_vel_max`: `-20` to `-10` - Sets the vertical velocity range for particles, giving them an upward trajectory.
*   `count_min`, `count_max`: `1` - The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: `0.2` to `0.3` - The duration each particle exists.
*   `create_real_particles`: `0` - Particles are cosmetic and do not interact physically.
*   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `30` to `45` - The delay between particle emission bursts.
*   `is_emitting`: `1` - The particle emitter is active by default.