---
title: Frozen Speed Up Effect
category: entities
---

# Frozen Speed Up Effect

This entity defines a game effect that temporarily speeds up entities while they are frozen.

## Key Components

### GameEffectComponent

This component governs the core behavior of the game effect.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `effect`         | Specifies the type of effect applied. `FROZEN_SPEED_UP` indicates the intended behavior. |
| `frames`         | The duration of the effect in game frames (120 frames = 2 seconds at 60 FPS). |
| `disable_movement` | A value of `0` means movement is *not* disabled by this effect.           |
| `ragdoll_effect` | When the entity becomes a ragdoll, it will be affected by the `FROZEN` effect. |
| `ragdoll_material` | The material applied to the ragdoll when frozen, set to `ice_glass_b2`.     |

### AudioComponent

This component handles the sound associated with the effect.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events (`data/audio/Desktop/misc.bank`). |
| `event_root`| The root event name for sounds related to this effect (`game_effect/frozen`). |