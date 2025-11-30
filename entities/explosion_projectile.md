---
title: Explosion Projectile
category: entities
---

# Explosion Projectile

This document details the configuration for an explosion projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of this entity is a projectile that, upon death (either from low velocity or lifetime expiration), triggers an explosion.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties. The `VelocityComponent` is present but empty, indicating that velocity is managed by the `ProjectileComponent`.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior and explosion characteristics.

| Attribute                 | Description