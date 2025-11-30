---
title: Custom Card - Grenade Tier 3
category: entities
---

# Custom Card - Grenade Tier 3

This entity defines a custom card in Noita, specifically the "Grenade Tier 3". It's designed to be a usable item within the game, likely a projectile weapon.

## Key Components

### Base Entity (`base_custom_card.xml`)

This card inherits its fundamental properties from a base custom card entity.

*   **SpriteComponent**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/grenade_tier_3.png` - Specifies the texture used for the card's icon.
*   **ItemActionComponent**: Links the card to a specific game action.
    *   `action_id`: `GRENADE_TIER_3` - Identifies the action this card triggers when used.
    *   `_tags`: `enabled_in_world` - Indicates the card is active and usable in the game world.

### Transform Component (`InheritTransformComponent`)

This component manages the positioning and orientation of the card when held by the player.

*   `parent_hotspot_tag`: `shoot_pos` - The card will align its transform relative to the "shoot\_pos" hotspot of the player's hand.
*   `_tags`: `enabled_in_world,enabled_in_hand` - Ensures this component is active when the card is in the world and being held.

### Particle Emitter Component (`ParticleEmitterComponent`)

This component adds visual effects, specifically cosmetic particles, when the card is held and identified.

*   `emitted_material_name`: `spark_purple_bright` - The type of particle to emit.
*   `offset.x`, `offset.y`: `0` - The particles originate from the center of the entity.
*   `x_pos_offset_min`, `x_pos_offset_max`: `-2` to `2` - Controls the horizontal spread of particle emission.
*   `y_pos_offset_min`, `y_pos_offset_max`: `2` to `-2` - Controls the vertical spread of particle emission.
*   `x_vel_min`, `x_vel_max`: `-2` to `2` - Sets the horizontal velocity range for emitted particles.
*   `y_vel_min`, `y_vel_max`: `-20` to `-10` - Sets the vertical velocity range for emitted particles (upwards).
*   `count_min`, `count_max`: `1` to `2` - The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: `0.2` to `0.3` - The duration each particle exists.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `8` to `15` - The delay between particle emission bursts.
*   `create_real_particles`: `0` - Particles are cosmetic and do not interact physically.
*   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
*   `is_emitting`: `1` - The particle emitter is active.
*   `_tags`: `enabled_in_hand,item_identified` - The emitter is active when the item is held and identified.

### Light Component (`LightComponent`)

This component adds a light source to the card when it's held and identified.

*   `radius`: `30` - The range of the light.
*   `fade_out_time`: `1.5` - How long the light takes to fade out.
*   `r`, `g`, `b`: `70`, `5`, `120` - Defines the color of the light (a purplish hue).
*   `_tags`: `enabled_in_hand,item_identified` - The light is active when the item is held and identified.