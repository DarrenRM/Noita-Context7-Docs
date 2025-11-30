---
title: Frozen Effect Entity
category: entities
---

# Frozen Effect Entity

This entity defines the visual and functional aspects of the "FROZEN" status effect in Noita.

## Key Components

### GameEffectComponent
This component governs the core mechanics of the frozen effect.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `effect`         | The identifier for the effect, set to "FROZEN".                          |
| `frames`         | Duration of the effect in game frames (120 frames = 2 seconds).          |
| `disable_movement` | If set to "1", the affected entity's movement is disabled.               |
| `ragdoll_effect` | The effect applied to the entity's ragdoll when frozen.                  |
| `ragdoll_material` | The material applied to the ragdoll, in this case "ice_glass_b2".        |

### AudioComponent
This component handles the sound effects associated with the frozen effect.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `file`       | The audio bank file containing the sound events.                         |
| `event_root` | The root event name for sounds related to the frozen effect.             |