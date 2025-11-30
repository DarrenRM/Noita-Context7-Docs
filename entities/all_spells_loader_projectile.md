---
title: All Spells Loader Projectile
category: entities
---

# All Spells Loader Projectile

This entity acts as a loader for various spell-related scripts, primarily for managing spell stages and effects within Noita. It utilizes Lua components to execute specific scripts at defined intervals or upon entity addition.

## Key Components

### Entity
- **name**: `$projectile_default` - Indicates this entity is a default projectile type.
- **tags**: `all_spells_loader` - A tag identifying its purpose.

### InheritTransformComponent
- This component is present, suggesting it inherits transform properties from a parent or base entity.

### LifetimeComponent
- **lifetime**: `7020` - Defines the duration this entity will exist in frames.

### VariableStorageComponent
- **name**: `stage`
- **value_int**: `0` - Stores an integer value, likely representing the current stage of spell loading or processing.

### LuaComponent (Stage Loader)
- **script_source_file**: `data/scripts/projectiles/all_spells_stage.lua` - The script responsible for managing spell stages.
- **execute_every_n_frame**: `300` - Executes the `all_spells_stage.lua` script every 300 frames.

### LuaComponent (Effect Executor)
- **script_source_file**: `data/scripts/projectiles/all_spells_effect.lua` - The script responsible for handling spell effects.
- **execute_every_n_frame**: `30` - Executes the `all_spells_effect.lua` script every 30 frames.

### LuaComponent (Initial Stage Setup)
- **script_source_file**: `data/scripts/projectiles/all_spells_stage.lua` - Re-uses the stage script.
- **execute_on_added**: `1` - Ensures this script runs immediately when the entity is added.
- **remove_after_executed**: `1` - The script will be removed after its first execution.

---