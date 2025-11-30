---
title: HomingComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:HomingComponent
category: modding-wiki
---

# HomingComponent Documentation

This documentation explains the `HomingComponent` in Noita, a crucial component for creating projectiles that can track their targets. Understanding and utilizing this component is essential for modders looking to implement advanced projectile behaviors, such as guided missiles or seeking spells.

## Overview

The `HomingComponent` is responsible for making projectiles actively seek out and follow a designated target. This involves defining how the projectile acquires a target, how it steers towards it, and the parameters that govern its homing behavior.

## Component Properties

The `HomingComponent` has several properties that can be configured in your mod's XML files to customize its behavior.

### Target Acquisition

These properties determine how the projectile finds and locks onto a target.

| Property Name | Type    | Description