---
title: Meatvine Short Verlet Chain
category: entities
---

# Meatvine Short Verlet Chain

This document describes the `verlet_vine_short.xml` entity, which defines a short, flexible meatvine segment used in Noita. It utilizes the Verlet physics system to simulate its movement and interaction with the environment.

## Entity Structure

The `verlet_vine_short.xml` entity is composed of several key components:

*   **VerletPhysicsComponent**: Governs the physics simulation of the vine.
*   **Base**: References to individual vine segment parts.
*   **MoveToSurfaceOnCreateComponent**: Handles the initial placement of the vine.
*   **AudioComponent**: Manages sound effects associated with the vine.

## Key Components and Attributes

### VerletPhysicsComponent

This component is central to the vine's behavior, defining how it moves and reacts.

| Attribute             | Description