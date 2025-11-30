---
title: Midas Radioactive Conversion Entity
category: entities
---

# Midas Radioactive Conversion Entity

This entity defines a special effect that converts nearby materials into radioactive gold. It's likely used as part of a boss encounter or a unique environmental hazard.

## Key Components

### MagicConvertMaterialComponent

This component handles the core conversion logic.

*   **`to_material`**: `gold_radioactive` - Specifies the material to convert into.
*   **`radius`**: `300` - The area of effect for the conversion.
*   **`steps_per_frame`**: `3` - How many conversion steps occur per game frame.
*   **`from_any_material`**: `1` - Allows conversion from any material type.
*   **`kill_when_finished`**: `0` - The entity does not self-destruct after the conversion is complete.
*   **`clean_stains`**: `0` - Stains are not removed during the conversion.
*   **`is_circle`**: `1` - The conversion radius is circular.
*   **`convert_same_material`**: `0` - Does not convert materials that are already the target material.

### LifetimeComponent

Determines how long the conversion effect lasts.

*   **`lifetime`**: `160` - The entity exists for 160 frames.

### LuaComponent

Triggers a Lua script to execute the conversion logic.

*   **`script_source_file`**: `data/entities/animals/boss_centipede/ending/midas_convert_everything_to_radioactive_gold.lua` - The path to the script that manages the conversion process.
*   **`execute_every_n_frame`**: `159` - The script is executed almost at the end of the entity's lifetime.
*   **`remove_after_executed`**: `1` - The entity is removed from the game after the script has executed.

## Inheritance

*   **`InheritTransformComponent`**: This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties.