---
title: Homing Projectile Component
category: entities
---

# Homing Projectile Component

This documentation describes the configuration for a homing projectile entity in Noita, focusing on its core components and key attributes for AI-assisted modding.

## Entity Structure

The `homing_projectile.xml` file defines an entity with two primary components: `HomingComponent` and `LuaComponent`.

```xml
<Entity >
	<HomingComponent ... />
	<LuaComponent ... />
	<LuaComponent ... />
</Entity>
```

## HomingComponent

This component dictates the projectile's ability to track and pursue targets.

### Key Attributes:

| Attribute                 | Description                                                                                                | Example Value |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- | :------------ |
| `_tags`                   | Internal tag for identifying this component.                                                               | `homing_projectile` |
| `target_tag`              | The tag of entities this projectile will attempt to home in on. `"-"` means no specific tag is enforced. | `"-"`         |
| `homing_targeting_coeff`  | Controls how strongly the projectile adjusts its trajectory towards the target. Higher values mean tighter turns. | `130.0`       |
| `homing_velocity_multiplier` | Multiplies the projectile's base velocity when homing.                                                     | `0.86`        |
| `detect_distance`         | The maximum distance at which the projectile can detect and begin homing on a target.                      | `300`         |
| `predefined_target`       | If set to `1`, the projectile will attempt to target a specific entity defined elsewhere. `0` means it uses `target_tag`. | `0`           |

## LuaComponent

These components are responsible for the projectile's behavior and execution logic, primarily handled by an external Lua script.

### First LuaComponent:

This component executes the homing script once and then removes the projectile.

| Attribute            | Description                                                                                                | Example Value |
| :------------------- | :--------------------------------------------------------------------------------------------------------- | :------------ |
| `script_source_file` | Path to the Lua script file that contains the projectile's logic.                                          | `data/scripts/projectiles/homing_projectile.lua` |
| `execute_every_n_frame` | How often the script is executed. `1` means every frame.                                                   | `1`           |
| `remove_after_executed` | If `1`, the entity is removed from the game after the script has executed.                               | `1`           |

### Second LuaComponent:

This component also executes the homing script, but at a slower interval. This might be for continuous homing adjustments or other periodic effects.

| Attribute            | Description                                                                                                | Example Value |
| :------------------- | :--------------------------------------------------------------------------------------------------------- | :------------ |
| `script_source_file` | Path to the Lua script file that contains the projectile's logic.                                          | `data/scripts/projectiles/homing_projectile.lua` |
| `execute_every_n_frame` | How often the script is executed. `6` means every 6 frames.                                                | `6`           |