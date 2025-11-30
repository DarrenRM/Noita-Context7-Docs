---
title: Book 01 Entity
category: entities
---

# Book 01 Entity

This document describes the `book_01.xml` entity, representing a basic book item in Noita.

## Entity Definition

The `book_01.xml` entity is defined as follows:

```xml
<Entity tags="tablet,normal_tablet">
	<Base file="data/entities/items/books/base_book.xml">
		<UIInfoComponent
			name="$booktitle01"
			>
		</UIInfoComponent>
		
		<ItemComponent
			item_name="$booktitle01"
			ui_description="$bookdesc01"
			>
		</ItemComponent>
		
		<AbilityComponent
			ui_name="$booktitle01"
			>
		</AbilityComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

This entity primarily inherits from `base_book.xml` and customizes its UI and item properties.

### Base Component

*   **`file`**: `data/entities/items/books/base_book.xml`
    *   This indicates that `book_01.xml` inherits its fundamental properties and behaviors from the generic book base entity.

### UIInfoComponent

*   **`name`**: `$booktitle01`
    *   This is a localization key that defines the display name of the book in the game's user interface.

### ItemComponent

*   **`item_name`**: `$booktitle01`
    *   Similar to `UIInfoComponent.name`, this specifies the internal item name, often used for referencing and localization.
*   **`ui_description`**: `$bookdesc01`
    *   This is a localization key for the descriptive text that appears when hovering over the item in the UI.

### AbilityComponent

*   **`ui_name`**: `$booktitle01`
    *   This attribute is used to define the name of the ability associated with this book when it's learned or equipped, linking it to the same localization key as the book's title.

## Summary

The `book_01.xml` entity is a simple book item that leverages a base book entity. Its primary function is to display a name and description defined by localization keys (`$booktitle01` and `$bookdesc01`), and it is associated with an ability also referenced by `$booktitle01`.