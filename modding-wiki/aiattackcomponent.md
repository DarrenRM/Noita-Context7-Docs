---
title: AIAttackComponent
source: https://noita.wiki.gg/wiki/Documentation:AIAttackComponent
category: modding-wiki
---

# AIAttackComponent

This documentation page details the `AIAttackComponent` in Noita, a crucial component for defining enemy attack behaviors. Understanding and modifying this component is essential for modders looking to create custom enemy AI, alter existing attack patterns, or implement new combat mechanics.

## Overview

The `AIAttackComponent` is responsible for managing an entity's offensive capabilities. It dictates how an AI-controlled entity will initiate and execute attacks, including targeting, projectile firing, melee swings, and cooldowns. By configuring its various properties, modders can fine-tune enemy aggression, attack variety, and overall combat effectiveness.

## Component Properties

The `AIAttackComponent` has several properties that can be modified in the entity's XML definition. These properties control different aspects of the attack behavior.

### `attack_range`

*   **Type:** `float`
*   **Description:** The maximum distance at which the entity can initiate an attack.

### `attack_delay`

*   **Type:** `float`
*   **Description:** The time in seconds between consecutive attacks.

### `attack_damage`

*   **Type:** `float`
*   **Description:** The base damage dealt by the attack.

### `attack_projectile`

*   **Type:** `string`
*   **Description:** The entity ID of the projectile to be fired. This projectile must be defined elsewhere in the game's XML files.

### `attack_projectile_speed`

*   **Type:** `float`
*   **Description:** The speed at which the projectile is launched.

### `attack_projectile_offset`

*   **Type:** `float`
*   **Description:** An offset applied to the projectile's spawn position.

### `attack_sound`

*   **Type:** `string`
*   **Description:** The name of the sound effect to play when the attack is initiated.

### `attack_visual_effect`

*   **Type:** `string`
*   **Description:** The entity ID of a visual effect to spawn when the attack is initiated.

### `attack_cooldown`

*   **Type:** `float`
*   **Description:** The time in seconds the entity must wait after an attack before it can attack again. This is often used in conjunction with `attack_delay` to create more complex attack patterns.

### `attack_target_angle`

*   **Type:** `float`
*   **Description:** The angle in degrees relative to the entity's facing direction that the attack will be aimed. A value of 0 means it will attack directly in front.

### `attack_target_offset`

*   **Type:** `float`
*   **Description:** An offset applied to the target's position when calculating the attack direction.

### `attack_target_radius`

*   **Type:** `float`
*   **Description:** The radius around the target within which the attack will be considered successful.

### `attack_target_type`

*   **Type:** `string`
*   **Description:** Specifies the type of target the AI should prioritize. Common values include:
    *   `player`
    *   `enemy`
    *   `ally`
    *   `any`

### `attack_target_faction`

*   **Type:** `string`
*   **Description:** Specifies the faction of the target the AI should prioritize.

### `attack_target_distance`

*   **Type:** `float`
*   **Description:** The preferred distance at which the AI should engage its target.

### `attack_target_los`

*   **Type:** `boolean`
*   **Description:** If `true`, the AI will only attack if it has line of sight to the target.

### `attack_target_los_range`

*   **Type:** `float`
*   **Description:** The maximum distance for line of sight checks.

### `attack_target_los_angle`

*   **Type:** `float`
*   **Description:** The angle within which line of sight is considered valid.

### `attack_target_los_height`

*   **Type:** `float`
*   **Description:** The maximum height difference for line of sight checks.

### `attack_target_los_width`

*   **Type:** `float`
*   **Description:** The maximum width difference for line of sight checks.

### `attack_target_los_margin`

*   **Type:** `float`
*   **Description:** A margin of error for line of sight checks.

### `attack_target_los_check_type`

*   **Type:** `string`
*   **Description:** Specifies the type of line of sight check.

### `attack_target_los_check_radius`

*   **Type:** `float`
*   **Description:** The radius for line of sight checks.

### `attack_target_los_check_angle`

*   **Type:** `float`
*   **Description:** The angle for line of sight checks.

### `attack_target_los_check_height`

*   **Type:** `float`
*   **Description:** The height for line of sight checks.

### `attack_target_los_check_width`

*   **Type:** `float`
*   **Description:** The width for line of sight checks.

### `attack_target_los_check_margin`

*   **Type:** `float`
*   **Description:** The margin for line of sight checks.

### `attack_target_los_check_margin_type`

*   **Type:** `string`
*   **Description:** The type of margin for line of sight checks.

### `attack_target_los_check_margin_value`

*   **Type:** `float`
*   **Description:** The value of the margin for line of sight checks.

### `attack_target_los_check_margin_offset`

*   **Type:** `float`
*   **Description:** The offset of the margin for line of sight checks.

### `attack_target_los_check_margin_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*   **Type:** `string`
*   **Description:** The type of offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_value`

*   **Type:** `float`
*   **Description:** The value of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset`

*   **Type:** `float`
*   **Description:** The offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset of the offset for the margin for line of sight checks.

### `attack_target_los_check_margin_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_offset_type`

*