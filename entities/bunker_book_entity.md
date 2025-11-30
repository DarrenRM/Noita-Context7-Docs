---
title: Bunker Book Entity
category: entities
---

# Bunker Book Entity

This document describes the `book_bunker.xml` entity, representing a book found in Noita.

## Key Attributes

This entity inherits from `base_book.xml` and customizes several components.

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/items_gfx/book_small.png`
    *   Specifies the visual representation of the book when it's in the game world.

### `UIInfoComponent`

*   **`name`**: `$booktitle_fisher`
    *   Defines the in-game name displayed for this book. The `$booktitle_fisher` likely refers to a localized string for "Fisher Book".

### `ItemComponent`

*   **`ui_sprite`**: `data/items_gfx/book.png`
    *   The sprite used for the book when it appears in the UI (inventory, hotbar).
*   **`item_name`**: `$booktitle_fisher`
    *   The internal name for the item, also likely referencing the localized "Fisher Book" title.
*   **`ui_description`**: `$bookdesc_fisher`
    *   The localized description text for the book.

### `SpriteComponent`

*   **`image_file`**: `data/items_gfx/in_hand/book_in_hand.png`
    *   The sprite used when the player is holding the book.

### `AbilityComponent`

*   **`ui_name`**: `$booktitle_fisher`
    *   The name displayed in the UI for the ability granted by this book.

### `BookComponent`

*   **`_enabled`**: `0`
    *   This component is currently disabled.

### `ParticleEmitterComponent`

*   **`_enabled`**: `0`
    *   This component is currently disabled.

## Inheritance

This entity inherits from `data/entities/items/books/base_book.xml`, meaning it shares common properties and behaviors with other book entities.

## Notes for Modding

*   The book's functionality is primarily determined by the `AbilityComponent` and the spells it grants. The current configuration suggests it's a "Fisher Book" based on the localized strings.
*   To change the book's appearance, modify the `image_file` attributes in `PhysicsImageShapeComponent`, `ItemComponent` (`ui_sprite`), and `SpriteComponent`.
*   To change the book's name or description, update the corresponding `$booktitle_...` and `$bookdesc_...` entries in the game's localization files.
*   The disabled `BookComponent` and `ParticleEmitterComponent` suggest that any specific book-related logic or visual effects are either handled by inherited components or are not yet implemented/intended for this specific book.