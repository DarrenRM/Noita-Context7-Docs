---
title: Utility Rain Entity
category: entities
---

---

# Utility Rain Entity

This entity defines a utility rain effect, likely used for spawning various utility boxes or effects at intervals.

## Key Components

### InheritTransformComponent
This component indicates that the entity inherits transformation properties from its parent or a default transform.

### LifetimeComponent
*   **lifetime**: `300` - The duration in frames this entity will exist.
*   **serialize_duration**: `1` - How long the entity's lifetime should be serialized.

### LuaComponent
*   **_enabled**: `1` - The Lua script is enabled.
*   **execute_every_n_frame**: `20` - The script will execute its logic every 20 frames.
*   **script_source_file**: `data/scripts/buildings/spawn_utility_boxes.lua` - This specifies the Lua script responsible for the entity's behavior. This script likely handles the spawning of utility boxes or other related effects.