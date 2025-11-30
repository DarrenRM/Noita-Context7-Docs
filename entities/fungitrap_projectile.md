---
title: Fungitrap Projectile
category: entities
---

# Fungitrap Projectile

This document describes the `fungitrap_01_projectile.xml` entity, which defines the behavior of a projectile fired by a fungitrap.

## Base Entity

The projectile inherits its base properties from `data/entities/base_projectile.xml`.

### Velocity Component

*   **mass**: `1.4` - Defines the mass of the projectile.

## Projectile Component

This component governs the projectile's specific behaviors and interactions.

### Key Attributes

*   **speed\_min**: `200` - The minimum speed of the projectile.
*   **speed\_max**: `200` - The maximum speed of the projectile.
*   **die\_on\_low\_velocity**: `0` - The projectile does not die when its velocity becomes low.
*   **on\_death\_explode**: `0` - The projectile does not explode upon death.
*   **on\_death\_gfx\_leave\_sprite**: `0` - No sprite is left behind when the projectile dies.
*   **on\_lifetime\_out\_explode**: `0` - The projectile does not explode when its lifetime expires.
*   **on\_collision\_die**: `1` - The projectile dies upon colliding with something.
*   **penetrate\_entities**: `1` - The projectile can pass through entities.
*   **collide\_with\_entities**: `0` - The projectile does not collide with entities (this seems to contradict `penetrate_entities`, suggesting it might only penetrate certain types or that the collision check is for spawning purposes).
*   **damage**: `0` - The projectile deals no direct damage.
*   **lifetime**: `40` - The projectile exists for 40 frames before expiring.
*   **on\_collision\_spawn\_entity**: `1` - An entity is spawned upon collision.
*   **spawn\_entity**: `data/entities/projectiles/deck/spore_pod_growing.xml` - The entity to spawn upon collision is `spore_pod_growing.xml`.

### Configuration Explosion

This section defines explosion properties, which are largely disabled for this projectile.

*   **never\_cache**: `1` - This explosion configuration will not be cached.
*   **damage**: `0` - No damage is dealt by the explosion.
*   **camera\_shake**: `0` - No camera shake is triggered.
*   **explosion\_radius**: `0` - The explosion has no radius.
*   **physics\_explosion\_power.min**: `0` - Minimum physics explosion power is zero.
*   **physics\_explosion\_power.max**: `0` - Maximum physics explosion power is zero.
*   **hole\_enabled**: `0` - No holes are created.
*   **particle\_effect**: `0` - No particle effects are generated.
*   **damage\_mortals**: `0` - Mortals are not damaged by the explosion.