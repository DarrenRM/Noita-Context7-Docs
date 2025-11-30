---
title: Twitchy Status Effect
category: scripts
---

---

# Twitchy Status Effect

This script defines the "Twitchy" status effect in Noita, which causes the player to randomly fire their weapon.

## Core Functionality

The primary effect of "Twitchy" is to force the player's weapon to fire on the next available update. This is achieved by manipulating the `PlatformShooterPlayerComponent`.

### Key Attributes

*   **`mForceFireOnNextUpdate`**: This boolean value within the `PlatformShooterPlayerComponent` is set to `true` to trigger an immediate weapon fire.

## Implementation Details

The script first identifies the entity and its root player entity. It then uses `edit_component` to modify the relevant components.

### `LuaComponent` Modification

*   **`execute_every_n_frame`**: This attribute of the `LuaComponent` is set to a random value between 10 and 160 frames. This determines how often the status effect's logic is re-evaluated, introducing a degree of randomness to when the "Twitchy" effect might trigger again.

### `PlatformShooterPlayerComponent` Modification

*   **`mForceFireOnNextUpdate`**: This is the critical component that directly causes the weapon to fire. When set to `true`, the game's internal firing mechanism is bypassed, and the weapon fires immediately.

## Script Logic Flow

1.  **Get Entity Information**: Retrieves the current entity ID, the player's root entity ID, and the entity's transform (position).
2.  **Set Random Seed**: Initializes a random seed based on the entity's position and the current frame number to ensure varied behavior.
3.  **Player Check**: Ensures the script is operating on the player entity and not some other entity that might have this status effect applied.
4.  **Modify `LuaComponent`**: Randomizes the `execute_every_n_frame` value for the `LuaComponent`.
5.  **Modify `PlatformShooterPlayerComponent`**: Sets `mForceFireOnNextUpdate` to `true`, forcing the player's weapon to fire.