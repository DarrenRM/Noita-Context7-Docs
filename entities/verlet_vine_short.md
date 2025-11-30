---
title: Verlet Vine Short
category: entities
---

# Verlet Vine Short

This entity defines a short, segmented vine using the Verlet physics system. It's designed to be a flexible, chain-like structure that can sway and interact with the environment.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the vine segments.

*   **`num_points`**: `8` - The number of individual points (segments) that make up the vine.
*   **`stiffness`**: `1.0` - Controls how rigid the connections between segments are. A higher value means less bending.
*   **`velocity_dampening`**: `0.9` - Reduces the velocity of segments over time, causing the vine to settle.
*   **`resting_distance`**: `4` - The ideal distance between connected points when the vine is not under tension.
*   **`simulate_gravity`**: `1` - Enables gravity to affect the vine segments.
*   **`constrain_stretching`**: `1` - Prevents the segments from stretching beyond their resting distance.

### Base Entity Inheritance

This entity inherits its visual and structural properties from several other vine segment entities. This allows for variations in appearance and behavior within the same vine structure.

*   `data/entities/animals/boss_centipede/verlet_chains/vine_verlet_1.xml` (Inherited twice)
*   `data/entities/animals/boss_centipede/verlet_chains/vine_verlet_2.xml` (Inherited twice)
*   `data/entities/animals/boss_centipede/verlet_chains/vine_verlet_3.xml` (Inherited twice)
*   `data/entities/animals/boss_centipede/verlet_chains/vine_verlet_4.xml` (Inherited once)

## Tags

*   `vine` - Identifies this entity as a vine.