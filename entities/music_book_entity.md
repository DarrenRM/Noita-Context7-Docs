---
title: Music Book Entity
category: entities
---

---

# Music Book Entity

This document describes the `book_music_a.xml` entity, representing a music book in Noita.

## Key Components and Attributes

This entity utilizes several components to define its behavior and appearance. The most important ones are:

### Base Book Component

This component inherits from `base_book.xml`, providing fundamental book properties.

*   **`_enabled`**: Controls whether the book component is active. (Set to `0` in this specific instance, suggesting it might be a template or disabled by default).

### Physics Image Shape Component

Defines the physical shape and visual representation of the book when it's in the game world.

*   **`image_file`**: Specifies the texture used for the book's sprite.
    *   `data/items_gfx/book_small.png`

### UI Info Component

Provides information displayed in the user interface, such as the item's name.

*   **`name`**: The internal identifier for the item's name, which is then localized.
    *   `$item_book_music`

### Item Component

Defines the item's properties relevant to inventory and player interaction.

*   **`ui_sprite`**: The sprite displayed for the item in the inventory.
    *   `data/items_gfx/book.png`
*   **`item_name`**: The localized name of the item.
    *   `$item_book_music`
*   **`ui_description`**: The localized description of the item.
    *   `$itemdesc_book_music`

### Sprite Component

Determines the visual appearance of the item when held by the player.

*   **`image_file`**: The texture for the item when it's in the player's hand.
    *   `data/items_gfx/in_hand/book_in_hand.png`

### Ability Component

This component is often used to grant abilities or spells when an item is used.

*   **`ui_name`**: The name displayed for the ability associated with this book.
    *   `$item_book_music`

## Summary

The `book_music_a.xml` entity defines a book that, when used, likely grants a music-related ability. It leverages a base book structure and specifies its visual assets for both world interaction and inventory display. The `_enabled="0"` on the `BookComponent` and `ParticleEmitterComponent` suggests this might be a base definition or a disabled variant, requiring further configuration or activation through other means to be fully functional.