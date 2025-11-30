---
title: Verlet Rope Load Test Entities
category: entities
---

# Verlet Rope Load Test Entities

This file contains functions for loading test entities that utilize verlet ropes with varying numbers of joints. These are primarily for debugging and testing purposes.

## Functions

### `load_rope_two_joints()`

Loads a verlet rope with two joints.

### `load_rope_one_joint()`

Loads a verlet rope with one joint.

## Key Elements

The core functionality relies on the `load_verlet_rope_with_two_joints` and `load_verlet_rope_with_one_joint` functions, which are assumed to be defined in `data/scripts/lib/utilities.lua`. These functions likely handle the instantiation and configuration of verlet rope entities based on a provided XML definition and positional parameters.

The specific verlet rope entity being loaded is `data/entities/verlet_chains/vines/verlet_vine.xml`.

**Example Usage (Conceptual):**

```lua
-- Assuming utilities.lua is loaded and contains the necessary functions

-- Load a verlet rope with two joints at specific coordinates
load_rope_two_joints()

-- Load a verlet rope with one joint at specific coordinates
load_rope_one_joint()
```