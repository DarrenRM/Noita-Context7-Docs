---
title: Hit Effect - Heal/Hurt
category: entities
---

# Hit Effect - Heal/Hurt

This entity defines a generic hit effect that can be used to trigger other entities, specifically for healing or hurting effects.

## Key Components

### HitEffectComponent

This component is responsible for defining what happens when this entity is "hit" or triggered.

*   **`effect_hit`**: Specifies the type of effect to apply.
    *   `LOAD_CHILD_ENTITY`: Indicates that another entity should be loaded and spawned.
*   **`value_string`**: The path to the entity that should be loaded when `effect_hit` is `LOAD_CHILD_ENTITY`.
    *   `data/entities/misc/effect_healhurt.xml`: This is the specific entity that will be loaded, which contains the actual logic for healing or hurting.

## Usage

This entity acts as a placeholder or trigger. When this entity is activated (e.g., by a projectile hitting it), it will load and spawn the `effect_healhurt.xml` entity. This allows for a modular approach to defining various healing and hurting effects by simply changing the `value_string` to point to different effect entities.