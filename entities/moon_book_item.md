---
title: Moon Book Item
category: entities
---

# Moon Book Item

This document describes the `book_moon.xml` entity, representing a Moon Book item in Noita.

## Core Entity

The `Entity` tag defines the root of this item.

*   **Tags**: `scroll` - Indicates this item is a scroll.

## Base Book Integration

The item inherits properties from `data/entities/items/books/base_book.xml`.

### Book Component

*   `_enabled`: Set to `0`, suggesting this specific book component might be disabled by default or overridden by other configurations.

### Particle Emitter Component

*   `_enabled`: Set to `0`, indicating no particle effects are active for this book in its base state.

### Physics Image Shape Component

*   `image_file`: `data/items_gfx/book_small.png` - Specifies the visual asset used for the book's physics shape.

### UI Info Component

*   `name`: `$item_book_moon` - The internal identifier for the item's name, which will be localized.

### Item Component

*   `ui_sprite`: `data/items_gfx/book.png` - The sprite displayed in the inventory or when the item is held.
*   `item_name`: `$item_book_moon` - Links to the localized name of the item.
*   `ui_description`: `$itemdesc_book_moon` - Links to the localized description of the item.

### Sprite Component

*   `image_file`: `data/items_gfx/in_hand/book_in_hand.png` - The sprite displayed when the player is holding the book.

### Ability Component

*   `ui_name`: `$item_book_moon` - The name displayed in UI elements related to abilities, likely for when the book grants a spell.