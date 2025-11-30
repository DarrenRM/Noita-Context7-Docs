---
title: Boss Limbs Trigger Entity
category: entities
---

# Boss Limbs Trigger Entity

This entity acts as a trigger for spawning boss limbs when the player enters its collision radius.

## Key Components

### CollisionTriggerComponent

This component defines the area that, when entered by an entity with the `player_unit` tag, will activate the associated Lua script.

*   **width**: `144` - The width of the trigger area.
*   **height**: `70` - The height of the trigger area.
*   **radius**: `160` - The circular radius of the trigger area.
*   **required_tag**: `player_unit` - The tag of the entity that must enter the trigger to activate it.

### LuaComponent

This component links the collision trigger to a specific Lua script that will be executed upon activation.

*   **script\_collision\_trigger\_hit**: `data/entities/animals/boss_limbs/boss_limbs_spawn.lua` - The path to the Lua script to execute when the trigger is hit.
*   **execute\_every\_n\_frame**: `-1` - Indicates the script should execute only once upon the first trigger hit.

### SpriteComponent

This component defines the visual representation of the trigger entity.

*   **image\_file**: `data/entities/animals/boss_limbs/boss_limbs_dormant.png` - The image file used for the sprite.
*   **offset\_y**: `23.5` - Vertical offset for the sprite.
*   **offset\_x**: `21.5` - Horizontal offset for the sprite.

```xml
<Entity>
    <CollisionTriggerComponent
      width="144"
      height="70" 
      radius="160"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/entities/animals/boss_limbs/boss_limbs_spawn.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
	
	<SpriteComponent 
		image_file="data/entities/animals/boss_limbs/boss_limbs_dormant.png" 
		offset_y="23.5"
		offset_x="21.5" >
	</SpriteComponent>
</Entity>
```