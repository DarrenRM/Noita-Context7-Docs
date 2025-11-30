---
title: Burn Trail Custom Card
category: entities
---

# Burn Trail Custom Card

This document describes the `burn_trail.xml` entity, which defines a custom card in Noita that creates a trail of fire.

## Key Attributes

### Base Entity Configuration

*   **`base_custom_card.xml`**: Inherits core functionality for custom cards.
    *   **`SpriteComponent`**:
        *   `image_file`: `data/ui_gfx/gun_actions/burn_trail.png` - Specifies the visual icon for this card in the UI.
    *   **`ItemActionComponent`**:
        *   `_tags`: `enabled_in_world` - Indicates the action is available when the player is in the game world.
        *   `action_id`: `BURN_TRAIL` - A unique identifier for this specific card action.

### Explosive Properties

*   **`base_explosive.xml`**: Inherits properties related to explosive effects. This suggests the burn trail might have some explosive characteristics or be built upon an explosive foundation.

## Summary

The `burn_trail.xml` entity is a custom card that, when activated, likely creates a persistent trail of fire. It leverages the base custom card and explosive entity structures to define its behavior and visual representation. The primary customization is the UI sprite used to represent the card.