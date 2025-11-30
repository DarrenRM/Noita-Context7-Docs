---
title: Medium Gunpowder Explosion Particle
category: entities
---

# Medium Gunpowder Explosion Particle

This entity defines the visual components of a medium-sized gunpowder explosion particle effect in Noita. It primarily uses `LoadEntitiesComponent` to spawn other particle entities, creating a layered and dynamic explosion.

## Key Components

The core functionality is driven by `LoadEntitiesComponent`, which is responsible for instantiating other pre-defined entities at the location of this particle.

### `LoadEntitiesComponent`

This component dictates which other entities are spawned and how many.

| Attribute     | Description