---
title: Phantom A (Ghost) Entity
category: entities
---

# Phantom A (Ghost) Entity

This document details the configuration of the Phantom A entity, commonly known as a "Ghost" in Noita. It outlines its core attributes, AI behaviors, combat capabilities, and visual/audio properties.

## Core Attributes

The Phantom A is a flying enemy with unique defensive and offensive capabilities.

### Base Entity Configuration

The entity inherits its fundamental properties from `data/entities/base_enemy_flying.xml`.

### ItemChestComponent

*   **level**: 5 - Indicates the loot tier.
*   **enemy\_drop**: 1 - Suggests a high chance of dropping items.

### DamageModelComponent

*   **hp**: 3 - The entity has a low health pool.
*   **ragdoll\_material**: `rock_static_glow` - Defines the material for its ragdoll effect upon death.
*   **blood\_material**: `plasma_fading` - Specifies the material for its blood effect.
*   **air\_needed**: 0 - The entity does not require air to survive.

#### Damage Multipliers

This table shows how different damage types affect the Phantom A.

| Damage Type | Multiplier | Notes                               |
| :---------- | :--------- | :---------------------------------- |
| projectile  | 0.5        | Takes half damage from projectiles. |
| explosion   | 0.4        | Takes less damage from explosions.  |
| electricity | 1          | Takes normal damage from electricity. |
| fire        | 0          | Immune to fire damage.              |
| slice       | 1          | Takes normal damage from slices.    |
| holy        | 1.2        | Takes slightly more damage from holy. |

### SpriteComponent

*   **image\_file**: `data/enemies_gfx/phantom_a.xml` - Specifies the graphical asset for the entity.
*   **additive**: 1 - Enables additive blending for a glowing effect.
*   **emissive**: 1 - The sprite emits light.

### PathFindingComponent

*   **can\_fly**: 1 - The entity is capable of flight.
*   **can\_swim\_on\_surface**: 1 - Can swim on the surface of liquids.

### GenomeDataComponent

*   **herd\_id**: `ghost` - Identifies the creature's herd or type.
*   **food\_chain\_rank**: 15 - Indicates its position in the food chain.
*   **is\_predator**: 1 - The entity is a predator.

### CharacterPlatformingComponent

*   **pixel\_gravity**: 600 - Defines its gravity value.
*   **jump\_velocity\_y**: -12 - The vertical velocity applied when jumping.
*   **run\_velocity**: 14 - The horizontal movement speed.

### HitboxComponent

*   **aabb\_min\_x**: -4.5, **aabb\_max\_x**: 4.5 - Defines the horizontal bounds of its hitbox.
*   **aabb\_min\_y**: -14, **aabb\_max\_y**: 3 - Defines the vertical bounds of its hitbox.

### CharacterDataComponent

*   **collision\_aabb\_min\_x**: -2, **collision\_aabb\_max\_x**: 2 - Defines the horizontal bounds for collision detection.
*   **collision\_aabb\_min\_y**: -14, **collision\_aabb\_max\_y**: 2 - Defines the vertical bounds for collision detection.
*   **mass**: 1.0 - The entity's mass.

### AudioComponent

*   **file**: `data/audio/Desktop/animals.bank` - The audio bank containing its sounds.
*   **event\_root**: `animals/ghost` - The root event name for its audio.

## AI and Behavior

The `AnimalAIComponent` governs the Phantom A's actions and interactions.

### AnimalAIComponent

*   **preferred\_job**: `JobDefault` - Its default AI behavior.
*   **escape\_if\_damaged\_probability**: 35 - A 35% chance to attempt to flee when damaged.
*   **creature\_detection\_range\_x**: 250, **creature\_detection\_range\_y**: 250 - The range at which it detects other creatures.
*   **sense\_creatures**: 1 - Actively senses nearby creatures.
*   **can\_fly**: 1 - Capable of flying.
*   **needs\_food**: 0 - Does not require food.

#### Combat Behaviors

*   **attack\_ranged\_enabled**: 1 - Can perform ranged attacks.
*   **attack\_ranged\_entity\_file**: `data/entities/projectiles/orbspawner.xml` - The projectile entity used for ranged attacks.
*   **attack\_ranged\_frames\_between**: 250 - The cooldown in frames between ranged attacks.
*   **attack\_landing\_ranged\_enabled**: 1 - Can perform ranged attacks while landing.
*   **attack\_ranged\_action\_frame**: 4 - The frame at which the ranged attack animation occurs.
*   **attack\_melee\_enabled**: 1 - Can perform melee attacks.
*   **attack\_melee\_damage\_min**: 0.6, **attack\_melee\_damage\_max**: 0.8 - The damage range for melee attacks.
*   **attack\_melee\_action\_frame**: 3 - The frame at which the melee attack animation occurs.
*   **attack\_dash\_enabled**: 0 - Cannot perform dash attacks.

## Special Properties

### GameEffectComponent

*   **effect**: `PROTECTION_FREEZE` - Grants immunity to freezing.
*   **frames**: -1 - The effect is permanent.

### AudioLoopComponent

*   **event\_name**: `animals/ghost/movement_loop` - The audio event for its movement loop.
*   **auto\_play**: 1 - The movement sound plays automatically.

---