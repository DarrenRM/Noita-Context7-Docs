---
title: Money Magic Custom Card
category: entities
---

# Money Magic Custom Card

This document describes the "Money Magic" custom card entity for Noita modding. It's designed to be a visually distinct item that likely has a unique gameplay effect related to gold.

## Core Components

### Base Entity

The card inherits from `base_custom_card.xml`, providing fundamental properties for custom items.

*   **`SpriteComponent`**: Defines the visual appearance of the card when held or in the inventory.
    *   `image_file`: `data/ui_gfx/gun_actions/golden_punch.png` - This indicates the card has a golden, punch-related visual.

### Item Action Component

This component assigns an `action_id` to the card, linking it to specific game mechanics.

*   **`ItemActionComponent`**:
    *   `action_id`: `MONEY_MAGIC` - This is the key identifier for the card's associated action or effect within the game's scripting.
    *   `_tags`: `enabled_in_world` - The card is active and usable when found in the game world.

### Transform Component

This component dictates how the card's visual elements are positioned relative to the player's hand.

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The card is active both in the world and when held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - The card's position will be anchored to the player's shooting position.

### Particle Emitter Component

This component adds visual flair by emitting particles when the card is held and identified.

*   **`ParticleEmitterComponent`**:
    *   `_tags`: `enabled_in_hand,item_identified` - Particles are emitted when the item is held and its identity has been revealed to the player.
    *   `emitted_material_name`: `gold` - The particles emitted are visually represented as gold.
    *   `offset.x`, `offset.y`: `0` - The emitter is centered on the card.
    *   `x_pos_offset_min`/`max`, `y_pos_offset_min`/`max`: Defines a small area around the card for particle emission.
    *   `x_vel_min`/`max`, `y_vel_min`/`max`: Controls the initial velocity and direction of the emitted particles, suggesting an upward and outward spread.
    *   `count_min`/`max`: `1` - A single particle is emitted per emission cycle.
    *   `lifetime_min`/`max`: `0.2` to `0.3` seconds - Particles have a short lifespan.
    *   `create_real_particles`: `0` - These are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Confirms cosmetic particle emission.
    *   `emission_interval_min_frames`/`max_frames`: `10` to `25` frames - Controls the rate at which particles are emitted.
    *   `is_emitting`: `1` - The particle emitter is active by default.

## Summary

The "Money Magic" card is a custom entity in Noita that visually resembles a golden punch. When held by the player, it emits cosmetic gold particles. Its `action_id` is `MONEY_MAGIC`, indicating it triggers a specific, yet undefined by this XML, gameplay effect related to gold or wealth. The visual design and particle effects suggest a theme of riches or a powerful, gold-themed ability.