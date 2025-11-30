---
title: Verlet Cord Long Entity
category: entities
---

# Verlet Cord Long Entity

This document describes the `verlet_cord_long.xml` entity, which defines a long, flexible cord using the Verlet physics system in Noita.

## Entity Definition

The core of this entity is the `VerletPhysicsComponent`, which dictates how the cord behaves in the game world.

### `VerletPhysicsComponent`

This component enables the entity to simulate a chain of connected points (a Verlet chain) that can bend, stretch, and react to physics.

| Attribute             | Description