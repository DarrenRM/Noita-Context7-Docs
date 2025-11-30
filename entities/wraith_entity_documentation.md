---
title: Wraith Entity Documentation
category: entities
---

# Wraith Entity Documentation

This document details the `wraith.xml` entity, providing key attributes for AI-assisted modding.

## Core Attributes

The Wraith is a flying enemy with unique visual and behavioral characteristics.

### Base Entity Configuration

The Wraith inherits from `base_enemy_flying.xml`, indicating its aerial nature and standard enemy behaviors.

### Health and Damage

*   **HP:** `14.75` - Relatively low health pool.
*   **Damage Multipliers:**
    *   `projectile`: `0.1` - Highly resistant to projectiles.
    *   `explosion`: `0.1` - Highly resistant to explosions.
    *   `electricity`: `0.5` - Takes half damage from electricity.
    *   `fire`: `0.5` - Takes half damage from fire.
    *   `slice`: `0.1` - Highly resistant to slicing damage.
    *   `ice`: `0.1` - Highly resistant to ice damage.
    *   `holy`: `1.2` - Takes slightly more damage from holy sources.
*   **Ragdoll FX:** `DISINTEGRATED` - Dissolves upon death.
*   **Ragdoll Material:** `plasma_fading_pink` - Dissolves into pink plasma.
*   **Blood Material:** `plasma_fading_pink` - Leaves pink plasma when damaged.
*   **Minimum Knockback Force:** `100000` - Extremely high knockback resistance.

### AI and Movement

*   **Flying:** `can_fly="1"` - Inherently a flying entity.
*   **Walking:** `can_walk="0"` - Cannot walk.
*   **Food Needs:** `needs_food="0"` - Does not require food.
*   **Attack Types:**
    *   `attack_ranged_enabled="0"` - Cannot perform ranged attacks.
    *   `attack_dash_enabled="0"` - Cannot perform dash attacks.

### Visuals and Sprites

*   **Main Sprite:** `data/enemies_gfx/wraith.xml` - Defines the primary visual appearance.
*   **Arm Sprite:** `data/enemies_gfx/wraith_arm.xml` - Used for the Wraith's arm, with a "walk" animation.
*   **Area Indicator:** `data/particles/area_indicator_096_purple_dark.png` - A disabled sprite, likely for visual effects or debugging.

### Collision and Hitbox

*   **Hitbox:** Defined by `aabb_min_x="-4.0"`, `aabb_max_x="4.0"`, `aabb_min_y="-4"`, `aabb_max_y="4"`.
*   **Collision AABB:** `collision_aabb_min_x="-2.0"`, `collision_aabb_max_x="2.0"`, `collision_aabb_min_y="-10"`, `collision_aabb_max_y="0"`.
*   **Mass:** `0.9` - Relatively light.

### Audio

*   **Sound Bank:** `data/audio/Desktop/animals.bank`
*   **Event Root:** `animals/wraith`
*   **Movement Loop:** `animals/wraith/movement_loop`
*   **Vortex Loop:** `animals/wraith/vortex_loop`

### Special Components

*   **Light Component:**
    *   `radius="30"`
    *   `r="99"`, `g="205"`, `b="139"` - Emits a greenish-blue light.
    *   `offset_y="-9"`
*   **Genome Data:**
    *   `herd_id="mage"`
    *   `food_chain_rank="15"`
    *   `is_predator="1"`
*   **Verlet Chains:** Includes `wraith_cape.xml` for its cape.
*   **Lua Component:**
    *   `script_source_file="data/scripts/projectiles/projectile_gravity_strong.lua"` - Likely influences projectile behavior or environmental effects.
    *   `execute_every_n_frame="1"` - Executes the script every frame.
*   **Particle Emitters:** Two emitters are configured to emit `spark_purple_bright` particles with varying radii and emission patterns, suggesting a visual effect related to its presence or abilities.

---