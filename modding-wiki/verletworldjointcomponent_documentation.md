---
title: VerletWorldJointComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:VerletWorldJointComponent
category: modding-wiki
---

# VerletWorldJointComponent Documentation

This documentation covers the `VerletWorldJointComponent`, a crucial component in Noita's physics system that allows for the creation of interconnected, flexible, and dynamic physical elements. Understanding this component is essential for modders looking to implement complex physics interactions, create new types of objects with unique behaviors, or modify existing ones to behave in novel ways.

## Understanding VerletWorldJointComponent

The `VerletWorldJointComponent` is used to create joints between entities in Noita's Verlet physics simulation. These joints allow entities to be connected, influencing each other's movement and behavior in a physically plausible manner. This is fundamental for creating chains, ropes, cloth-like structures, and other articulated objects.

### Component Properties

The `VerletWorldJointComponent` has several properties that can be configured to define the behavior of the joint. These properties are typically set within an entity's XML definition.

| Property Name | Type    | Description