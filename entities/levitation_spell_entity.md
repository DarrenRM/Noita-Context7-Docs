---
title: Levitation Spell Entity
category: entities
---

# Levitation Spell Entity

This document describes the `levitation_entity.xml` file, which defines the properties of the Levitation spell entity in Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

### Key Attributes

*   **`tags`**: `spell,levitation` - This tag indicates that the entity is a spell and specifically grants the levitation effect.

## Components

### LifetimeComponent

This component controls how long the entity persists.

*   **`lifetime`**: `600` - The entity will exist for 600 frames (approximately 10 seconds).