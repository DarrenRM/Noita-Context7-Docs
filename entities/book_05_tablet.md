---
title: Book 05 (Tablet)
category: entities
---

# Book 05 (Tablet)

This document describes the Noita entity for "Book 05", which functions as a tablet item.

## Entity Definition

The core entity definition for Book 05 is as follows:

```xml
<Entity tags="tablet,forgeable,normal_tablet">
	<!-- under the lavalake -->

	<Base file="data/entities/items/books/base_book.xml">
		<UIInfoComponent
			name="$booktitle05"
			>
		</UIInfoComponent>
		
		<ItemComponent
			item_name="$booktitle05"
			ui_description="$bookdesc05"
			>
		</ItemComponent>
		
		<AbilityComponent
			ui_name="$booktitle05"
			>
		</AbilityComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

This entity inherits from `base_book.xml` and primarily defines its identity and UI representation.

### Base Entity (`<Base file="data/entities/items/books/base_book.xml">`)

This indicates that Book 05 uses the standard template for books, inheriting common properties and behaviors.

### UI Information (`<UIInfoComponent>`)

*   **`name="$booktitle05"`**: This attribute defines the in-game name of the book, likely referencing a localization string for "Book 05".

### Item Properties (`<ItemComponent>`)

*   **`item_name="$booktitle05"`**: Similar to `UIInfoComponent`, this links the item's internal name to a localization string.
*   **`ui_description="$bookdesc05"`**: This attribute specifies the in-game description for the item, referencing a localization string for "Book 05 description".

### Ability Component (`<AbilityComponent>`)

*   **`ui_name="$booktitle05"`**: This attribute sets the name displayed when the book's ability is referenced, again using a localization string.

## Tags

The entity possesses the following tags:

*   `tablet`: Indicates this item is a tablet.
*   `forgeable`: Suggests the item can be forged.
*   `normal_tablet`: Further categorizes it as a standard tablet.

## Notes

The comment `<!-- under the lavalake -->` suggests a potential spawn location or context for this item, though it's not directly implemented in the entity's XML.