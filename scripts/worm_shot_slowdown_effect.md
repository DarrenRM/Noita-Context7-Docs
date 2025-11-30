---
title: Worm Shot Slowdown Effect
category: scripts
---

# Worm Shot Slowdown Effect

This script modifies the velocity of a projectile, applying slowdown effects based on proximity to "Worm Attractor" and "Worm Detractor" entities.

## Key Functionality

This script primarily targets the `VelocityComponent` of an entity to alter its movement.

### Velocity Modification Logic

1.  **Initial Speed Check:** If the projectile's current velocity magnitude exceeds 450, its speed is reduced by multiplying both `vel_x` and `vel_y` by 0.86. This acts as a general speed cap or initial slowdown.

2.  **Worm Detractor Interaction:**
    *   The script checks for the closest `WormDetractor` entity.
    *   If a detractor is found within a `radius` of 240 units from the projectile:
        *   The projectile's velocity is adjusted to move *away* from the detractor.
        *   The strength of this adjustment is proportional to the distance to the detractor, with a multiplier of 0.05.
        *   The closer the projectile is to the detractor, the stronger the push away.

3.  **Worm Attractor Interaction:**
    *   The script checks for the closest `WormAttractor` entity.
    *   If an attractor is found within a `radius` of 240 units from the projectile:
        *   The projectile's velocity is adjusted to move *towards* the attractor.
        *   The strength of this adjustment is proportional to the distance to the attractor, with a multiplier of 0.05.
        *   The closer the projectile is to the attractor, the stronger the pull towards it.

## Core Components and Variables

*   `entity_id`: The unique identifier of the entity this script is attached to.
*   `radius`: Defines the interaction range (240 units) for both attractors and detractors.
*   `c_id`, `c_x`, `c_y`: Variables storing the ID and coordinates of the closest `WormAttractor`.
*   `f_id`, `f_x`, `f_y`: Variables storing the ID and coordinates of the closest `WormDetractor`.
*   `VelocityComponent`: The component being modified to change the entity's velocity.
*   `mVelocity`: The vector representing the entity's current velocity.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity. When this projectile is spawned, it will:

1.  Immediately check if it's moving too fast and slow down if necessary.
2.  Continuously check its proximity to any `WormDetractor` or `WormAttractor` entities in the game world.
3.  If within range of a detractor, it will be pushed away.
4.  If within range of an attractor, it will be pulled towards it.

This creates dynamic projectile behavior, allowing for effects like projectiles being repelled by certain enemies or drawn towards specific points.