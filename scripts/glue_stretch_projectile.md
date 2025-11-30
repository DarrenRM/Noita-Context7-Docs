---
title: Glue Stretch Projectile
category: scripts
---

---

# Glue Stretch Projectile

This script defines the behavior for a "glue stretch" projectile in Noita. It creates a visual effect that stretches between two anchor points, simulating a sticky substance. The glue weakens and breaks over time or if the anchors move too far apart.

## Key Attributes and Behavior

### Anchor Points
The projectile relies on two "glue anchor" entities to define its start and end points. If these anchors are not present or are missing, the projectile is destroyed.

### Breaking Conditions
The glue stretch has two primary breaking conditions:

*   **Distance:** If the distance between the anchor points exceeds a calculated `break_dist`, the projectile is destroyed.
*   **Aging:** The `break_dist` decreases over time, making the glue weaker and more prone to breaking as the game progresses.

### Visual Properties
The script dynamically adjusts the visual representation of the glue stretch:

*   **Position:** The sprite is centered between the two anchor points.
*   **Rotation:** The sprite is rotated to align with the angle between the anchors.
*   **Scaling:**
    *   `scale_x`: Determined by the distance between anchors relative to the sprite's `sprite_width`.
    *   `scale_y`: Decreases as the distance between anchors increases, making the glue appear thinner when stretched further.
*   **Alpha (Transparency):** The transparency of the glue decreases as the distance between anchors increases, making it more faded when stretched.

### Parameters

| Parameter              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `initial_break_distance` | The maximum distance the glue can stretch at the moment of creation.        |
| `final_break_distance`   | The minimum distance the glue can stretch before it is guaranteed to break. |
| `aging_speed`          | How quickly the `break_dist` decreases over time.                           |
| `sprite_width`         | The visible pixel width of the glue sprite, used for scaling calculations.  |

### Core Logic

The script performs the following steps:

1.  **Initialization:** Retrieves the entity ID and sets up initial parameters.
2.  **Anchor Detection:** Finds and records the positions of child entities tagged as "glue\_anchor".
3.  **Anchor Validation:** Checks if at least two anchors are found. If not, the projectile is destroyed.
4.  **Angle and Distance Calculation:** Determines the angle and distance between the anchor points.
5.  **Break Distance Calculation:** Calculates the current `break_dist` based on initial distance, aging, and the final minimum distance.
6.  **Distance Check:** If the current distance exceeds `break_dist`, the projectile is destroyed.
7.  **Sprite Transformation:**
    *   Calculates the position, angle, and scale for the glue sprite.
    *   Applies these transformations to the projectile entity.
8.  **Alpha Adjustment:** Sets the transparency of the sprite based on the stretch distance.