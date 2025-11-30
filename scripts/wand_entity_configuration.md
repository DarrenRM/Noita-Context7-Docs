---
title: Wand Entity Configuration
category: data/entities
---

---

# Wand Entity Configuration

This document details the configuration of the `wand` entity, commonly found in boss pits, which acts as a projectile-spawning entity. It utilizes a `VariableStorageComponent` to determine the projectile to fire and a multiplier for its velocity.

## Key Components and Attributes

### VariableStorageComponent

This component is crucial for defining the wand's behavior. It stores key-value pairs that dictate what projectile to spawn and how it should be launched.

| Attribute     | Description