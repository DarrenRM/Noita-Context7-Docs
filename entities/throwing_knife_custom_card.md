---
title: Throwing Knife Custom Card
category: entities
---

# Throwing Knife Custom Card

This document details the configuration for a custom card entity in Noita, specifically a "Throwing Knife". This entity is designed to be a usable item within the game, capable of being thrown.

## Base Entity Configuration

The core of this custom card is built upon a base entity designed for custom cards.

### Base File
*   `data/entities/base_custom_card.xml`: This specifies the foundational properties and behaviors inherited by this custom card.

### Item Component
*   `_tags`: `enabled_in_world`, `enabled_in_hand`, `enabled_in_world`. These tags ensure the item is active and usable in various game states.
*   `is_equipable_forced="1"`: This attribute forces the item to be equipable, meaning the player can hold and use it.

### Sprite Component (World/UI)
*   `image_file="data/ui_gfx/gun_actions/knife.png"`: This defines the visual representation of the knife when it appears as a gun action or in UI elements.

### Item Action Component
*   `_tags`: `enabled_in_world`.
*   `action_id="KNIFE"`: This assigns a unique identifier to the action performed by this item, likely used by game systems to trigger its behavior.

## In-Hand Visuals

This section defines how the knife appears when held by the player.

### Sprite Component (In Hand)
*   `_tags`: `enabled_in_hand`, `not_enabled_in_wand`. Ensures it's visible when held but not when part of a wand.
*   `_enabled="0"`: This sprite is initially disabled, likely controlled by the `AbilityComponent`.
*   `offset_x="1.5"`, `offset_y="8"`: Adjusts the position of the knife sprite relative to the player's hand.
*   `image_file="data/items_gfx/in_hand/knife_in_hand.png"`: The specific image file for the knife when held.

## Ability Component

This component defines the functional behavior of the throwing knife.

### Ability Component
*   `_tags`: `enabled_in_hand`.
*   `ui_name="Throwing Knife"`: The name displayed to the player in the user interface.
*   `entity_file="data/entities/items/pickup/knife.xml"`: Specifies the entity file that represents the projectile when the knife is thrown. This allows the thrown knife to have its own properties and behaviors.
*   `rotate_hand_amount="0.05"`: Controls the slight rotation of the player's hand when holding this item.
*   `throw_as_item="1"`: Indicates that the item should be thrown as a distinct entity.
*   `simulate_throw_as_item="1"`: Enables simulation of throwing as an item, likely for physics and trajectory.
*   `use_entity_file_as_projectile_info_proxy="1"`: Uses the `entity_file` to proxy information about the projectile.

#### Gun Config
*   `deck_capacity="0"`: This implies the throwing knife does not have a deck capacity, meaning it's a single-use or non-stacking item in terms of wand mechanics.