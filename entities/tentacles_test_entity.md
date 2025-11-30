---
title: Tentacles Test Entity
category: entities
---

# Tentacles Test Entity

This document describes the `tentacles_test.xml` entity, designed for testing tentacle-like behaviors in Noita. It utilizes a combination of sprite, physics, and Lua components to achieve its functionality.

## Key Components

### SpriteComponent
Defines the visual appearance of the entity.

*   **`image_file`**: `data/enemies_gfx/acidshooter.xml` - Specifies the graphical asset used for the sprite.
*   **`offset_x`**: `0` - Horizontal offset of the sprite.
*   **`offset_y`**: `0` - Vertical offset of the sprite.

### PhysicsBodyComponent
Manages the physical properties of the entity.

*   **`uid`**: `1` - Unique identifier for the physics body.
*   **`allow_sleep`**: `0` - Prevents the physics body from sleeping.
*   **`fixed_rotation`**: `1` - The entity's rotation is fixed.
*   **`is_bullet`**: `0` - Not a bullet.
*   **`is_static`**: `0` - The entity is not static.
*   **`is_kinematic`**: `1` - The entity's movement is controlled by external forces (scripts).
*   **`is_character`**: `0` - Not a character.
*   **`auto_clean`**: `1` - The physics body will be automatically cleaned up.

### PhysicsShapeComponent
Defines the collision shape of the entity.

*   **`is_circle`**: `1` - The collision shape is a circle.
*   **`friction`**: `0.75` - The friction applied to the shape.
*   **`restitution`**: `0.1` - The bounciness of the shape.
*   **`density`**: `0` - The density of the shape.
*   **`local_position_x`**: `0` - Horizontal offset of the shape's center.
*   **`local_position_y`**: `-0.45` - Vertical offset of the shape's center.
*   **`radius_x`**: `0.6` - The radius of the circular shape.

### LuaComponent
Attaches a Lua script to the entity for custom behavior.

*   **`_enabled`**: `1` - The component is enabled.
*   **`execute_every_n_frame`**: `1` - The script executes every frame.
*   **`remove_after_executed`**: `1` - The component will be removed after its script has executed once.
*   **`script_source_file`**: `data/scripts/animals/tentacles.lua` - The path to the Lua script that controls the entity's behavior.

### LightComponent
Adds a light source to the entity.

*   **`_enabled`**: `1` - The component is enabled.
*   **`radius`**: `70` - The radius of the light's influence.
*   **`r`**: `149` - Red component of the light color.
*   **`g`**: `255` - Green component of the light color.
*   **`b`**: `149` - Blue component of the light color.

```xml
<Entity >
 

	<SpriteComponent 
		image_file="data/enemies_gfx/acidshooter.xml" 
		offset_x="0"
		offset_y="0">
	</SpriteComponent>

	<PhysicsBodyComponent
		uid="1"
		allow_sleep="0"
		fixed_rotation="1"
		is_bullet="0"
		is_static="0"
		is_kinematic="1"
		is_character="0"
		go_through_sand="0"
		gridworld_box2d="0"
		auto_clean="1"
		on_death_leave_physics_body="0"
		update_entity_transform="0"
	>
	</PhysicsBodyComponent>

	<PhysicsShapeComponent
		recreate="0"
		is_circle="1"				
		friction="0.75"
		restitution="0.1"
		density="0"		
		local_position_x="0"
		local_position_y="-0.45"	
		radius_x="0.6"	
		>
	</PhysicsShapeComponent>
  
	<LuaComponent 
	    _enabled="1" 
	    execute_every_n_frame="1"
	    remove_after_executed="1"
	    script_source_file="data/scripts/animals/tentacles.lua"
	    >
	</LuaComponent>

	<LightComponent 
	    _enabled="1" 
	    radius="70" 
		r="149"
		g="255"
		b="149">
    </LightComponent>

</Entity>
```