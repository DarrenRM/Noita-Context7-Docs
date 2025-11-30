---
title: VerletPhysicsComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:VerletPhysicsComponent
category: modding-wiki
---

# VerletPhysicsComponent Documentation

This documentation covers the `VerletPhysicsComponent` in Noita, a crucial component for creating and manipulating physics-based entities within the game. Understanding this component is essential for modders looking to implement custom physics behaviors, create dynamic objects, or modify existing entities' physical interactions.

## Overview of Verlet Physics

Verlet physics is a numerical integration method used to simulate the motion of a system of particles. It's known for its stability and efficiency, making it a popular choice for game physics. In Noita, the `VerletPhysicsComponent` allows entities to behave according to these physics principles, enabling effects like cloth simulation, soft bodies, and more.

## Component Properties

The `VerletPhysicsComponent` has several properties that can be configured to alter an entity's physical behavior. These properties are typically defined within an entity's XML definition.

### Core Properties

| Property Name | Type    | Description