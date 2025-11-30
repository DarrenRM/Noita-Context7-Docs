---
title: Flamethrower Custom Card
category: entities
---

---

# Flamethrower Custom Card

This document describes the configuration for the Flamethrower custom card entity in Noita, intended for AI-assisted modding.

## Entity Structure

The Flamethrower custom card is built upon two base entity files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental properties of a custom card, including its visual representation and interaction components.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Inherits properties related to explosive effects, suggesting the flamethrower might have some explosive characteristics or be part of a broader explosive-themed set.

## Key Components and Attributes

### Base: `data/entities/base_custom_card.xml`

This base file defines the core attributes of the custom card.

#### SpriteComponent

*   `image_file`: Specifies the UI image used to represent the flamethrower card.
    *   Value: `data/ui_gfx/gun_actions/flamethrower.png`

#### ItemActionComponent

*   `_tags`: Defines the contexts in which this item action is available.
    *   Value: `enabled_in_world` (meaning it can be used in the game world).
*   `action_id`: A unique identifier for this action.
    *   Value: `FLAMETHROWER`

### Base: `data/entities/misc/custom_cards/base_explosive.xml`

This base file likely contributes to the flamethrower's behavior by inheriting properties from a general explosive entity. Specific attributes from this base are not detailed in the provided XML snippet but would typically influence damage, area of effect, or particle effects.

## Summary

The Flamethrower custom card is a UI element that, when activated, performs an action identified as `FLAMETHROWER`. Its visual representation is defined by `flamethrower.png`. It inherits functionality from both a generic custom card and an explosive base, suggesting it will likely produce a damaging, area-of-effect attack.