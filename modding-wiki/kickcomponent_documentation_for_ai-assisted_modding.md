---
title: KickComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:KickComponent
category: modding-wiki
---

# KickComponent Documentation

This documentation covers the `KickComponent` in Noita, a crucial element for implementing physics-based interactions like pushing and knocking back entities. Understanding this component is essential for modders looking to create dynamic environments, custom projectile behaviors, or unique enemy interactions.

## Understanding KickComponent

The `KickComponent` is responsible for applying a force to an entity when it collides with another entity that has this component. This allows for physics-driven reactions, making the game world feel more alive and interactive.

### Component Properties

The `KickComponent` has several properties that can be configured to control the behavior of the kick. These properties are typically defined within an entity's XML definition.

| Property Name | Type    | Description