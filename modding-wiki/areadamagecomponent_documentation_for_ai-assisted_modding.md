---
title: AreaDamageComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:AreaDamageComponent
category: modding-wiki
---

# AreaDamageComponent Documentation

This document details the `AreaDamageComponent` in Noita, a crucial component for defining how entities inflict damage over an area. Understanding and modifying this component is essential for creating custom weapons, spells, and environmental hazards that affect multiple targets simultaneously. This guide provides the necessary information for AI-assisted modding, including its properties, configuration, and practical examples.

## Overview of AreaDamageComponent

The `AreaDamageComponent` is attached to entities that deal damage in a radius around them. This is commonly used for explosions, splash damage from projectiles, or environmental effects. By configuring its various parameters, modders can precisely control the damage dealt, the area of effect, and how it interacts with the game world.

## Component Properties

The `AreaDamageComponent` has several properties that can be adjusted in the entity's XML definition.

### Core Properties

| Property Name        | Type    | Description