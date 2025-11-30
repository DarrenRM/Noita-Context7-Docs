---
title: Main Contained Explosion Particle
category: entities
---

# Main Contained Explosion Particle

This entity defines a core component for contained explosion effects in Noita. It primarily functions by loading other pre-defined particle entities to create a layered visual and functional explosion.

## Key Components

The `LoadEntitiesComponent` is the central element here, responsible for instantiating other entities at the location of this particle.

### `LoadEntitiesComponent`

This component dictates which other entities are loaded and how many.

| Attribute     | Description