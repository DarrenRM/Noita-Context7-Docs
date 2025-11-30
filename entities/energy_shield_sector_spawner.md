---
title: Energy Shield Sector Spawner
category: entities
---

# Energy Shield Sector Spawner

This entity spawns a temporary energy shield around a nearby enemy.

## Key Components

### LifetimeComponent
*   **lifetime**: Duration the spawner entity exists (in frames).

### LuaComponent
*   **script_source_file**: Path to the Lua script that handles the spawning logic.
*   **execute_every_n_frame**: How often the script is executed.

### Entity (Spawned Shield)
This nested entity defines the properties of the spawned energy shield. It inherits from `animal_energy_shield_sector.xml`.

#### EnergyShieldComponent
*   **radius**: The radius of the energy shield.
*   **max_energy**: The maximum energy capacity of the shield.
*   **recharge_speed**: How quickly the shield recharges.

#### ParticleEmitterComponent (Multiple)
These components are responsible for visual effects associated with the shield. Their `_enabled` attribute is set to `0` in the spawner, implying they are enabled within the base `animal_energy_shield_sector.xml` or controlled by the Lua script.

#### LightComponent
*   Responsible for lighting effects. `_enabled="0"` suggests it's controlled elsewhere.

#### AudioComponent
*   Responsible for sound effects. `_enabled="0"` suggests it's controlled elsewhere.