---
title: Poison Blast Custom Card
category: entities
---

# Poison Blast Custom Card

This document details the `poison_blast.xml` entity, representing a custom spell card in Noita that casts a poison blast.

## Base Entity

The core of this custom card is built upon `base_custom_card.xml`.

### Sprite Component

Defines the visual representation of the card in the UI.

*   **image\_file**: `data/ui_gfx/gun_actions/poison_blast.png` - Specifies the texture used for the card's icon.

### Item Action Component

Links the card to a specific in-game action.

*   **action\_id**: `POISON_BLAST` - Identifies the action triggered when this card is used.
*   **\_tags**: `enabled_in_world` - Indicates the card is active and usable within the game world.

## Inheritance and Transform

This section defines how the card's visual and functional elements are positioned relative to the player's hand.

### Inherit Transform Component

Applies transformations to the card's visual elements when held.

*   **\_tags**: `enabled_in_world`, `enabled_in_hand` - Ensures these transformations are active when the card is in the world and being held.
*   **Transform**:
    *   **position.x**: `4` - Offsets the card 4 units to the right.
    *   **position.y**: `0` - No vertical offset.

## Particle Emitter Component

This component governs the visual effects produced when the "Poison Blast" action is activated.

*   **\_tags**: `enabled_in_hand`, `item_identified` - The particle effect is active when the item is held and identified.
*   **emitted\_material\_name**: `poison_gas` - The type of material that forms the particles.
*   **offset.x / offset.y**: `0` - The emitter is centered on the card's origin.
*   **x\_pos\_offset\_min / x\_pos\_offset\_max**: `-5` to `5` - Particles are spread horizontally around the emitter.
*   **y\_pos\_offset\_min / y\_pos\_offset\_max**: `2` to `-2` - Particles are spread vertically around the emitter.
*   **x\_vel\_min / x\_vel\_max**: `-2` to `2` - Initial horizontal velocity of particles.
*   **y\_vel\_min / y\_vel\_max**: `-20` to `-10` - Initial upward velocity of particles, creating an arc.
*   **count\_min / count\_max**: `1` - A single particle is emitted per emission cycle.
*   **lifetime\_min / lifetime\_max**: `0.2` to `0.3` - Duration each particle exists.
*   **create\_real\_particles**: `1` - Indicates that these particles have physical properties.
*   **emit\_cosmetic\_particles**: `1` - Also emits visual-only particles for added effect.
*   **emission\_interval\_min\_frames / emission\_interval\_max\_frames**: `10` to `25` - The delay between particle emissions.
*   **is\_emitting**: `1` - The particle emitter is active.