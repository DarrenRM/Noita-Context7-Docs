---
title: Glitter Bomb Custom Card
category: entities
---

# Glitter Bomb Custom Card

This document describes the configuration for the "Glitter Bomb" custom card entity in Noita, intended for AI-assisted modding.

## Base Configuration

The Glitter Bomb card inherits its base functionality from `base_custom_card.xml`.

### Key Components:

*   **ItemComponent**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` (indicates it can be found and equipped).
    *   `is_equipable_forced`: `1` (ensures it's always equipable).

*   **SpriteComponent (Base)**:
    *   `image_file`: `data/ui_gfx/gun_actions/glitter_bomb.png` (UI icon for the action).

*   **ItemActionComponent**:
    *   `_tags`: `enabled_in_world`.
    *   `action_id`: `DYNAMITE` (links this card to a specific action type).

## In-Hand Visuals

This section defines how the Glitter Bomb appears when held by the player.

### SpriteComponent (In-Hand):

*   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` (only visible when held, not when in a wand).
*   `_enabled`: `0` (initially disabled, likely controlled by other components).
*   `offset_x`: `2.5`
*   `offset_y`: `4.5`
*   `image_file`: `data/items_gfx/in_hand/glitter_bomb_in_hand.png` (the actual sprite for the item in hand).

## Ability and Projectile

This component defines the card's primary function: throwing the Glitter Bomb.

### AbilityComponent:

*   `_tags`: `enabled_in_hand` (active when the item is held).
*   `ui_name`: `$action_glitter_bomb` (references a localization string for the name).
*   `entity_file`: `data/entities/projectiles/glitter_bomb.xml` (specifies the projectile entity to be spawned).
*   `rotate_hand_amount`: `0.05` (slight rotation when aiming).
*   `throw_as_item`: `1` (indicates it's thrown like an item).
*   `simulate_throw_as_item`: `1` (enables simulation for throwing behavior).
*   `use_entity_file_as_projectile_info_proxy`: `1` (uses the projectile entity's properties for information).

#### gun_config:

*   `deck_capacity`: `0` (this card does not contribute to wand deck capacity).