---
title: No Wand Editing Effect
category: entities
---

# No Wand Editing Effect

This entity defines a game effect that prevents the player from editing wands.

## Key Components

### GameEffectComponent
This component applies the specified game effect.

*   **effect**: `NO_WAND_EDITING` - This is the core identifier for the effect that disables wand editing.
*   **frames**: `600` - The duration of the effect in frames (approximately 10 seconds at 60 FPS).

## Usage

This entity is typically spawned in the game world to apply the "no wand editing" debuff to the player.