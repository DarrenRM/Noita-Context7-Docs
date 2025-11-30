---
title: Empty Potion Pickup
category: entities
---

# Empty Potion Pickup

This entity represents an empty potion pickup in Noita. It inherits its base properties from the generic `potion.xml` but has its `LuaComponent` disabled.

## Key Attributes

*   **`Base`**: Inherits from `data/entities/items/pickup/potion.xml`. This means it shares fundamental properties with other potion pickups.
*   **`LuaComponent`**:
    *   **`_enabled="0"`**: This is the crucial difference. The Lua component, which typically handles item behavior and effects, is disabled for this empty potion. This prevents it from having any active effect when picked up.

## Usage in Modding

This entity is primarily useful for:

*   **Creating visual placeholders**: You might use this as a visual element in a mod that doesn't require a functional potion.
*   **As a base for new potion types**: While its Lua is disabled, you could enable it and modify its properties to create a new potion effect.
*   **Testing or debugging**: It can serve as a simple, non-interactive item for testing pickup mechanics.

## Example XML Structure

```xml
<Entity>
	<Base file="data/entities/items/pickup/potion.xml">
		<LuaComponent 
			_enabled="0"
		></LuaComponent>
	</Base>
</Entity>
```