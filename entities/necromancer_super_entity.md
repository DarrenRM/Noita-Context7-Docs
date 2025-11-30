---
title: Necromancer Super Entity
category: entities
---

---

# Necromancer Super Entity

This document details the `necromancer_super.xml` entity, representing a powerful variant of the Necromancer enemy in Noita. It focuses on its combat capabilities, defensive mechanisms, and AI behaviors.

## Core Attributes

### Base Entity

Inherits from `data/entities/base_enemy_flying.xml`, providing fundamental flying enemy characteristics.

### Health and Damage

*   **HP:** 36
*   **Critical Damage Resistance:** 0.5
*   **Minimum Knockback Force:** 10000
*   **Damage Multipliers:**
    *   Projectile: 0.4
    *   Explosion: 0.2
    *   Fire: 0.1
    *   Electricity, Ice, Holy: 0

### Movement and AI

*   **Detection Range:** 900x900 pixels
*   **Aggressiveness:** 100 (max)
*   **Flight:** Enabled, with high vertical and horizontal speeds.
*   **Pathfinding:** Can fly, cannot walk, ignores line of sight for movement.
*   **AI Behavior:** Primarily aggressive, with specific AI scripts for chasing and initiating combat.

### Visuals and Audio

*   **Sprite:** Uses `necromancer_super.xml` for base graphics and `necromancer_super_emissive.xml` for emissive effects.
*   **Light Component:** Emits a bright pinkish-white light (radius 70).
*   **Audio:** Utilizes `animals.bank` for sound events related to the Necromancer Shop.

## Combat Mechanics

### Ranged Attacks

The Necromancer Super has two distinct ranged attack patterns:

1.  **Primary Ranged Attack:**
    *   **Trigger:** `AIAttackComponent`
    *   **Distance:** 11-200 pixels
    *   **Frequency:** 50 frames between attacks, 7 frames globally.
    *   **Projectile:** `data/entities/projectiles/orb_pink_big_super.xml` (2 projectiles)
    *   **Offset:** x=12, y=-22
    *   **Animation:** `attack_ranged`

2.  **Fast Ranged Attack:**
    *   **Trigger:** `AIAttackComponent` (70% probability)
    *   **Distance:** 0-70 pixels
    *   **Frequency:** 7 frames between attacks, 7 frames globally.
    *   **Projectile:** `data/entities/projectiles/orb_pink_super.xml` (1 projectile)
    *   **Offset:** x=21, y=-8
    *   **Animation:** `attack_ranged_fast`

### Special Abilities

*   **Cell Eater Component:** Enabled when the player is seen, with an 8% probability to eat cells within a 40-pixel radius.

## Defensive Systems

### Protections

The Necromancer Super is immune to freezing and electricity effects.

### Energy Shields

It is protected by two concentric energy shields:

*   **Outer Shield:**
    *   Radius: 52.0 pixels
    *   Recharge Speed: 0.9
    *   Visuals: Emits pink plasma particles.
*   **Inner Shield:**
    *   Radius: 40.0 pixels
    *   Recharge Speed: 0.9
    *   Visuals: Emits pink plasma particles.

## Scripted Behaviors

*   **Initialization:** `data/scripts/animals/necromancer_shop_init.lua` (executed on addition)
*   **Chasing:**
    *   `data/scripts/animals/necromancer_super_chase.lua` (executed every 1 frame when player is seen)
    *   `data/scripts/animals/necromancer_super_chase_begin.lua` (executed every 47 frames)

## Other Components

*   **ItemChestComponent:** Level 1 chest component.
*   **GenomeDataComponent:** Herd ID "mage", predator.
*   **CharacterDataComponent:** Defines collision box and mass.
*   **CharacterPlatformingComponent:** Manages flight and movement parameters.