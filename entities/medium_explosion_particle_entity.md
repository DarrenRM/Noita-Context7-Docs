---
title: Medium Explosion Particle Entity
category: entities
---

# Medium Explosion Particle Entity

This entity defines the components that make up a medium-sized explosion effect in Noita. It primarily uses `LoadEntitiesComponent` to spawn other particle entities, creating a layered and dynamic visual effect.

## Key Components

### LoadEntitiesComponent

This component is responsible for spawning other entities. For this explosion, it's used to instantiate various particle effects that contribute to the overall explosion visual.

| Attribute      | Description