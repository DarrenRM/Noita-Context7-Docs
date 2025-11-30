---
title: Debug Settings Ollis
source: https://noita.wiki.gg/wiki/Documentation:DebugSettingsOllis
category: modding-wiki
---

# Debug Settings Ollis

This document details the `DebugSettingsOllis` file, a crucial component for understanding and manipulating Noita's internal game settings. For AI-assisted modding, this file provides insights into various game parameters that can be adjusted, offering a deeper level of control and customization beyond standard modding practices. Understanding these settings can unlock unique modding possibilities and help debug complex mod interactions.

## Overview of DebugSettingsOllis

The `DebugSettingsOllis` file contains a collection of settings that influence various aspects of Noita's gameplay, debugging, and internal logic. While not directly moddable in the same way as other game assets, understanding its contents is vital for advanced modders and for debugging issues that may arise from mod conflicts or unexpected game behavior.

### File Location

The `DebugSettingsOllis` file is typically located within the game's installation directory, often found in a path similar to:

`Noita\data\scripts\debug`

### Purpose for Modding

For AI-assisted modding, `DebugSettingsOllis` serves as a reference for:

*   **Understanding Game Mechanics:** It reveals how certain game features are controlled and parameterized.
*   **Debugging:** By knowing the default or expected values, modders can more easily identify discrepancies caused by their mods.
*   **Advanced Customization:** While direct modification is discouraged and can break the game, understanding these settings can inform the creation of mods that interact with or mimic these behaviors.

## Key Settings and Parameters

The `DebugSettingsOllis` file is structured with various sections and parameters that control different aspects of the game. The following are some of the key areas and their significance.

### Biome Settings

This section likely contains parameters related to the generation and properties of different biomes within the game.

### Entity Settings

Parameters governing the behavior, spawning, and properties of entities in the game.

### Gameplay Settings

Various toggles and values that affect core gameplay mechanics, such as physics, AI, and progression.

### Rendering and Visuals

Settings that influence how the game is rendered, including visual effects, lighting, and graphical options.

### AI and Pathfinding

Parameters related to the artificial intelligence of enemies and NPCs, as well as their pathfinding capabilities.

### Physics and Collisions

Settings that control the game's physics engine, including gravity, collision detection, and object interactions.

### Debugging and Logging

Options related to enabling or disabling debug features, logging information, and performance monitoring.

## Example Usage (Conceptual)

While direct modification of `DebugSettingsOllis` is not recommended for standard modding, understanding its structure can be helpful when working with Lua scripts that might interact with or query similar game states.

For instance, if you were developing a mod that needed to understand the current game difficulty or a specific biome's properties, you might look for analogous settings or functions within the Lua API that are influenced by these debug settings.

**Note:** The following is a conceptual example and does not represent direct modification of `DebugSettingsOllis`.

```lua
-- This is a hypothetical example of how a mod might interact with game settings
-- It does NOT directly modify DebugSettingsOllis.

local game_state = require("game_state") -- Assuming a hypothetical game_state module

-- Get a value that might be influenced by debug settings (e.g., enemy aggression)
local enemy_aggression_level = game_state.get_setting("enemy_aggression")

if enemy_aggression_level > 0.7 then
    print("Enemies are highly aggressive!")
    -- Implement mod logic based on high aggression
else
    print("Enemies are less aggressive.")
    -- Implement mod logic for lower aggression
end

-- Example of checking a debug flag (if exposed via API)
if game_state.is_debug_mode_enabled("show_hitboxes") then
    print("Hitboxes are currently visible for debugging.")
end
```

## Important Links

*   [Noita Modding API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Noita Wiki - Debugging](https://noita.wiki.gg/wiki/Debugging)

---