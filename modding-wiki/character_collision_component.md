---
title: Character Collision Component
source: https://noita.wiki.gg/wiki/Documentation:CharacterCollisionComponent
category: modding-wiki
---

# Character Collision Component

This documentation page details the `CharacterCollisionComponent` in Noita, a crucial component for defining how characters interact with the game world's physics and other entities. Understanding this component is essential for modders looking to customize character behavior, implement new movement mechanics, or create unique collision interactions.

## Overview

The `CharacterCollisionComponent` is responsible for managing a character's physical presence and how it collides with the environment and other game objects. It dictates aspects like the character's hitbox, its interaction with surfaces, and how it responds to forces. Modifying this component allows for fine-grained control over a character's physical properties.

## Component Properties

The `CharacterCollisionComponent` has several properties that can be adjusted via XML files. These properties control various aspects of the character's collision behavior.

### `collision_material`

This property defines the physical material properties of the character's collision.

| Property        | Type   | Description