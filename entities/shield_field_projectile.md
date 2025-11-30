---
title: Shield Field Projectile
category: entities
---

# Shield Field Projectile

This document describes the `shield_field.xml` entity, which defines a projectile that creates an energy shield.

## Key Components

### GameAreaEffectComponent
This component defines the area of effect for the shield.

*   **radius**: `28` - The radius of the shield.

### ParticleEmitterComponent (x3)
These components control the visual effects of the shield, primarily using `plasma_fading` material.

#### Emitter 1 (General Shield Effect)
*   **_tags**: `character,enabled_in_hand,item_identified__LEGACY`
*   **emitted_material_name**: `plasma_fading`
*   **lifetime_min/max**: `0.1` / `0.5`
*   **count_min/max**: `2` / `4`
*   **area_circle_radius.max**: `28`
*   **airflow_force**: `0.5`

#### Emitter 2 (Shield Ring)
*   **_tags**: `character,enabled_in_hand,item_identified__LEGACY,shield_ring`
*   **emitted_material_name**: `plasma_fading`
*   **lifetime_min/max**: `0.02` / `0.05`
*   **count_min/max**: `90` / `100`
*   **area_circle_radius.min/max**: `28` / `28`
*   **airflow_force**: `0.3`

#### Emitter 3 (Shield Hit Effect)
*   **_tags**: `character,enabled_in_hand,item_identified__LEGACY,shield_hit`
*   **emitted_material_name**: `plasma_fading`
*   **lifetime_min/max**: `0.3` / `1`
*   **count_min/max**: `300` / `360`
*   **area_circle_radius.min/max**: `28` / `28`
*   **airflow_force**: `2.8`
*   **is_emitting**: `0` (This emitter is likely triggered by specific events, not continuously active)

### Base Component (`data/entities/projectiles/deck/base_field.xml`)
This indicates inheritance from a base projectile definition.

#### SpriteComponent
*   **image_file**: `data/projectiles_gfx/blast_shield.xml` - Defines the visual appearance of the shield.

#### SpriteParticleEmitterComponent
*   **_enabled**: `0` (Likely disabled by default, activated by specific conditions)
*   **sprite_file**: `data/particles/teleparticle.xml`
*   **lifetime**: `0.4`
*   **scale.x/y**: `1` / `0.2`
*   **randomize_velocity.min/max_y**: `-40` / `40`

#### ProjectileComponent
*   **lifetime**: `7220` - The duration the projectile (and its shield) exists.
*   **config_explosion**: Defines the visual effect upon the projectile's destruction.

### EnergyShieldComponent
This is the core component for the shield functionality.

*   **recharge_speed**: `0.0` - The shield does not passively recharge.
*   **max_energy**: `20.0` - The maximum energy capacity of the shield.
*   **radius**: `28.0` - The radius of the shield.
*   **energy_required_to_shield**: `0.1` - The amount of energy consumed per unit of shield.
*   **energy**: `20` - The initial energy of the shield.

### AudioComponent
*   **file**: `data/audio/Desktop/projectiles.bank`
*   **event_root**: `player_projectiles/shield` - Specifies the sound events associated with this projectile.