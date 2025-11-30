---
title: Hanging Wire Spawner
category: scripts
---

# Hanging Wire Spawner

This script is responsible for procedurally generating hanging wires in the game world. It identifies suitable anchor points on platforms and creates a chain of wire segments connected by physics joints.

## Core Functionality

The script performs the following key actions:

1.  **Environment Check:** It first checks if there are any platforms within a specified horizontal search distance from the spawner's position.
2.  **Anchor Point Identification:** It then raycasts downwards from potential anchor points to find valid surfaces (platforms) to attach the wire.
3.  **Wire Generation:** Based on the identified anchor points, it creates a series of `PhysicsImageShapeComponent` entities for the wire segments and `PhysicsJoint2Component` entities to connect them.
4.  **Physics Initialization:** Finally, it initializes the physics for the created wire components.

## Key Attributes and Parameters

The script utilizes several parameters to control the appearance and behavior of the generated wires.

| Attribute           | Description