---
title: Evil Sarcophagus Prop
category: entities
---

---

# Evil Sarcophagus Prop

This document describes the configuration for the "Evil Sarcophagus" prop entity in Noita, intended for AI-assisted modding.

## Entity Definition

The `sarcophagus_evil.xml` file defines a prop entity with the following key tags:

*   `hittable`: Indicates the entity can be damaged.
*   `mortal`: The entity can be destroyed.
*   `prop`: Identifies it as a prop object in the game world.
*   `pixelsprite`: The entity is rendered using pixel art.

## Components

### PixelSpriteComponent

This component handles the visual representation of the sarcophagus.

*   `image_file`: `data/props_gfx/sarcophagus_evil.png` - Specifies the sprite image.
*   `anchor_x`, `anchor_y`: `7`, `28` - Defines the sprite's anchor point.
*   `create_box2d_bodies`: `1` - Enables physics body creation for collision.
*   `clean_overlapping_pixels`: `1` - Helps in rendering clean sprite edges.
*   `material`: `rock_loose` - Sets the base material for physics interactions.

### SimplePhysicsComponent

This component governs basic physics properties.

*   `can_go_up`: `0` - Prevents the sarcophagus from moving upwards.

### VelocityComponent

This component is present to allow for velocity-related physics, though not explicitly configured here.

## Scripting (Commented Out)

The following `LuaComponent` is commented out in the provided XML. If enabled, it would trigger specific Lua scripts upon collision or death.

```xml
<!--
	<LuaComponent
    execute_every_n_frame="-1"
    script_collision_trigger_hit="data/scripts/props/sarcophagus_spirit.lua"
    script_death="data/scripts/props/sarcophagus_spirit.lua"
    remove_after_executed="0">
  </LuaComponent>
-->
```

*   `script_collision_trigger_hit`: `data/scripts/props/sarcophagus_spirit.lua` - Script to execute when the entity is hit.
*   `script_death`: `data/scripts/props/sarcophagus_spirit.lua` - Script to execute when the entity is destroyed.
*   `remove_after_executed`: `0` - The entity will not be removed after the script executes.

This configuration suggests the Evil Sarcophagus is a static, hittable prop that, if its Lua components were active, would interact with the `sarcophagus_spirit.lua` script.