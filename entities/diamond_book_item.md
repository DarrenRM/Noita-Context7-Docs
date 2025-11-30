---
title: Diamond Book Item
category: entities
---

# Diamond Book Item

This document describes the `book_diamond.xml` entity, representing a book item in Noita.

## Key Attributes

This book entity inherits from `base_book.xml` and defines specific properties for the "Diamond" book.

### Entity Tags

*   `scroll`: Indicates this entity is a scroll, likely usable for casting spells.

### Base Entity Inheritance

*   `data/entities/items/books/base_book.xml`: This book inherits its fundamental properties and behaviors from the base book entity.

### Physics Image Shape Component

*   `image_file="data/items_gfx/book_small.png"`: Specifies the visual asset used for the book's physical representation in the game world.

### UI Info Component

*   `name="$item_book_diamond"`: Defines the internal name identifier for this item, used for referencing in game data and potentially for localization.

### Item Component

*   `ui_sprite="data/items_gfx/book.png"`: The sprite displayed in the player's inventory and UI.
*   `item_name="$item_book_diamond"`: The localized name of the item displayed to the player.
*   `ui_description="$itemdesc_book_diamond"`: The localized description of the item, explaining its function or lore.

### Sprite Component

*   `image_file="data/items_gfx/in_hand/book_in_hand.png"`: The sprite displayed when the player is holding the book.

### Ability Component

*   `ui_name="$item_book_diamond"`: The name displayed in the UI for the ability associated with this book.

## Disabled Components

The following components are present but disabled (`_enabled="0"`), meaning their functionality is not active in this specific entity configuration.

*   `BookComponent`
*   `ParticleEmitterComponent`