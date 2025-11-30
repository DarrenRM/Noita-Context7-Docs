---
title: Chaotic Transmutation Material Effect
category: entities
---

# Chaotic Transmutation Material Effect

This entity defines a magical effect that transmutes materials within a specified radius. It's designed to be a dynamic and potentially chaotic element within the game.

## MagicConvertMaterialComponent

This component handles the core material transmutation logic.

### Key Attributes:

*   **`from_material_tag`**: `"[chaotic_transmutation]"` - Specifies the tag of materials that this effect will target for transmutation.
*   **`to_material`**: `"water"` - The material that the targeted materials will be converted into.
*   **`radius`**: `"32"` - The radius (in pixels) around the effect's origin within which transmutation will occur.
*   **`steps_per_frame`**: `"48"` - Controls the intensity or speed of the transmutation process per frame. Higher values mean faster conversion.
*   **`loop`**: `"1"` - Indicates that the transmutation effect should repeat continuously.
*   **`kill_when_finished`**: `"0"` - The effect will not be removed automatically once it has completed its process (though other game logic might remove it).
*   **`clean_stains`**: `"0"` - Stains are not cleaned by this transmutation effect.
*   **`is_circle`**: `"1"` - The transmutation area is circular.
*   **`_enabled`**: `"0"` - This effect is currently disabled by default.
*   **`_tags`**: `"transmutation"` - A tag associated with this component, useful for scripting and game logic.

## LuaComponent

This component links the visual and functional aspects of the effect to a Lua script.

### Key Attributes:

*   **`script_source_file`**: `"data/scripts/projectiles/transmutation.lua"` - The path to the Lua script that controls the behavior and execution of this entity.
*   **`remove_after_executed`**: `"1"` - The Lua script will be removed after it has been executed.
*   **`execute_every_n_frame`**: `"1"` - The Lua script will execute every frame.