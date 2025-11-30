---
title: Main Guts Explosion Particle Entity
category: entities
---

# Main Guts Explosion Particle Entity

This entity defines the components that make up the "main guts" explosion particle effect in Noita. It primarily uses `LoadEntitiesComponent` to spawn other pre-defined particle entities, creating a complex visual effect from simpler parts.

## Key Components

The core functionality of this entity is driven by the `LoadEntitiesComponent`. Each instance of this component is responsible for loading and spawning another entity file, effectively layering different particle effects to form the final explosion.

### `LoadEntitiesComponent`

This component is used to load and instantiate other entities.

| Attribute      | Description