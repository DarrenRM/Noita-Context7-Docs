---
title: Magic Conversion Utilities
category: scripts
---

# Magic Conversion Utilities

This script provides utility functions for creating magic that converts one material into another within the game world.

## `convert_material(x, y, from_material, to_material, clean_stains)`

This function creates an entity at the specified `x` and `y` coordinates that will convert a target material (`from_material`) into a new material (`to_material`).

### Parameters

| Parameter      | Type   | Description                                                                 |
| -------------- | ------ | --------------------------------------------------------------------------- |
| `x`            | number | The X-coordinate where the conversion entity will be spawned.               |
| `y`            | number | The Y-coordinate where the conversion entity will be spawned.               |
| `from_material`| string | The internal name of the material to be converted (e.g., "water").        |
| `to_material`  | string | The internal name of the material to convert to (e.g., "acid").           |
| `clean_stains` | boolean| (Optional) If `true`, this will also clean any stains of the `from_material` at the location. Defaults to `false`. |

### Usage Example

```lua
-- Convert water to acid at the player's current position
convert_material(player.x, player.y, "water", "acid")

-- Convert lava to gold and clean any lava stains
convert_material(player.x, player.y, "lava", "gold", true)
```

### Internal Mechanism

This function spawns a dedicated entity (`data/entities/misc/magic/convert_material.xml`) which is configured with a `MagicConvertMaterialComponent`. This component handles the actual material conversion logic based on the provided parameters.