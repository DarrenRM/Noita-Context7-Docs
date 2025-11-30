---
title: Verlet Cord Entity
category: entities
---

# Verlet Cord Entity

This document describes the `verlet_cord.xml` entity, which defines a basic Verlet physics-based cord. This entity is designed to be used as a foundational element for creating various types of ropes and chains in Noita mods.

## Entity Definition

The `verlet_cord.xml` entity utilizes the `VerletPhysicsComponent` to simulate the behavior of a flexible cord. It also includes a `MoveToSurfaceOnCreateComponent` to ensure the cord attaches correctly to surfaces upon creation.

```xml
<Entity >
    <!-- ... components ... -->
</Entity>
```

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the cord.

| Attribute             | Description