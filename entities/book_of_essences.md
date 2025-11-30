---
title: Book of Essences
category: entities
---

# Book of Essences

This document details the `book_essences.xml` entity, representing a book item in Noita.

## Core Entity

The `Entity` tag defines the fundamental object.

*   **Tags**: `scroll` - Indicates this entity is a scroll or book type item.

## Base Book Configuration

The `Base` tag inherits properties from `data/entities/items/books/base_book.xml`.

### Book Component

*   `_enabled`: Controls the activation state of the book component.

### Particle Emitter Component

*   `_enabled`: Controls the activation state of particle effects.

### Physics Image Shape Component

*   `image_file`: Specifies the sprite used for the book's physical representation in the game world.
    *   Value: `data/items_gfx/book_small.png`

### UI Info Component

*   `name`: The internal identifier for the item's name, often linked to localization strings.
    *   Value: `$item_book_essences`

### Item Component

This component defines the item's properties for inventory and UI.

*   `ui_sprite`: The sprite displayed for the item in the UI.
    *   Value: `data/items_gfx/book.png`
*   `item_name`: The localized name of the item.
    *   Value: `$item_book_essences`
*   `ui_description`: The localized description of the item.
    *   Value: `$itemdesc_book_essences`

### Sprite Component

This component defines the sprite used when the item is held by the player.

*   `image_file`: The sprite for the book when in the player's hand.
    *   Value: `data/items_gfx/in_hand/book_in_hand.png`

### Ability Component

This component links the item to an in-game ability or function.

*   `ui_name`: The name displayed for the ability associated with this book.
    *   Value: `$item_book_essences`