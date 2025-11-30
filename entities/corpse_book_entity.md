---
title: Corpse Book Entity
category: entities
---

---

# Corpse Book Entity

This document describes the `book_corpse.xml` entity, which represents a book in Noita that grants the "Corpse" spell.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag with the following attributes:

*   **tags**: `tablet`, `normal_tablet` - These tags categorize the entity as a usable tablet and a standard one.

## Base Book Configuration

The entity inherits its fundamental properties from `data/entities/items/books/base_book.xml`. Key components are overridden or configured:

### UIInfoComponent

This component defines how the book appears in the game's user interface.

*   **name**: `$booktitle_corpse` - This is a localization key that resolves to the in-game name of the book (e.g., "Corpse").

### ItemComponent

This component defines the item's properties when it's picked up or interacted with.

*   **item_name**: `$booktitle_corpse` - Similar to the UI name, this is the internal and display name for the item.
*   **ui_description**: `$bookdesc_corpse` - This localization key provides the in-game description for the book.

### AbilityComponent

This component links the book to the spell it grants.

*   **ui_name**: `$booktitle_corpse` - This specifies the name of the spell associated with this book, which is also "Corpse".