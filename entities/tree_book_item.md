---
title: Tree Book Item
category: entities
---

# Tree Book Item

This document describes the `book_tree.xml` entity, representing a book item in Noita that grants the "Tree" spell.

## Entity Definition

The core of this item is defined by the `Base` entity, which inherits properties from `data/entities/items/books/base_book.xml`.

```xml
<Entity tags="tablet,normal_tablet">
	<!-- in the tree  -->
	<Base file="data/entities/items/books/base_book.xml">
		<!-- ... other components ... -->
	</Base>
</Entity>
```

## Key Components and Attributes

### ParticleEmitterComponent

This component defines the visual effect associated with the book when it's in the game world.

*   **`emitted_material_name`**: Specifies the material that will be emitted as particles.
    *   `spark_blue`: Indicates that blue sparks will be emitted.

```xml
<ParticleEmitterComponent
	emitted_material_name="spark_blue"
>
</ParticleEmitterComponent>
```

### UIInfoComponent

This component provides information displayed in the user interface, such as the book's title.

*   **`name`**: The internal identifier for the UI name.
    *   `$booktitle_tree`: Refers to a localization key for the book's title, likely "Tree".

```xml
<UIInfoComponent
	name="$booktitle_tree"
>
</UIInfoComponent>
```

### ItemComponent

This component defines the item's properties when it's picked up or interacted with as an item.

*   **`item_name`**: The internal identifier for the item's name.
    *   `$booktitle_tree`: Links to the same localization key as `UIInfoComponent.name`.
*   **`ui_description`**: The localization key for the item's description.
    *   `$bookdesc_tree`: Refers to a localization key for the book's description, explaining the "Tree" spell.

```xml
<ItemComponent
	item_name="$booktitle_tree"
	ui_description="$bookdesc_tree"
>
</ItemComponent>
```

### AbilityComponent

This component links the item to a specific magical ability or spell.

*   **`ui_name`**: The name displayed in the spell selection UI.
    *   `$booktitle_tree`: Again, links to the localization key for the spell's name.

```xml
<AbilityComponent
	ui_name="$booktitle_tree"
>
</AbilityComponent>
```