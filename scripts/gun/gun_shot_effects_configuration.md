---
title: Gun Shot Effects Configuration
category: scripts/gun
---

# Gun Shot Effects Configuration

This documentation outlines the configuration parameters for gun shot effects in Noita, specifically focusing on how these effects are initialized, passed to the game, read, and copied.

## Key Attributes

The primary attribute managed by these functions is `recoil_knockback`.

### `recoil_knockback`

*   **Description:** Controls the knockback force applied to the player or entity when the gun is fired.
*   **Type:** Number

## Functions

### `ConfigGunShotEffects_Init( value )`

*   **Purpose:** Initializes the default values for gun shot effect configurations.
*   **Key Action:** Sets `recoil_knockback` to `0` by default.

```lua
function ConfigGunShotEffects_Init( value )
    value.recoil_knockback = 0
end
```

### `ConfigGunShotEffects_PassToGame( value )`

*   **Purpose:** Passes the configured gun shot effect parameters to the game engine.
*   **Key Action:** Registers the `recoil_knockback` value with the game.

```lua
function ConfigGunShotEffects_PassToGame( value )
    RegisterGunShotEffects(
        value.recoil_knockback
  )
end
```

### `ConfigGunShotEffects_ReadToLua( recoil_knockback )`

*   **Purpose:** Reads `recoil_knockback` values and stores them in a global data structure.
*   **Key Action:** Assigns the provided `recoil_knockback` to `__globaldata.recoil_knockback`.

```lua
function ConfigGunShotEffects_ReadToLua( recoil_knockback )
    __globaldata = {}
    __globaldata.recoil_knockback = recoil_knockback
end
```

### `ConfigGunShotEffects_Copy( source, dest )`

*   **Purpose:** Copies gun shot effect configurations from a source to a destination.
*   **Key Action:** Copies the `recoil_knockback` value from `source` to `dest`.

```lua
function ConfigGunShotEffects_Copy( source, dest )
    dest.recoil_knockback = source.recoil_knockback
end
```