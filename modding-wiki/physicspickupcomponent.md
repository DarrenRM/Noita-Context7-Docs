---
title: PhysicsPickUpComponent
source: https://noita.wiki.gg/wiki/Documentation:PhysicsPickUpComponent
category: modding-wiki
---

# PhysicsPickUpComponent

This documentation covers the `PhysicsPickUpComponent` in Noita, a crucial component for defining how items behave when picked up by the player or other entities. Understanding this component is essential for modders looking to create custom items, modify existing ones, or implement unique pickup mechanics. It dictates properties like what can be picked up, how it's picked up, and what happens after pickup.

## Overview

The `PhysicsPickUpComponent` is attached to entities that can be picked up. It defines the conditions and effects associated with the pickup action. This includes specifying which entity tags can pick up the item, whether the pickup is instantaneous or requires a delay, and what Lua functions or game events are triggered upon successful pickup.

## Component Properties

The `PhysicsPickUpComponent` has several properties that can be configured in your mod's XML files. These properties control the behavior of the pickup mechanism.

### Core Properties

| Property Name        | Type    | Description