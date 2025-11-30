---
title: Midas Effect Entity
category: entities
---

# Midas Effect Entity

This entity implements a "Midas touch" effect, converting nearby materials to gold. It's likely used as part of a boss encounter or special event.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion.

*   **`kill_when_finished`**: `0` - The entity does not destroy itself upon completion of the conversion.
*   **`from_any_material`**: `1` - Can convert any material it encounters.
*   **`steps_per_frame`**: `3` - The number of conversion steps to perform each frame.
*   **`to_material`**: `"gold"` - The target material for conversion.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `300` - The radius of the circular conversion area.
*   **`convert_same_material`**: `0` - Does not convert materials that are already gold.

### LifetimeComponent

Determines how long the entity persists.

*   **`lifetime`**: `160` - The entity will exist for 160 frames.

### LuaComponent

Executes a Lua script to manage the conversion process.

*   **`execute_every_n_frame`**: `159` - The script will execute just before the entity's lifetime ends.
*   **`remove_after_executed`**: `1` - The entity will be removed after the script executes.
*   **`script_source_file`**: `"data/entities/animals/boss_centipede/ending/midas_convert_everything_to_gold.lua"` - The path to the Lua script that controls the conversion logic.