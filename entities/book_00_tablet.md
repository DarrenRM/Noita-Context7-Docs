---
title: Book 00 (Tablet)
category: entities
---

# Book 00 (Tablet)

This document describes the `book_00.xml` entity, representing a basic tablet item in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity tags="tablet,normal_tablet">
	<!-- ... -->
</Entity>
```

### Key Attributes:

*   **`tags`**: `tablet`, `normal_tablet` - These tags categorize the entity as a tablet and a standard, non-specialized tablet.

## Base Entity Inheritance

This book entity inherits its fundamental properties from `base_book.xml`.

```xml
<Base file="data/entities/items/books/base_book.xml">
	<!-- ... -->
</Base>
```

### Key Components:

*   **`UIInfoComponent`**:
    *   **`name`**: `$booktitle00` - This refers to a localization key for the book's title, indicating it's the first in a series or a default title.

*   **`ItemComponent`**:
    *   **`item_name`**: `$booktitle00` - Similar to `UIInfoComponent`, this links to the item's name.
    *   **`ui_description`**: `$bookdesc00` - This refers to a localization key for the item's description.

*   **`AbilityComponent`**:
    *   **`ui_name`**: `$booktitle00` - This also links to the localization key for the book's title, likely used for displaying its name in ability-related UI elements.