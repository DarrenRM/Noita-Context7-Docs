---
title: AnimalAIComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:AnimalAIComponent
category: modding-wiki
---

# AnimalAIComponent Documentation for AI-Assisted Modding

This documentation details the `AnimalAIComponent` in Noita, a crucial component for defining the behavior of animal entities. Understanding its parameters and functionalities is essential for modders looking to create custom AI behaviors, modify existing ones, or integrate new animal-like creatures into the game. This guide breaks down the component's structure and provides practical examples for AI-assisted modding.

## Understanding AnimalAIComponent

The `AnimalAIComponent` is attached to entities that are intended to behave like animals. It governs their movement, target acquisition, and general AI logic. Modifying this component allows for fine-grained control over how these entities interact with the game world and the player.

### Core Parameters

The `AnimalAIComponent` utilizes a variety of parameters to define its behavior. These are typically configured within the entity's XML definition.

#### Movement and Navigation

These parameters control how the animal moves and navigates the environment.

| Parameter             | Type    | Description