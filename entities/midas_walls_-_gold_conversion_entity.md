---
title: Midas Walls - Gold Conversion Entity
category: entities
---

---

# Midas Walls - Gold Conversion Entity

This entity is responsible for converting surrounding materials into gold, simulating a "Midas touch" effect. It's typically used in boss encounters or specific environmental events.

## Key Components

### MagicConvertMaterialComponent

This component handles the core material conversion logic.

*   **`to_material`**: `gold_static` - Specifies the target material to convert to.
*   **`radius`**: `300` - The area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - Controls the intensity and speed of the conversion process.
*   **`from_any_material`**: `1` - Allows conversion from any existing material.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`kill_when_finished`**: `0` - The entity persists after the conversion is complete.
*   **`clean_stains`**: `0` - Stains are not removed during conversion.

### LuaComponent

This component triggers a Lua script to execute the conversion.

*   **`script_source_file`**: `data/entities/animals/boss_centipede/ending/midas_convert_everything_to_gold.lua` - The path to the Lua script that manages the conversion process.
*   **`execute_every_n_frame`**: `159` - The script executes every 159 frames.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its script has executed once.