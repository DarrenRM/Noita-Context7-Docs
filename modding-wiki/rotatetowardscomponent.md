---
title: RotateTowardsComponent
source: https://noita.wiki.gg/wiki/Documentation:RotateTowardsComponent
category: modding-wiki
---

# RotateTowardsComponent

This documentation page explains the `RotateTowardsComponent` in Noita, a crucial component for making entities rotate to face a specific target. Understanding this component is essential for modders who want to implement dynamic behaviors like enemies tracking the player, projectiles homing in, or environmental objects reacting to game events.

## Overview

The `RotateTowardsComponent` allows an entity to automatically rotate its visual representation and potentially its physics orientation to face a designated target. This is achieved by defining the target and controlling the speed and smoothness of the rotation.

## Component Properties

The `RotateTowardsComponent` is configured within the entity's XML definition. Here are its key properties:

| Property        | Type    | Description