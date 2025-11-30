---
title: Summon Portal (Broken) Card Entity
category: entities
---

# Summon Portal (Broken) Card Entity

This document describes the `summon_portal_broken.xml` entity, which represents a "broken" summon portal card in Noita. This entity is designed to be a custom card that can be forged.

## Key Attributes

### Entity Tags
*   `forgeable`: Indicates that this entity can be crafted or forged within the game.
*   `card_summon_portal_broken`: A specific tag identifying this as the broken summon portal card.

### Base Entity
*   `Base file="data/entities/base_custom_card.xml"`: This entity inherits its core functionality and properties from the `base_custom_card.xml` file, suggesting it's a template for custom cards.

### Sprite Component
*   `image_file="data/ui_gfx/gun_actions/broken_spell.png"`: Defines the visual representation of the card in the game's UI, specifically using an image associated with a "broken spell."

### Item Action Component
*   `action_id="SUMMON_PORTAL_BROKEN"`: This is the crucial identifier for the action this card performs when used. It triggers the "SUMMON_PORTAL_BROKEN" game action.
*   `_tags="enabled_in_world"`: This tag ensures that the action associated with this card is available and can be activated when the player is in the game world.