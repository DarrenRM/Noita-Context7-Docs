---
title: Debug Settings for Noita Modding
source: https://noita.wiki.gg/wiki/Documentation:DebugSettings
category: modding-wiki
---

# Debug Settings for Noita Modding

This documentation outlines the various debug settings available within Noita, which are invaluable tools for modders. Understanding and utilizing these settings can significantly streamline the mod development process by providing insights into game mechanics, entity behavior, and potential issues.

## Accessing Debug Settings

Debug settings are typically accessed through the game's console or by modifying configuration files. The exact method may vary depending on your Noita installation and any mods you have installed that alter debug functionality.

## Core Debug Commands and Features

While the original wiki page indicated no specific text, the context of "DebugSettings" implies a range of commands and configurations that can be enabled or modified to aid in debugging. These often include:

*   **Console Commands:** A set of commands that can be typed into the in-game console to trigger specific debug actions or display information.
*   **Configuration Flags:** Boolean or numerical values that can be toggled in configuration files to enable or disable certain debug features.
*   **Logging:** Mechanisms to output detailed information about game events, entity states, and script execution to log files.

### Example: Enabling Debug Logging (Conceptual)

Many games, including Noita, allow for the enabling of detailed logging. This is often done by setting a specific value in a configuration file.

For instance, a hypothetical `config.ini` might contain a line like this:

```ini
debug_logging_enabled = true
```

Or, a Lua script might be used to toggle this:

```lua
-- Example of enabling debug logging via Lua
Debug.SetLoggingLevel(Debug.LOG_LEVEL_VERBOSE)
```

### Example: Displaying Entity Information (Conceptual)

A common debug feature is the ability to inspect entities in the game world. This could be triggered by a console command or a keybind.

**Console Command Example:**

```
/show_entity_info <entity_id>
```

This command would hypothetically display detailed information about the entity with the specified ID, such as its components, current state, and position.

## Modding-Specific Debugging Tools

Modders often rely on specific tools and techniques to debug their creations. These can include:

*   **Error Reporting:** Mechanisms that catch and report Lua errors or other script-related issues.
*   **Performance Profiling:** Tools to identify performance bottlenecks within mods.
*   **Asset Inspection:** Ways to view and verify the properties of custom assets being loaded by a mod.

### Lua API for Debugging

The Noita Lua API provides functions that can be used for debugging purposes. While specific functions for `DebugSettings` were not detailed on the original page, a general understanding of the Lua API is crucial.

You can find more information on the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Important Links for Modding

*   [Noita Modding Wiki](https://noita.wiki.gg/wiki/Modding)
*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)

---