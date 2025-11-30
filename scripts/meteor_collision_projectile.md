---
title: Meteor Collision Projectile
category: scripts
---

# Meteor Collision Projectile

This script defines the behavior of a projectile that simulates a meteor's collision. It primarily focuses on disabling world penetration for the projectile.

## Key Attributes

### ProjectileComponent

This component governs the projectile's fundamental properties.

*   **`penetrate_world`**: Set to `false`. This ensures that the meteor projectile will not pass through the game world's geometry upon impact.