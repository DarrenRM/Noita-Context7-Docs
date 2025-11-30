---
title: Shieldshot Shield Entity
category: entities
---

# Shieldshot Shield Entity

This document details the `shieldshot_shield.xml` entity, which defines the properties and behavior of the Shieldshot shield in Noita. This entity is designed to be used as an item that grants the player a protective energy shield.

## Key Components and Attributes

The `shieldshot_shield.xml` entity is composed of several components, each contributing to its functionality. The most important ones are highlighted below:

### Entity Tags

*   `energy_shield`: Identifies this entity as an energy shield.
*   `shieldshot`: A specific tag for this type of shield, potentially used for unique interactions or effects.

### HitboxComponent

Defines the physical boundaries of the shield when it's active.

*   `aabb_min_x`, `aabb_max_x`: Defines the horizontal extent of the hitbox.
*   `aabb_min_y`, `aabb_max_y`: Defines the vertical extent of the hitbox.

### InheritTransformComponent

Controls how the shield's transform (position, rotation, scale) is inherited from its parent, typically the player's hand when held.

*   `use_root_parent="1"`: Ensures the shield's position is relative to the player's root.
*   `position.x`, `position.y`: Offsets the shield's position relative to the parent.

### EnergyShieldComponent

This is the core component responsible for the shield's protective capabilities.

*   `recharge_speed`: How quickly the shield's energy replenishes.
*   `radius`: The effective radius of the shield around the player.
*   `energy`: The current energy level of the shield.
*   `max_energy`: The maximum energy the shield can hold.

### ParticleEmitterComponent (Multiple Instances)

These components are responsible for generating visual effects (particles) associated with the shield. There are distinct emitters for different states:

#### General Shield Particles (`enabled_in_hand`)

*   `emitted_material_name="plasma_fading"`: The type of particle material used.
*   `lifetime_min`, `lifetime_max`: Duration each particle exists.
*   `count_min`, `count_max`: Number of particles emitted per burst.
*   `area_circle_radius.max`: The maximum radius within which particles are emitted.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters controlling particle movement and behavior.

#### Shield Ring Particles (`shield_ring`)

*   These particles create a visual ring effect around the shield.
*   `area_circle_radius.min`, `area_circle_radius.max`: Set to the shield's radius to form a distinct ring.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to `0` for continuous emission.

#### Shield Hit Particles (`shield_hit`)

*   These particles are emitted when the shield takes damage.
*   `is_emitting="0"`: This emitter is initially inactive and likely triggered by game events.
*   `count_min`, `count_max`: A high count for a significant visual impact on hit.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters for a more dynamic, impactful burst.

### LightComponent

Adds a light source to the shield, illuminating the surrounding area.

*   `radius`: The range of the light.
*   `fade_out_time`: How long the light takes to fade.
*   `r`, `g`, `b`: The color of the light.

### AudioComponent

Manages the sound effects associated with the shield.

*   `file`: Path to the audio bank.
*   `event_root`: The base event name for shield sounds.
*   `set_latest_event_position="1"`: Ensures sounds originate from the shield's position.

### LifetimeComponent

Determines how long the shield entity persists.

*   `lifetime`: The duration in frames the shield will exist before despawning.