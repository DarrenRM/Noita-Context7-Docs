---
title: PhysicsImageShapeComponent
source: https://noita.wiki.gg/wiki/Documentation:PhysicsImageShapeComponent
category: modding-wiki
---

# PhysicsImageShapeComponent

This documentation page explains the `PhysicsImageShapeComponent` in Noita, a crucial component for defining the physical collision shapes of entities based on their sprite images. Understanding this component is essential for modders who want to create custom entities with specific physical interactions, such as enemies, projectiles, or environmental objects.

## Overview

The `PhysicsImageShapeComponent` allows entities to have their collision shapes automatically generated from their sprite's alpha channel. This means that transparent areas of the sprite will not participate in physics, while opaque areas will. This component is fundamental for creating visually accurate and physically consistent entities in Noita.

## Component Properties

The `PhysicsImageShapeComponent` has the following properties that can be configured in an entity's XML definition:

| Property Name | Type    | Description