---
title: Holy Lance Custom Card
category: entities
---

# Holy Lance Custom Card

This document describes the `lance_holy.xml` entity, which defines a custom spell card in Noita.

## Base Entity

The card inherits from `base_custom_card.xml`, providing fundamental properties for custom spells.

### Sprite Component

*   **image_file**: `data/ui_gfx/gun_actions/lance_holy.png` - Specifies the visual icon for the spell card in the UI.

### Item Action Component

*   **action\_id**: `LANCE_HOLY` - This unique identifier links the card to its specific spell behavior.
*   **\_tags**: `enabled_in_world` - Indicates the card can be found and used within the game world.

## Visual and Effect Components

These components define the visual flair and particle effects associated with the Holy Lance when held.

### Inherit Transform Component

*   **\_tags**: `enabled_in_world`, `enabled_in_hand` - The card is active both in the world and when held by the player.
*   **Transform**:
    *   **position.x**: `8`
    *   **position.y**: `0` - Defines the relative position of the card's visual elements when held.

### Particle Emitter Component

This component generates cosmetic particles to enhance the visual appearance of the card when identified.

*   **\_tags**: `enabled_in_hand`, `item_identified`
*   **emitted\_material\_name**: `gold` - The material used for the emitted particles.
*   **offset.x/y**: `0` - Center of emission.
*   **x\_pos\_offset\_min/max**: `-2` to `2`
*   **y\_pos\_offset\_min/max**: `2` to `-2` - Defines the area where particles are spawned.
*   **x\_vel\_min/max**: `-2` to `2`
*   **y\_vel\_min/max**: `-30` to `-10` - Controls the initial velocity of the particles.
*   **count\_min/max**: `1` to `2` - Number of particles emitted per burst.
*   **lifetime\_min/max**: `0.4` to `0.6` - Duration each particle exists.
*   **create\_real\_particles**: `0` - Only cosmetic particles are created.
*   **emit\_cosmetic\_particles**: `1` - Enables cosmetic particle emission.
*   **emission\_interval\_min/max\_frames**: `5` to `15` - Controls the timing between particle bursts.
*   **is\_emitting**: `1` - The particle emitter is active.

### Light Component

This component adds a light source to the card when held and identified.

*   **\_tags**: `enabled_in_hand`, `item_identified`
*   **\_enabled**: `1` - The light component is active.
*   **radius**: `30` - The range of the light.
*   **fade\_out\_time**: `1.5` - How long the light takes to fade.
*   **r, g, b**: `40, 140, 180` - Defines the color of the light (a bluish-white hue).