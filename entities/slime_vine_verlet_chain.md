---
title: Slime Vine Verlet Chain
category: entities
---

# Slime Vine Verlet Chain

This entity defines a slime vine, a type of verlet chain used in Noita. It utilizes the `VerletPhysicsComponent` to simulate its behavior and is constructed from multiple `Base` entities representing its segments.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet chain.

### Key Attributes:

*   **`num_points`**: The number of points (segments) in the verlet chain.
    *   Value: `6`
*   **`stiffness`**: Controls how rigid the chain is. Higher values mean less bending.
    *   Value: `1.0`
*   **`velocity_dampening`**: Reduces the velocity of the points over time, simulating friction or air resistance.
    *   Value: `0.9`
*   **`resting_distance`**: The ideal distance between adjacent points when the chain is at rest.
    *   Value: `4`
*   **`pixelate_sprite_transforms`**: Whether to pixelate the sprites attached to the verlet points.
    *   Value: `1` (enabled)
*   **`follow_entity_transform`**: If enabled, the entire chain will follow the transform of another entity.
    *   Value: `0` (disabled)
*   **`simulate_wind`**: Whether wind affects the verlet chain.
    *   Value: `1` (enabled)
*   **`wind_change_speed`**: How quickly the wind's direction and strength can change.
    *   Value: `0.25`
*   **`simulate_gravity`**: Whether gravity affects the verlet chain.
    *   Value: `1` (enabled)

## Base Components

These components define the visual and physical segments that make up the slime vine. The vine is constructed by chaining together different `slime_vine_verlet_X.xml` files.

*   **`data/entities/verlet_chains/slime_vine/parts/slime_vine_verlet_1.xml`**: Appears to be a standard segment of the vine. This is repeated multiple times to form the main body.
*   **`data/entities/verlet_chains/slime_vine/parts/slime_vine_verlet_2.xml`**: Likely represents a different type of segment, possibly for the end or a junction of the vine.

## MoveToSurfaceOnCreateComponent

This component ensures that the verlet chain attaches itself to a surface when it is created.

### Key Attributes:

*   **`lookup_radius`**: The radius around the creation point to search for a surface.
    *   Value: `28`
*   **`verlet_min_joint_distance`**: The minimum distance between verlet joints for the attachment to be considered valid.
    *   Value: `14`
*   **`type`**: Specifies the type of verlet attachment.
    *   Value: `VERLET_ROPE_ONE_JOINT` (Indicates it will attach with a single joint)