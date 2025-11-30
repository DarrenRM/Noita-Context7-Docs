---
title: Boss Fish Damage Handling
category: entities
---

---

# Boss Fish Damage Handling

This document describes the `damage_received` function for the Boss Fish entity in Noita, detailing how it reacts to taking damage.

## Core Functionality

The `damage_received` function is triggered when the Boss Fish entity takes damage. It handles the visual and projectile-based responses to being hit.

### Key Actions:

*   **Projectile Ejection:** Upon taking damage, the Boss Fish shoots a "big orb" projectile.
*   **Directional Aiming:** The projectile's trajectory is influenced by the entity that caused the damage. If the damage source is known, the projectile is aimed towards the Boss Fish. Otherwise, it's fired in a random direction.
*   **Health Bar Visibility:** The Boss Fish's health bar is made visible when it receives damage.

### Important Attributes/Elements:

*   `damage_received( damage, desc, entity_who_caused, is_fatal )`: The primary function that executes when the entity takes damage.
    *   `damage`: The amount of damage taken.
    *   `desc`: A description of the damage.
    *   `entity_who_caused`: The entity that inflicted the damage (can be `NULL_ENTITY`).
    *   `is_fatal`: A boolean indicating if the damage was fatal.
*   `EntityGetTransform( entity_id )`: Retrieves the position and rotation of an entity.
*   `SetRandomSeed( frame_num, entity_id )`: Seeds the random number generator for consistent randomness.
*   `Random( min, max )`: Generates a random number within a specified range.
*   `get_direction( from_x, from_y, to_x, to_y )`: Calculates the angle between two points.
*   `shoot_projectile( shooter_entity_id, projectile_xml_path, x, y, vx, vy )`: Shoots a projectile from a specified entity.
    *   `projectile_xml_path`: The XML path to the projectile entity (e.g., `"data/entities/animals/boss_fish/orb_big.xml"`).
    *   `x`, `y`: The spawn position of the projectile.
    *   `vx`, `vy`: The velocity components of the projectile.
*   `EntityGetComponent( entity_id, component_type, component_name )`: Retrieves a specific component from an entity.
    *   `component_type`: The type of component (e.g., `"SpriteComponent"`).
    *   `component_name`: The name of the component (e.g., `"health_bar"`).
*   `ComponentSetValue2( component, property_name, value )`: Sets a value for a property of a component.
    *   `property_name`: The name of the property to set (e.g., `"visible"`).
    *   `value`: The new value for the property (e.g., `true`).