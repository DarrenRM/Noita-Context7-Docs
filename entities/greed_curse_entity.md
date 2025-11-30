---
title: Greed Curse Entity
category: entities
---

---

# Greed Curse Entity

This entity defines the visual and auditory effects associated with the "Greed Curse" in Noita. It primarily utilizes Lua scripts and particle emitters to create a distinct atmospheric effect.

## Key Components

### VariableStorageComponent

These components store internal state variables for the curse.

| Name         | Description                                     |
|--------------|-------------------------------------------------|
| `status`     | Likely indicates the active state of the curse. |
| `latest_depth` | Records the depth at which the curse was last active. |
| `timer`      | A general-purpose timer for curse-related logic. |

### LuaComponent

These components execute Lua scripts to manage the curse's behavior.

| Attribute             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| `execute_every_n_frame` | How often the script is executed (e.g., 60 frames for `check_biome.lua`). |
| `script_source_file`  | The path to the Lua script file.                                         |

*   `data/scripts/magic/greed_curse/check_biome.lua`: Likely handles logic related to biome checks for the curse.
*   `data/scripts/status_effects/effect_curse_radioactive.lua`: Suggests this curse might have radioactive properties or interact with them.

### ParticleEmitterComponent

These components generate various particle effects to visually represent the curse.

| Attribute                 | Description