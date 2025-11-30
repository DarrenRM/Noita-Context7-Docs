---
title: Book 07 Entity
category: entities
---

# Book 07 Entity

This document describes the Noita entity for "Book 07". It's a standard tablet item with associated UI and item components.

## Entity Definition

The core entity definition uses a `Base` file, indicating it inherits properties from a generic book entity.

```xml
<Entity tags="tablet,forgeable,normal_tablet">
	<Base file="data/entities/items/books/base_book.xml">
		<!-- ... components ... -->
	</Base>
</Entity>
```

### Key Attributes:

*   **tags**: `tablet`, `forgeable`, `normal_tablet` - These tags define the item's type and behavior within the game.

## Components

### UIInfoComponent

This component defines the user interface information for the book.

```xml
<UIInfoComponent
	name="$booktitle07"
	>
</UIInfoComponent>
```

#### Key Attributes:

*   **name**: `$booktitle07` - Refers to a localization key for the book's title.

### ItemComponent

This component defines the item's properties when it's in the player's inventory or used.

```xml
<ItemComponent
	item_name="$booktitle07"
	ui_description="$bookdesc07"
	>
</ItemComponent>
```

#### Key Attributes:

*   **item\_name**: `$booktitle07` - Refers to a localization key for the item's name.
*   **ui\_description**: `$bookdesc07` - Refers to a localization key for the item's description.

### AbilityComponent

This component is associated with the book's potential abilities or actions.

```xml
<AbilityComponent
	ui_name="$booktitle07"
	>
</AbilityComponent>
```

#### Key Attributes:

*   **ui\_name**: `$booktitle07` - Refers to a localization key for the UI name, likely the same as the book's title.