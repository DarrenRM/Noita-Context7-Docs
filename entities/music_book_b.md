---
title: Music Book B
category: entities
---

# Music Book B

This document details the configuration for the "Music Book B" entity in Noita, intended for AI-assisted modding.

## Core Entity

The `Entity` tag defines the fundamental object.

*   **`tags`**: `scroll` - Indicates this item functions as a scroll or book within the game's mechanics.

## Base Configuration

The `Base` tag inherits properties from a common book template.

*   **`file`**: `data/entities/items/books/base_book.xml` - Specifies the parent XML file from which this entity derives its core attributes.

### Components

This section highlights key components and their significant attributes.

#### BookComponent

*   **`_enabled`**: `0` - This attribute is currently disabled, suggesting this specific book might not have unique active effects beyond its visual representation and item properties.

#### ParticleEmitterComponent

*   **`_enabled`**: `0` - Similar to `BookComponent`, this is disabled, meaning no special particle effects are associated with this book in its current state.

#### PhysicsImageShapeComponent

*   **`image_file`**: `data/items_gfx/book_small.png` - Defines the visual asset used for the book's physical representation in the game world.

#### UIInfoComponent

*   **`name`**: `$item_book_music_b` - This is a localization key that will be translated into the in-game name for the item.

#### ItemComponent

This component governs the item's properties as it appears in the player's inventory and UI.

*   **`ui_sprite`**: `data/items_gfx/book.png` - The sprite displayed for the item in the UI.
*   **`item_name`**: `$item_book_music_b` - The localization key for the item's name, matching the `UIInfoComponent`.
*   **`ui_description`**: `$itemdesc_book_music_b` - The localization key for the item's description, which will be displayed in the UI.

#### SpriteComponent

*   **`image_file`**: `data/items_gfx/in_hand/book_in_hand.png` - The sprite used when the player is holding the book.

#### AbilityComponent

*   **`ui_name`**: `$item_book_music_b` - The localization key for the name displayed in the abilities UI, likely when the book is "read" or equipped.