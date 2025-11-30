---
title: Book S (Scroll)
category: entities
---

# Book S (Scroll)

This document details the configuration for a scroll item in Noita, specifically the "Book S" variant.

## Entity Definition

The core entity is defined as a scroll.

```xml
<Entity tags="scroll">
	<Base file="data/entities/items/books/base_book.xml">
		<!-- ... other components ... -->
	</Base>
</Entity>
```

## Key Components

### Base Book Configuration

This entity inherits its fundamental properties from `data/entities/items/books/base_book.xml`.

### Book Component

This component, though present, is disabled (`_enabled="0"`) in this specific configuration. It typically handles book-specific logic.

```xml
<BookComponent
	_enabled="0"
	>
</BookComponent>
```

### Particle Emitter Component

This component is also disabled (`_enabled="0"`), meaning no special particle effects are emitted by this scroll in its default state.

```xml
<ParticleEmitterComponent 
	_enabled="0"
	>
</ParticleEmitterComponent>
```

### Physics Image Shape Component

Defines the visual representation of the scroll when it's in the game world.

```xml
<PhysicsImageShapeComponent 
	image_file="data/items_gfx/book_s_small.png"
></PhysicsImageShapeComponent>
```

*   `image_file`: Specifies the texture used for the scroll's sprite.

### UI Info Component

Provides information displayed in the user interface, such as the item's name.

```xml
<UIInfoComponent
	name="$item_book_s_a"
	>
</UIInfoComponent>
```

*   `name`: A localization key for the item's display name.

### Item Component

Manages the item's properties relevant to inventory and player interaction.

```xml
<ItemComponent
	ui_sprite="data/items_gfx/book_s.png"
	item_name="$item_book_s_a"
	ui_description="$itemdesc_book_s_e"
	>
</ItemComponent>
```

*   `ui_sprite`: The texture used for the item's icon in the UI.
*   `item_name`: Localization key for the item's name (can be the same as `UIInfoComponent`).
*   `ui_description`: Localization key for the item's descriptive text.

### Sprite Component

Defines the visual appearance of the item when held by the player.

```xml
<SpriteComponent
	image_file="data/items_gfx/in_hand/book_s_in_hand.png"
></SpriteComponent>
```

*   `image_file`: The texture for the sprite when the item is in the player's hand.

### Ability Component

This component is associated with the item's name in the UI, suggesting it might be linked to an ability or spell granted by the scroll.

```xml
<AbilityComponent
	ui_name="$item_book_s_a"
	>
</AbilityComponent>
```

*   `ui_name`: Localization key for the name displayed when associated with an ability.