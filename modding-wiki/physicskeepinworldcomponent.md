---
title: PhysicsKeepInWorldComponent
source: https://noita.wiki.gg/wiki/Documentation:PhysicsKeepInWorldComponent
category: modding-wiki
---

# PhysicsKeepInWorldComponent

This documentation page explains the `PhysicsKeepInWorldComponent` in Noita, a crucial component for controlling how entities interact with the game's physics boundaries. Understanding this component is essential for modders who want to create entities that behave predictably, whether they should be confined to the playable area or allowed to exit.

## PhysicsKeepInWorldComponent

The `PhysicsKeepInWorldComponent` is a component that can be added to entities to influence their behavior when they approach the edges of the game world. It primarily controls whether an entity is "kept in world" or allowed to leave.

### Component Properties

The `PhysicsKeepInWorldComponent` has the following properties that can be configured in an entity's XML definition:

| Property Name | Type    | Description