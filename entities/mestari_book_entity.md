---
title: Mestari Book Entity
category: entities
---

# Mestari Book Entity

This document describes the `book_mestari.xml` entity, representing the "Mestari" book in Noita. This book functions as a scroll, granting the player a specific ability when read.

## Key Components and Attributes

### Base Book Configuration

The entity inherits its core functionality from `data/entities/items/books/base_book.xml`.

### Book Component

*   `_enabled`: Controls the activation state of the book component.

### Particle Emitter Component

*   `_enabled`: Controls the activation state of particle effects associated with the book.

### Physics Image Shape Component

*   `image_file`: Specifies the visual representation of the book in the game world.
    *   `data/items_gfx/book_small.png`

### UI Info Component

*   `name`: Defines the in-game display name of the book.
    *   `$booktitle_mestari` (This is a localization key, the actual text will be fetched from language files.)

### Item Component

*   `ui_sprite`: The sprite used for the book in the inventory or when held.
    *   `data/items_gfx/book.png`
*   `item_name`: The internal name for the item, often used for referencing.
    *   `$booktitle_mestari`
*   `ui_description`: The text displayed when hovering over the item in the UI.
    *   `$bookdesc_mestari` (This is a localization key.)

### Sprite Component

*   `image_file`: The sprite used when the book is held in the player's hand.
    *   `data/items_gfx/in_hand/book_in_hand.png`

### Ability Component

*   `ui_name`: The name displayed in the UI related to the ability granted by this book.
    *   `$booktitle_mestari`

## Summary

The `book_mestari.xml` entity defines a scrollable item in Noita. It utilizes a base book configuration and specifies its visual assets, UI information, and the ability it grants through localization keys. The primary function is to act as a collectible that unlocks a specific spell or effect for the player.