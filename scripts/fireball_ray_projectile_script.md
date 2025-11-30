---
title: Fireball Ray Projectile Script
category: scripts
---

# Fireball Ray Projectile Script

This script defines the behavior for a "fireball ray" projectile in Noita. It's designed to be attached to an entity that will then fire this projectile.

## Core Functionality

The primary purpose of this script is to:
*   Get the current entity's ID and root entity.
*   Determine the entity's position.
*   Generate a random angle.
*   Calculate velocity components based on the random angle and a fixed length.
*   Shoot a `fireball_ray.xml` projectile from the entity's position with the calculated velocity.

## Key Attributes

*   **`entity_id`**: The unique identifier for the entity firing the projectile.
*   **`pos_x`, `pos_y`**: The X and Y coordinates of the firing entity.
*   **`angle`**: A randomly generated angle in radians, determining the projectile's direction.
*   **`length`**: A fixed value (3000) that influences the magnitude of the projectile's velocity.
*   **`vel_x`, `vel_y`**: The calculated X and Y components of the projectile's velocity.
*   **`shoot_projectile`**: The core function used to instantiate and launch the projectile.

## Projectile Definition

The projectile itself is defined in:
```xml
data/entities/projectiles/deck/fireball_ray.xml
```
This script only dictates *how* and *where* that projectile is fired.

## Usage

This script is intended to be attached to an entity that should have the capability to fire a fireball ray. The `shoot_projectile` function is a utility that handles the creation and launching of the projectile entity.