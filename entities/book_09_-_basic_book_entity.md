---
title: Book 09 - Basic Book Entity
category: entities
---

# Book 09 - Basic Book Entity

This document describes the `book_09.xml` entity, which represents a basic book item in Noita. It inherits its core functionality from `base_book.xml` and primarily defines its in-game name and description.

## Key Attributes

The `book_09.xml` entity is a simple item with the following key attributes:

*   **Tags**: `tablet`, `forgeable`, `normal_tablet` - These tags categorize the item, indicating it's a tablet, can be forged, and is a standard tablet.
*   **Base File**: `data/entities/items/books/base_book.xml` - This specifies that the book inherits its fundamental properties and behaviors from the base book entity.

### UI Information

The `UIInfoComponent` defines how the book appears in the user interface.

| Attribute | Value        | Description                                    |
| :-------- | :----------- | :--------------------------------------------- |
| `name`    | `$booktitle09` | The internal identifier for the book's title. |

### Item Component

The `ItemComponent` provides details relevant to the item's inventory and usage.

| Attribute      | Value        | Description                                       |
| :------------- | :----------- | :------------------------------------------------ |
| `item_name`    | `$booktitle09` | The in-game name displayed to the player.         |
| `ui_description` | `$bookdesc09`  | The in-game description displayed to the player. |

### Ability Component

The `AbilityComponent` is used to associate abilities with the item, though in this basic book, it primarily serves to link the UI name.

| Attribute | Value        | Description                                    |
| :-------- | :----------- | :--------------------------------------------- |
| `ui_name` | `$booktitle09` | The name displayed when the item's ability is shown. |