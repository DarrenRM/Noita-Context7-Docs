---
title: Starting Potion Item
category: guides
---

<Entity>
	<Base file="data/entities/items/pickup/potion.xml" >
		<LuaComponent 
			script_source_file="data/scripts/items/potion_starting.lua" 
		></LuaComponent>
	</Base>
</Entity>
```

---
title: Starting Potion Item
category: entities/items/pickup
---

# Starting Potion Item

This document describes the configuration for a starting potion item in Noita, intended for AI-assisted modding.

## Entity Configuration

The `potion_starting.xml` file defines a basic potion item.

### Key Elements

*   **`<Entity>`**: The root element for the entity definition.
*   **`<Base file="data/entities/items/pickup/potion.xml">`**: This indicates that the starting potion inherits its core properties and behaviors from a general `potion.xml` file. This is a common practice for reusing common item logic.
*   **`<LuaComponent script_source_file="data/scripts/items/potion_starting.lua">`**: This is the crucial part that customizes the behavior of this specific potion. It links to a Lua script (`potion_starting.lua`) that defines its unique properties, such as what kind of potion it is, its effects, and how it's used.

## Lua Scripting

The behavior of the starting potion is primarily controlled by its associated Lua script.

### `data/scripts/items/potion_starting.lua`

This script is responsible for defining the specific characteristics of the starting potion. While the content of this script is not provided in the source XML, it would typically handle:

*   **Potion Type**: Identifying the potion (e.g., health, mana, stamina).
*   **Effects**: Defining the buffs or debuffs applied when consumed.
*   **Visuals**: Potentially influencing the potion's appearance or particle effects.
*   **Interaction**: How the player interacts with and consumes the potion.

## Summary

The `potion_starting.xml` entity is a simple wrapper that leverages a base potion configuration and customizes its behavior through a dedicated Lua script. This approach allows for efficient creation of various potion types by reusing common functionality and defining unique aspects in separate script files.