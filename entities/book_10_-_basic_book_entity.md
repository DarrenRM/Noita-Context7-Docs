---
title: Book 10 - Basic Book Entity
category: entities
---

# Book 10 - Basic Book Entity

This document describes the `book_10.xml` entity, which represents a basic book item in Noita. It inherits its core functionality from `base_book.xml`.

## Key Attributes

This entity primarily defines a book with a specific in-game title and description.

### `Entity`

*   **tags**: `tablet`, `forgeable`, `normal_tablet` - These tags categorize the item, indicating it's a tablet, can be forged, and is a standard tablet.

### `Base`

*   **file**: `data/entities/items/books/base_book.xml` - Specifies that this book inherits its fundamental properties from the base book entity.

### `UIInfoComponent`

*   **name**: `$booktitle10` - This is a localization key that will be replaced with the actual in-game title for the book.

### `ItemComponent`

*   **item_name**: `$booktitle10` - Similar to the `UIInfoComponent`, this links to the localization key for the item's name.
*   **ui_description**: `$bookdesc10` - This is a localization key for the in-game description of the book.

### `AbilityComponent`

*   **ui_name**: `$booktitle10` - This also references the localization key for the book's title, likely used in contexts where abilities are displayed.