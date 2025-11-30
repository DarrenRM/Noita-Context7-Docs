---
title: Hint Book Entity
category: entities
---

# Hint Book Entity

This document describes the `book_hint.xml` entity, which represents a hint book in Noita. These books provide in-game descriptions and lore.

## Key Components and Attributes

The `book_hint.xml` entity is built upon a base book structure and includes several key components that define its behavior and appearance.

### Base Entity Structure

The entity is tagged as a `scroll`, indicating its general type.

```xml
<Entity tags="scroll">
```

### Base Book Component

This component inherits from `data/entities/items/books/base_book.xml`.

```xml
	<Base file="data/entities/items/books/base_book.xml">
		<BookComponent
			_enabled="0"
			>
		</BookComponent>
```

*   `_enabled`: This attribute is set to `0`, suggesting that the default `BookComponent` might be disabled or overridden by specific settings within this entity.

### Particle Emitter Component

This component is also disabled by default.

```xml
		<ParticleEmitterComponent
			_enabled="0"
			>
		</ParticleEmitterComponent>
```

*   `_enabled`: Set to `0`, indicating no particles are emitted by default for this book.

### Physics Image Shape Component

Defines the visual representation of the book in the game world.

```xml
		<PhysicsImageShapeComponent
			image_file="data/items_gfx/book_small.png"
		></PhysicsImageShapeComponent>
```

*   `image_file`: Specifies the sprite used for the book's physical form (`data/items_gfx/book_small.png`).

### UI Info Component

Provides information displayed in the user interface.

```xml
		<UIInfoComponent
			name="$item_book_hint"
			>
		</UIInfoComponent>
```

*   `name`: The internal name identifier for the item, linked to a localization string (`$item_book_hint`).

### Item Component

Defines the item's properties when it's in the player's inventory or being interacted with.

```xml
		<ItemComponent
			ui_sprite="data/items_gfx/book.png"
			item_name="$item_book_hint"
			ui_description="$itemdesc_book_hint"
			>
		</ItemComponent>
```

*   `ui_sprite`: The sprite displayed for the item in the UI (`data/items_gfx/book.png`).
*   `item_name`: The display name of the item in the UI, linked to a localization string (`$item_book_hint`).
*   `ui_description`: The description text displayed for the item, linked to a localization string (`$itemdesc_book_hint`).

### Sprite Component

Defines the sprite used when the item is held in the player's hand.

```xml
		<SpriteComponent
			image_file="data/items_gfx/in_hand/book_in_hand.png"
		></SpriteComponent>
```

*   `image_file`: Specifies the sprite for the book when held (`data/items_gfx/in_hand/book_in_hand.png`).

### Ability Component

This component is often used to grant abilities or define item interactions.

```xml
		<AbilityComponent
			ui_name="$item_book_hint"
			>
		</AbilityComponent>
```

*   `ui_name`: The name displayed in the UI for any associated ability, linked to a localization string (`$item_book_hint`).