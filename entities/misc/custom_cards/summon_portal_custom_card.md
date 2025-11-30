---
title: Summon Portal Custom Card
category: entities/misc/custom_cards
---

# Summon Portal Custom Card

This document describes the `summon_portal.xml` entity, which defines a custom card in Noita that allows the player to summon a portal.

## Entity Definition

The core of this entity is a `Base` entity, inheriting properties from `data/entities/base_custom_card.xml`.

### Key Components

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/summon_portal.png` - This specifies the visual representation of the card in the game's UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates that this action is available when the player is in the game world.
    *   `action_id`: `SUMMON_PORTAL` - This is the unique identifier for the action performed by this card.