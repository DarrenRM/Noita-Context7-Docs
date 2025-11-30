---
title: Persistent Flags
category: scripts
---

# Persistent Flags

Persistent flags are used in Noita to track specific game states that should persist across game sessions. These are typically used for unlocking secrets, tracking progress, or enabling certain game mechanics.

## Key Persistent Flags

The `persistent_flags` table in Noita primarily serves as a registry for these flags. While the provided snippet is minimal, it demonstrates the core concept.

### `biome_0_secret_unlocked`

This flag, as shown in the example, likely indicates whether a secret within the first biome has been unlocked by the player.

```lua
persistent_flags = 
{
	biome_0_secret_unlocked = "biome_0_secret_unlocked",
}
```

## Usage

In the context of modding, you would typically interact with these flags to:

*   **Check if a flag is set:** To determine if a player has met certain conditions.
*   **Set a flag:** To mark a condition as met, such as unlocking a secret after a specific event.
*   **Unset a flag:** To reset a condition, though this is less common for persistent flags.

The actual implementation of checking and setting these flags would occur in other Lua scripts that reference this `persistent_flags` definition.