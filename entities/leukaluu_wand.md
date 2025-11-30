---
title: Leukaluu Wand
category: entities
---

# Leukaluu Wand

This document describes the Leukaluu Wand entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The Leukaluu Wand is a type of wand that can be forged and is teleportable. It inherits its base properties from `wand_level_03.xml`.

```xml
<Entity tags="teleportable_NOT,item,wand,leukaluu,forgeable" >
	<Base file="data/entities/items/wand_level_03.xml">
	    <HotspotComponent 
	        _tags="shoot_pos" 
	        offset.x="16" 
	        offset.y="0" >
	    </HotspotComponent>
	</Base>
	
	<LuaComponent 
		execute_on_added="1"
		execute_every_n_frame="181"
		remove_after_executed="1"
		script_source_file="data/scripts/gun/procedural/wand_leukaluu.lua" 
		>
	</LuaComponent>
</Entity>
```

## Key Components and Attributes

### Base Entity (`Base`)

*   **`file`**: `data/entities/items/wand_level_03.xml`
    *   Indicates that this wand inherits its fundamental properties from the `wand_level_03.xml` entity. This is crucial for understanding its base stats, spell capacity, and other inherent wand behaviors.

### Hotspot Component (`HotspotComponent`)

*   **`_tags`**: `shoot_pos`
    *   Defines the position from which projectiles are fired.
*   **`offset.x`**: `16`
    *   The horizontal offset of the shooting position.
*   **`offset.y`**: `0`
    *   The vertical offset of the shooting position.

### Lua Component (`LuaComponent`)

*   **`execute_on_added`**: `1`
    *   The script will execute immediately when the entity is added to the game world.
*   **`execute_every_n_frame`**: `181`
    *   The script will execute every 181 frames. This likely controls the wand's firing rate or a specific behavior tied to this interval.
*   **`remove_after_executed`**: `1`
    *   The Lua component will be removed after its first execution. This suggests a one-time effect or initialization.
*   **`script_source_file`**: `data/scripts/gun/procedural/wand_leukaluu.lua`
    *   This is the most significant attribute, pointing to the custom Lua script that defines the unique behavior and spell generation of the Leukaluu Wand. Modders should examine this script to understand its procedural generation logic.