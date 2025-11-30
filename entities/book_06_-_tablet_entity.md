---
title: Book 06 - Tablet Entity
category: entities
---

# Book 06 - Tablet Entity

This document describes the Noita entity for a specific book, identified as `book_06.xml`. This entity represents a tablet that can be forged and is considered a normal tablet.

## Key Attributes

The `book_06.xml` entity primarily defines a tablet item with the following key attributes:

*   **`tags`**: `tablet`, `forgeable`, `normal_tablet` - These tags categorize the item, indicating its type, its ability to be forged, and its rarity/commonality.
*   **`Base file`**: `data/entities/items/books/base_book.xml` - This indicates that the entity inherits its fundamental properties from a base book entity.

### UI and Item Components

The entity utilizes components to define its in-game presentation and functionality:

*   **`UIInfoComponent`**:
    *   `name`: `$booktitle06` - This refers to a localization key for the book's title displayed in the user interface.
*   **`ItemComponent`**:
    *   `item_name`: `$booktitle06` - Similar to the UI name, this links to the localized title for the item.
    *   `ui_description`: `$bookdesc06` - This refers to a localization key for the book's descriptive text shown in the UI.
*   **`AbilityComponent`**:
    *   `ui_name`: `$booktitle06` - This also links to the localized title, likely for displaying the ability associated with the book.

## Summary

The `book_06.xml` entity is a straightforward definition of a tablet item. It leverages a base book entity and primarily customizes its UI display name and description through localization keys. The `forgeable` and `normal_tablet` tags suggest its role within the game's crafting and item systems.