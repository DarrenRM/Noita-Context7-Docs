---
title: Small Shield Shot Projectile
category: entities
---

# Small Shield Shot Projectile

This document details the configuration for the `shieldshot_small.xml` projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The projectile is based on the default projectile entity (`$projectile_default`).

```xml
<Entity name="$projectile_default">
  <Base file="data/entities/base_projectile.xml" />
  <ProjectileComponent ... />
  <ParticleEmitterComponent ... />
  <AudioComponent ... />
  <HitEffectComponent ... />
  <VariableStorageComponent ... />
</Entity>
```

## Key Components and Attributes

### ProjectileComponent

This component defines the core behavior and properties of the projectile.

| Attribute                 | Description