---
title: Robot Book Item
category: entities
---

# Robot Book Item

This document describes the `book_robot.xml` entity, which represents a book item in Noita. This book, when read, grants the player the "Robot" ability.

## Key Components and Attributes

### Base Book Structure

The entity inherits from `data/entities/items/books/base_book.xml`, providing a foundational structure for all book items.

### `BookComponent`

*   **`_enabled`**: Set to `0`, indicating this specific component might be disabled or overridden by other configurations. In the context of a book, this would typically control its functional aspects when read.

### `ParticleEmitterComponent`

*   **`_enabled`**: Set to `0`. This suggests that the default particle effects associated with books are disabled for this specific item.

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/items_gfx/book_small.png`
    *   This defines the visual representation of the book when it's in the game world, likely a smaller sprite for dropped items.

### `UIInfoComponent`

*   **`name`**: `$item_book_robot`
    *   This is a localization key that will be translated into the in-game name of the item (e.g., "Robot Book").

### `ItemComponent`

*   **`ui_sprite`**: `data/items_gfx/book.png`
    *   The primary sprite used for the item in the UI (inventory, hotbar).
*   **`item_name`**: `$item_book_robot`
    *   Links to the localization key for the item's name.
*   **`ui_description`**: `$itemdesc_book_robot`
    *   A localization key for the item's description, which will explain its effect when read.

### `SpriteComponent`

*   **`image_file`**: `data/items_gfx/in_hand/book_in_hand.png`
    *   The sprite used to display the book when the player is holding it.

### `AbilityComponent`

*   **`ui_name`**: `$item_book_robot`
    *   This likely links the book to the "Robot" ability, using the same localization key as the item name. When the book is read, this component would trigger the granting of the associated ability.