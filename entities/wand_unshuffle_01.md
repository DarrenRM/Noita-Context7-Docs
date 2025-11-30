---
title: Wand Unshuffle 01
category: entities
---

# Wand Unshuffle 01

This document describes the `wand_unshuffle_01.xml` entity, which defines a specific type of wand in Noita. This wand is characterized by its "unshuffle" behavior, meaning its spell deck does not shuffle after each cast.

## Base Components

The wand inherits functionality from two base entity files:

*   **`data/entities/base_item.xml`**: Provides fundamental item properties like sprite rendering and hover animations.
*   **`data/entities/base_wand.xml`**: Implements core wand mechanics, including shooting, mana management, and spell casting.

## Key Attributes

The `AbilityComponent` defines the primary characteristics of this wand:

| Attribute                 | Value                               | Description