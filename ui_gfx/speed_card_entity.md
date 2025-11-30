---
title: Speed Card Entity
category: data/entities
---

# Speed Card Entity

This document describes the `speed.xml` entity, which represents a custom card in Noita that grants a speed boost.

## Base Entity

The entity inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

### Sprite Component

*   **image_file**: `data/ui_gfx/gun_actions/speed.png` - Specifies the visual representation of the card in the UI.

### Item Action Component

*   **action\_id**: `SPEED` - Identifies the specific action this card performs.
*   **\_tags**: `enabled_in_world` - Indicates the card is active when in the game world.

## Transform Component

### Inherit Transform Component

*   **\_tags**: `enabled_in_world`, `enabled_in_hand` - The card is active both in the world and when held by the player.
*   **parent\_hotspot\_tag**: `shoot_pos` - Defines the point from which the card's effects originate when held.

## Particle Emitter Component

This component generates cosmetic particles when the card is held and identified.

*   **\_tags**: `enabled_in_hand`, `item_identified` - Particles are emitted when the item is held and its identity is known.
*   **emitted\_material\_name**: `spark_green` - The type of material used for the emitted particles.
*   **offset.x**, **offset.y**: `0` - The particles are emitted from the exact center of the parent hotspot.
*   **x\_pos\_offset\_min/max**: `-4` to `4` - Horizontal spread of particle emission.
*   **y\_pos\_offset\_min/max**: `0` to `0` - No vertical spread of particle emission.
*   **x\_vel\_min/max**: `-10` to `10` - Horizontal velocity range for particles.
*   **gravity.y**: `0.0` - Particles are not affected by gravity.
*   **y\_vel\_min/max**: `-30` to `30` - Vertical velocity range for particles.
*   **count\_min/max**: `1` to `2` - Number of particles emitted per burst.
*   **lifetime\_min/max**: `0.05` to `0.4` - Duration particles exist.
*   **create\_real\_particles**: `0` - Only cosmetic particles are created.
*   **emit\_cosmetic\_particles**: `1` - Cosmetic particles are enabled.
*   **emission\_interval\_min/max\_frames**: `10` to `20` - The delay between particle emission bursts.
*   **is\_emitting**: `1` - The particle emitter is active.