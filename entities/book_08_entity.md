---
title: Book 08 Entity
category: entities
---

# Book 08 Entity

This document describes the Noita entity for "Book 08", a tablet item.

## Entity Definition

The `book_08.xml` file defines a tablet entity with specific UI and item properties.

```xml
<Entity tags="tablet,forgeable,normal_tablet">
	<Base file="data/entities/items/books/base_book.xml">
		<UIInfoComponent
			name="$booktitle08"
			>
		</UIInfoComponent>
		
		<ItemComponent
			item_name="$booktitle08"
			ui_description="$bookdesc08"
			>
		</ItemComponent>
		
		<AbilityComponent
			ui_name="$booktitle08"
			>
		</AbilityComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

### Entity Tags

*   `tablet`: Indicates this entity is a tablet item.
*   `forgeable`: Suggests the item can be forged.
*   `normal_tablet`: Further categorizes it as a standard tablet.

### Base Component

*   `file="data/entities/items/books/base_book.xml"`: This entity inherits its core functionality from a base book entity.

### UIInfoComponent

*   `name="$booktitle08"`: Defines the internal name or identifier for the book's title, likely referencing a localization string.

### ItemComponent

*   `item_name="$booktitle08"`: Links the item's display name to a localization string.
*   `ui_description="$bookdesc08"`: Links the item's tooltip description to a localization string.

### AbilityComponent

*   `ui_name="$booktitle08"`: Specifies the UI name for any associated ability, also referencing a localization string.