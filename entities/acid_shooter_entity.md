---
title: Acid Shooter Entity
category: entities
---

# Acid Shooter Entity

This document describes the `acidshooter.xml` entity, a creature found in Noita. It's a relatively simple enemy with basic health and a unique attack.

## Key Components

### DamageModelComponent
This component defines the health of the Acid Shooter.

| Attribute | Value | Description |
|---|---|---|
| `hp` | 4 | Current health points. |
| `max_hp` | 4 | Maximum health points. |

### Base Entity
The Acid Shooter inherits its core functionality from a base entity, likely defining its movement and AI.

### Attached Entities (Tentacles)
The Acid Shooter is visually augmented with several "slime tentacle" entities. These are purely cosmetic and do not appear to have independent functionality or damage.

| Entity File | Relative Position (x, y) | Description |
|---|---|---|
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_02.xml` | (-3, -1) | A slime tentacle attached to the entity. |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_01.xml` | (-4, -1) | Another slime tentacle. |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_01.xml` | (0, -1) | A third slime tentacle. |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_01.xml` | (4, -1) | A thinner slime tentacle. |

## AI and Behavior (Inferred)

While not explicitly defined in this snippet, the name "acidshooter" strongly suggests that this entity possesses an attack that involves spitting or spraying acid. The `DamageModelComponent` indicates it's a fragile enemy, easily dispatched. The attached tentacles are likely for visual flair and to give it a distinct appearance.

## Modding Potential

*   **Health/Damage:** Adjust `hp` and `max_hp` to make it more or less challenging.
*   **Visuals:** Replace or modify the attached tentacle entities for a different look.
*   **Attack Behavior:** This XML snippet doesn't detail the attack. To modify its acid-spitting ability, you would need to examine other related XML files or Lua scripts that define its AI and projectile behavior.