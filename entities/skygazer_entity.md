---
title: Skygazer Entity
category: entities
---

---

# Skygazer Entity

This document details the Skygazer entity, a flying creature found in Noita, intended for AI-assisted modding.

## Core Attributes

The Skygazer is a flying enemy with basic ranged attack capabilities.

### Base Entity Configuration

The Skygazer inherits its core functionality from `base_enemy_flying.xml`.

### Health and Damage

*   **HP:** 10
*   **Ragdoll Material:** `meat_slime`
*   **Blood Material:** `magic_liquid_random_polymorph`
*   **Damage Multipliers:**
    *   Melee: 1.2
    *   Projectile: 0.4
    *   Explosion: 0.8
    *   Electricity: 0.8
    *   Ice: 1.2
    *   Fire: 0
    *   Holy: 0.5
*   **Materials that Damage:** `acid`, `poison`, `blood_cold`, `blood_cold_vapour` with corresponding damage values.

### AI and Movement

*   **Flying:** `can_fly="1"` is enabled for both AI and pathfinding.
*   **Ranged Attack:**
    *   Enabled: `attack_ranged_enabled="1"`
    *   Projectile: `data/entities/projectiles/polyshot.xml`
    *   Action Frame: `attack_action_frame="1"`
    *   Frames Between Attacks: `attack_ranged_frames_between="100"`
*   **Dash Attack:** `attack_dash_enabled="0"` (disabled)

### Visuals and Hitbox

*   **Sprite:** `data/enemies_gfx/skygazer.xml`
*   **Hitbox:**
    *   AABB Min X: -10.5, Max X: 10.5
    *   AABB Min Y: -18.0, Max Y: 6
*   **Collision AABB:**
    *   Min X: -10.0, Max X: 10.0
    *   Min Y: -19, Max Y: 3
*   **Mass:** 2.3

### Genome and Material

*   **Herd ID:** `slimes`
*   **Material Inventory:**
    *   Drops as item: `drop_as_item="0"`
    *   Leaks on damage: `leak_on_damage_percent="0.999"`
    *   Contains `magic_liquid_random_polymorph` (200 units).

### Audio

*   **Bank:** `data/audio/Desktop/animals.bank`
*   **Event Root:** `animals/gazer`
*   **Movement Loop:** `animals/gazer/movement_loop` (auto-plays)

### Particles

*   **Shine Effect:** A `SpriteParticleEmitterComponent` is used for a visual shine effect with specific parameters for lifetime, color, velocity, and emission.