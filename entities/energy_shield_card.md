---
title: Energy Shield Card
category: entities
---

# Energy Shield Card

This document details the configuration for the "Energy Shield" card entity in Noita, intended for AI-assisted modding.

## Core Components

The Energy Shield card is defined by several key components that dictate its behavior and appearance.

### ItemComponent
This component marks the entity as an item that can be picked up and used in the game world.
- `_tags`: `enabled_in_world`
- `preferred_inventory`: `FULL` (Indicates it's a full item, not a component)

### HitboxComponent
Defines the physical boundaries of the card when it's an entity in the world.
- `aabb_min_x`, `aabb_max_x`: `-4`, `4`
- `aabb_min_y`, `aabb_max_y`: `-3`, `3`

### SimplePhysicsComponent
Enables basic physics interactions for the entity.
- `_tags`: `enabled_in_world`

### VelocityComponent
Allows the entity to have velocity, enabling movement.
- `_tags`: `enabled_in_world`

### ItemActionComponent
Links this entity to a specific game action.
- `action_id`: `ENERGY_SHIELD`

### InheritTransformComponent
Manages how the card's transform is inherited when held by the player.
- `use_root_parent`: `1` (Inherits transform from the player's hand)
- `position.y`: `-4` (Slight offset when held)

## Visuals (SpriteComponent)

The card has distinct sprites for its identified and unidentified states, as well as a background element.

| Sprite ID | Image File                                | Offset X | Offset Y | Z-Index | Tags                                      |
| :-------- | :---------------------------------------- | :------- | :------- | :------ | :---------------------------------------- |
| 0         | `data/ui_gfx/gun_actions/energy_shield.png` | `8`      | `17`     | `-1.51` | `enabled_in_world,item_identified`        |
| 1         | `data/ui_gfx/gun_actions/unidentified.png`  | `8`      | `17`     | `-1.51` | `enabled_in_world,item_unidentified`      |
| 2         | `data/ui_gfx/inventory/item_bg_projectile.png` | `10`     | `19`     | `-1.5`  | `enabled_in_world,item_bg`                |

### SpriteOffsetAnimatorComponent
These components add a subtle vertical bobbing animation to the sprites.
- `y_amount`: `1`
- `y_speed`: `2.5`
- `sprite_id`: `0`, `1`, `2`, `3` (Applies to multiple sprite layers)

## Functionality (EnergyShieldComponent)

This is the core component that enables the energy shield effect.
- `_tags`: `enabled_in_hand,item_identified__LEGACY`
- `recharge_speed`: `0.25` (How quickly the shield regenerates)
- `radius`: `16.0` (The size of the shield)

## Particle Effects

The card utilizes several `ParticleEmitterComponent` instances to create visual feedback for the shield.

### Emitting Particles (Shield Activation/Idle)
- `_tags`: `character,enabled_in_hand,item_identified__LEGACY`
- `emitted_material_name`: `plasma_fading`
- `lifetime_min`/`max`: `0.1` - `0.5`
- `count_min`/`max`: `2` - `4`
- `area_circle_radius.max`: `16`
- `is_emitting`: `1`

### Ring Particles (Shield Ring)
- `_tags`: `character,enabled_in_hand,item_identified__LEGACY,shield_ring`
- `emitted_material_name`: `plasma_fading`
- `lifetime_min`/`max`: `0.02` - `0.05`
- `count_min`/`max`: `90` - `100`
- `area_circle_radius.min`/`max`: `16`
- `is_emitting`: `1`

### Hit Particles (Shield Impact)
- `_tags`: `character,enabled_in_hand,item_identified__LEGACY,shield_hit`
- `emitted_material_name`: `plasma_fading`
- `lifetime_min`/`max`: `0.3` - `1`
- `count_min`/`max`: `300` - `360`
- `area_circle_radius.min`/`max`: `16`
- `is_emitting`: `0` (This emitter is triggered by events, not continuously)

## Lighting (LightComponent)

Provides a visual glow when the shield is active.
- `_tags`: `enabled_in_hand,item_identified`
- `radius`: `80`
- `r`, `g`, `b`: `150`, `190`, `230` (A bluish-white light)

## Audio (AudioComponent)

Handles sound effects associated with the shield.
- `_tags`: `enabled_in_hand,item_identified`
- `file`: `data/audio/Desktop/projectiles.bank`
- `event_root`: `player_projectiles/shield`