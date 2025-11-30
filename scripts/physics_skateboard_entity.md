---
title: Physics Skateboard Entity
category: data/entities
---

# Physics Skateboard Entity

This document describes the `physics_skateboard.xml` entity, which defines a functional skateboard object within the game. It utilizes multiple physics components to simulate the skateboard's body and wheels, along with joints to connect them.

## Key Components

### `PhysicsBodyComponent`

This component defines the physical properties of a rigid body. The skateboard entity uses three instances of this component: one for the main board and one for each wheel.

| Attribute           | Description