---
title: Touch Grass Projectile
category: entities
---

# Touch Grass Projectile

This entity defines a player projectile that converts nearby materials into "grass_holy" and has a limited lifetime.

## Key Components

### LuaComponent
- **script_source_file**: `data/scripts/projectiles/touch_grass.lua`
- **execute_on_added**: `1` (Script executes when the entity is added)
- **call_init_function**: `1` (Calls the init function of the script)

### MagicConvertMaterialComponent (Primary)
- **from_any_material**: `1` (Can convert any material)
- **to_material**: `grass_holy` (Converts to this material)
- **steps_per_frame**: `7` (Number of conversion steps per frame)
- **loop**: `0` (Does not loop)
- **is_circle**: `1` (Conversion area is a circle)
- **radius**: `30` (Radius of the conversion area)
- **convert_entities**: `1` (Also converts entities within the radius)

### MagicConvertMaterialComponent (Secondary)
- **from_any_material**: `1` (Can convert any material)
- **to_material**: `grass_holy` (Converts to this material)
- **steps_per_frame**: `7` (Number of conversion steps per frame)
- **loop**: `0` (Does not loop)
- **is_circle**: `1` (Conversion area is a circle)
- **radius**: `40` (Radius of the conversion area)

### LifetimeComponent
- **lifetime**: `6` (The projectile exists for 6 seconds)

### AudioComponent
- **file**: `data/audio/Desktop/projectiles.bank`
- **event_root**: `player_projectiles/touch` (Audio event triggered by this projectile)