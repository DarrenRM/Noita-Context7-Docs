---
title: All Spells Effect Script
category: scripts
---

# All Spells Effect Script

This script defines various effects triggered by different "states" of a spell entity. It primarily handles spawning projectiles, particles, or other entities based on a stored state value.

## Key Functionality

The script reads a `state` variable from a `VariableStorageComponent` attached to the spell entity. Based on this `state` value, it executes different logic.

### State-Based Effects

Here's a breakdown of the effects for key states:

| State | Description