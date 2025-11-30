---
title: Chain Shot Projectile Logic
category: scripts
---

---

# Chain Shot Projectile Logic

This script defines the behavior for projectiles that can chain to other projectiles, creating a sequence of shots. It manages the iteration count and determines the properties of the next projectile in the chain.

## Core Functionality

The primary purpose of this script is to:
1.  **Track Chain Iterations**: Keep count of how many times a projectile has chained.
2.  **Determine Next Projectile**: Select the file and velocity for the subsequent projectile.
3.  **Spawn Chained Projectile**: Create and initialize the next projectile in the chain.

## Key Attributes and Elements

### Variable Storage Component

This script heavily relies on a `VariableStorageComponent` attached to the projectile entity to store and retrieve chain-related information.

| Variable Name    | Type      | Description