---
title: Meditation Cube Player Effect
category: entities
---

# Meditation Cube Player Effect

This entity defines a special effect applied to the player when interacting with a meditation cube.

## Key Components

### `InheritTransformComponent`

This component indicates that the entity inherits its transformation properties from its parent. In this context, it means the effect will be tied to the player's position and orientation.

### `GameEffectComponent`

This is the core component that defines the actual game effect.

*   **`effect`**: `EDIT_WANDS_EVERYWHERE`
    *   This attribute specifies the type of game effect. `EDIT_WANDS_EVERYWHERE` grants the player the ability to edit their wands from any location.
*   **`frames`**: `36000`
    *   This attribute defines the duration of the effect in game frames. 36000 frames is equivalent to 10 minutes (36000 frames / 60 frames per second / 60 seconds per minute).

## Notes

*   The effect is designed to be removed when the player teleports back from the meditation cube.