---
title: ShotEffectComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ShotEffectComponent
category: modding-wiki
---

# ShotEffectComponent Documentation

This document details the `ShotEffectComponent` in Noita, a crucial component for defining the effects that projectiles have when they hit something. Understanding and modifying this component is essential for creating custom projectiles with unique behaviors, damage types, status effects, and visual impacts, significantly enhancing the possibilities for AI-assisted modding.

## Overview of ShotEffectComponent

The `ShotEffectComponent` is attached to projectile entities and dictates what happens when that projectile collides with the environment or other entities. It's a versatile component that allows for a wide range of effects, from simple damage application to complex status effect chains and visual transformations.

## Core Functionality and Parameters

The `ShotEffectComponent` uses a variety of parameters to define its behavior. These parameters are typically configured within the projectile's XML definition.

### Common Parameters

| Parameter Name        | Type    | Description