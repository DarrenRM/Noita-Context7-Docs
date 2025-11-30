---
title: Laser Shooter Entity
category: entities
---

# Laser Shooter Entity

This document describes the `lasershooter.xml` entity, a creature in Noita that fires lasers.

## Core Components

### Base Entity

The `lasershooter.xml` inherits its base properties from `data/entities/animals/lasershooter.xml`.

### Damage Component

*   **`hp`**: 16 - The current health of the entity.
*   **`max_hp`**: 16 - The maximum health the entity can have.
*   **`minimum_knockback_force`**: 100000 - A very high value, indicating significant resistance to knockback.

## Visual Components (Tentacles)

The Laser Shooter entity is visually augmented with several tentacle entities, likely for aesthetic or animation purposes. These tentacles are inherited from various `tealslime_tentacle` files and positioned relative to the main entity.

### Tentacle 1

*   **Base File**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_02.xml`
*   **Relative Position**: `x: -3`, `y: -1`

### Tentacle 2

*   **Base File**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_01.xml`
*   **Relative Position**: `x: -4`, `y: -1`

### Tentacle 3

*   **Base File**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_01.xml`
*   **Relative Position**: `x: 0`, `y: -1`

### Tentacle 4

*   **Base File**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_thin_01.xml`
*   **Relative Position**: `x: 4`, `y: -1`