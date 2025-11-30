---
title: Small Book S (Scroll)
category: entities
---

# Small Book S (Scroll)

This entity defines a small book item in Noita, specifically a scroll. It inherits its base properties from `base_book.xml`.

## Key Attributes

*   **`tags`**: `scroll` - Identifies this entity as a scroll item.
*   **`Base file`**: `data/entities/items/books/base_book.xml` - Indicates that this book uses the common properties defined for books.

## Components

### `BookComponent`

*   `_enabled`: `0` - This component is disabled by default for this specific book.

### `ParticleEmitterComponent`

*   `_enabled`: `0` - Particle effects are disabled for this book.

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/items_gfx/book_s_small.png` - Specifies the graphical asset used for the book's physics shape.

### `UIInfoComponent`

*   **`name`**: `$item_book_s_a` - The internal identifier for the item's name, likely referencing a localization string.

### `ItemComponent`

*   **`ui_sprite`**: `data/items_gfx/book_s.png` - The sprite displayed in the UI inventory.
*   **`item_name`**: `$item_book_s_a` - The name displayed to the player, referencing a localization string.
*   **`ui_description`**: `$itemdesc_book_s_b` - The description displayed in the UI, referencing a localization string.

### `SpriteComponent`

*   **`image_file`**: `data/items_gfx/in_hand/book_s_in_hand.png` - The sprite used when the item is held in the player's hand.

### `AbilityComponent`

*   **`ui_name`**: `$item_book_s_a` - The name displayed in the UI for abilities associated with this item, referencing a localization string.