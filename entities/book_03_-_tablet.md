---
title: Book 03 - Tablet
category: entities
---

# Book 03 - Tablet

This document describes the `book_03.xml` entity, representing a tablet item in Noita.

## Entity Definition

The core of this entity is a `Base` component, inheriting properties from `data/entities/items/books/base_book.xml`.

```xml
<Entity tags="tablet,normal_tablet">
	<Base file="data/entities/items/books/base_book.xml">
		<!-- ... components ... -->
	</Base>
</Entity>
```

## Key Components

### UIInfoComponent

This component defines the in-game display name for the tablet.

```xml
<UIInfoComponent
	name="$booktitle03"
	>
</UIInfoComponent>
```

*   **`name`**: `$booktitle03` - This is a localization key that will be translated into the actual display name (e.g., "Tablet").

### ItemComponent

This component defines the item's properties when it's in the player's inventory or in the world.

```xml
<ItemComponent
	item_name="$booktitle03"
	ui_description="$bookdesc03"
	>
</ItemComponent>
```

*   **`item_name`**: `$booktitle03` - Links to the same localization key as `UIInfoComponent` for consistency.
*   **`ui_description`**: `$bookdesc03` - A localization key for the item's descriptive text.

### AbilityComponent

This component is often used for items that grant abilities or have specific interactions.

```xml
<AbilityComponent
	ui_name="$booktitle03"
	>
</AbilityComponent>
```

*   **`ui_name`**: `$booktitle03` - Again, links to the localization key for the item's name, suggesting it might be displayed in ability-related UI elements.

## Summary

`book_03.xml` defines a standard tablet item. Its functionality and appearance are primarily determined by its inherited `Base` component and the localization keys used for its name and description. The `tags` attribute indicates it's a "tablet" and a "normal_tablet".