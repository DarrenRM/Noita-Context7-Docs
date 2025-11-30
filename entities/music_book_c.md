---
title: Music Book C
category: entities
---

# Music Book C

This document details the configuration for the "Music Book C" entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity is defined as a scroll item.

```xml
<Entity tags="scroll">
	<Base file="data/entities/items/books/base_book.xml">
		<!-- ... other components ... -->
	</Base>
</Entity>
```

## Key Components

### Base Book Configuration

This entity inherits its base properties from `data/entities/items/books/base_book.xml`.

### Book Component

This component is currently disabled (`_enabled="0"`), suggesting it might be a placeholder or intended for future functionality.

```xml
<BookComponent
	_enabled="0"
	>
</BookComponent>
```

### Particle Emitter Component

This component is also disabled (`_enabled="0"`).

```xml
<ParticleEmitterComponent 
	_enabled="0"
	>
</ParticleEmitterComponent>
```

### Physics Image Shape Component

Defines the visual representation of the book in the game world.

```xml
<PhysicsImageShapeComponent 
	image_file="data/items_gfx/book_small.png"
></PhysicsImageShapeComponent>
```

### UI Info Component

Provides information for the user interface, specifically the item's name.

```xml
<UIInfoComponent
	name="$item_book_music_c"
	>
</UIInfoComponent>
```

### Item Component

Configures the item's properties for inventory and UI display.

```xml
<ItemComponent
	ui_sprite="data/items_gfx/book.png"
	item_name="$item_book_music_c"
	ui_description="$itemdesc_book_music_c"
	>
</ItemComponent>
```

### Sprite Component

Defines the sprite used when the item is held in the player's hand.

```xml
<SpriteComponent
	image_file="data/items_gfx/in_hand/book_in_hand.png"
></SpriteComponent>
```

### Ability Component

This component is associated with the item's name displayed in the UI.

```xml
<AbilityComponent
	ui_name="$item_book_music_c"
	>
</AbilityComponent>
```