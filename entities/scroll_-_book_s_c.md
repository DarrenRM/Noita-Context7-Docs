---
title: Scroll - Book S (C)
category: entities
---

# Scroll - Book S (C)

This entity defines a specific scroll item in Noita, referred to as "Book S (C)". It inherits its core functionality from `base_book.xml` and defines its visual appearance and UI information.

## Key Components

### Base Book Inheritance

The scroll utilizes `data/entities/items/books/base_book.xml` for its fundamental properties.

### Physics Image Shape Component

Defines the visual representation of the scroll when it's in the game world.

*   `image_file`: `data/items_gfx/book_s_small.png`

### UI Info Component

Provides information displayed in the user interface, such as the item's name.

*   `name`: `$item_book_s_a` (This is a localization key for the item's name)

### Item Component

Manages the item's properties as an inventory item.

*   `ui_sprite`: `data/items_gfx/book_s.png` (The sprite used in the inventory UI)
*   `item_name`: `$item_book_s_a` (Localization key for the item's name)
*   `ui_description`: `$itemdesc_book_s_c` (Localization key for the item's description)

### Sprite Component

Determines the sprite used when the item is held in the player's hand.

*   `image_file`: `data/items_gfx/in_hand/book_s_in_hand.png`

### Ability Component

Associates an ability with the scroll, likely related to what spell it grants.

*   `ui_name`: `$item_book_s_a` (Localization key for the ability's name, matching the item name)

## Disabled Components

The following components are present but disabled (`_enabled="0"`), meaning they do not actively contribute to the entity's behavior in this specific configuration:

*   `BookComponent`
*   `ParticleEmitterComponent`