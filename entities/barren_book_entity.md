---
title: Barren Book Entity
category: entities
---

# Barren Book Entity

This document describes the `book_barren.xml` entity, representing a "Barren" book in Noita. This book, when picked up, grants no specific spells or abilities.

## Key Attributes

The `book_barren.xml` entity inherits from `base_book.xml` and primarily defines its visual representation and UI information.

### Entity Tags

*   `scroll`: Indicates this entity is a type of scroll or book.

### Base Entity Inheritance

*   `data/entities/items/books/base_book.xml`: This entity inherits core functionality from the base book definition.

### Components

*   **`BookComponent`**:
    *   `_enabled="0"`: This component is disabled, meaning the book does not inherently grant any spells or effects when read.

*   **`ParticleEmitterComponent`**:
    *   `_enabled="0"`: This component is disabled, so no particles are emitted by the book itself.

*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/items_gfx/book_small.png"`: Defines the visual sprite for the book when it exists in the game world.

*   **`UIInfoComponent`**:
    *   `name="$booktitle_barren"`: Sets the display name of the book in the UI, localized by the `$booktitle_barren` string.

*   **`ItemComponent`**:
    *   `ui_sprite="data/items_gfx/book.png"`: Specifies the sprite used for the book in the player's inventory or when displayed in UI elements.
    *   `item_name="$booktitle_barren"`: The internal name for the item, also localized.
    *   `ui_description="$bookdesc_barren"`: The descriptive text shown for the book in the UI, localized by the `$bookdesc_barren` string.

*   **`SpriteComponent`**:
    *   `image_file="data/items_gfx/in_hand/book_in_hand.png"`: Defines the sprite used when the player is holding the book.

*   **`AbilityComponent`**:
    *   `ui_name="$booktitle_barren"`: Sets the name displayed in the ability selection UI, if applicable (though this book grants no abilities).

## Summary

The `book_barren.xml` entity is a placeholder book that visually appears as a book but provides no functional benefit or spell acquisition. Its primary purpose is likely for visual variety or as a base for other book types.