---
title: Mass Polymorph Projectile
category: scripts
---

---

# Mass Polymorph Projectile

This script defines the behavior of a projectile that attempts to polymorph nearby enemies.

## Core Functionality

The projectile scans for entities within a radius and applies a polymorph effect to eligible targets.

### Target Acquisition

*   **Radius:** 200 pixels.
*   **Tags Searched:**
    *   `homing_target`
    *   `player_unit` (added to the list of potential targets)

### Polymorph Conditions

An entity will be polymorphed if it meets all of the following criteria:

*   It is within a distance of 300 pixels from the projectile's origin.
*   It is not tagged as `boss`.
*   It is not tagged as `this_is_sampo`.
*   It is not tagged as `polymorphable_NOT`.
*   It must be a root entity (i.e., not a child entity).

### Effect Application

*   If an entity meets the polymorph conditions, the `effect_polymorph.xml` entity is loaded onto it.

## Script Actions

*   **Screenshake:** A screenshake of intensity 100 is triggered.
*   **Self-Destruction:** The projectile entity is killed after its actions are completed.