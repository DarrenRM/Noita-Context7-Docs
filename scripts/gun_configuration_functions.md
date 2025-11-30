---
title: Gun Configuration Functions
category: scripts
---

# Gun Configuration Functions

This document outlines the core Lua functions used for configuring and registering guns in Noita, specifically focusing on the `ConfigGun_Init`, `ConfigGun_PassToGame`, `ConfigGun_ReadToLua`, and `ConfigGun_Copy` functions. These functions are essential for defining the behavior and properties of player-held weapons.

## `ConfigGun_Init(value)`

This function initializes a `value` table with default gun properties. It's typically called when a gun is first loaded or created.

### Key Attributes:

*   `actions_per_round`: The number of spells that can be cast per trigger pull.
    *   Default: `1`
*   `shuffle_deck_when_empty`: Determines if the spell deck is shuffled when it runs out of spells.
    *   Default: `false`
*   `reload_time`: The time in frames it takes for the gun to reload after all actions are used.
    *   Default: `40`
*   `deck_capacity`: The maximum number of spells the gun can hold in its deck.
    *   Default: `2`

## `ConfigGun_PassToGame(value)`

This function takes a configured `value` table and registers the gun with the game engine.

### Key Parameters:

*   `value.actions_per_round`: Passed directly to the game's gun registration.
*   `value.shuffle_deck_when_empty`: Passed directly to the game's gun registration.
*   `value.reload_time`: Passed directly to the game's gun registration.
*   `value.deck_capacity`: Passed directly to the game's gun registration.

## `ConfigGun_ReadToLua(actions_per_round, shuffle_deck_when_empty, reload_time, deck_capacity)`

This function reads gun configuration values and stores them in a global table `__globaldata`. This is often used for loading gun data from external sources or for internal game state management.

### Key Attributes Stored in `__globaldata`:

*   `actions_per_round`
*   `shuffle_deck_when_empty`
*   `reload_time`
*   `deck_capacity`

## `ConfigGun_Copy(source, dest)`

This function copies gun configuration properties from a `source` table to a `dest` table. This is useful for duplicating gun configurations or for transferring settings between different gun instances.

### Key Attributes Copied:

*   `actions_per_round`
*   `shuffle_deck_when_empty`
*   `reload_time`
*   `deck_capacity`