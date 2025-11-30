---
title: PhysicsJoint2MutatorComponent
source: https://noita.wiki.gg/wiki/Documentation:PhysicsJoint2MutatorComponent
category: modding-wiki
---

# PhysicsJoint2MutatorComponent

This documentation page explains the `PhysicsJoint2MutatorComponent` in Noita, a crucial component for creating and manipulating physics joints within the game's modding framework. Understanding this component is essential for modders who wish to implement custom physics interactions, such as connecting entities, creating complex machinery, or altering the behavior of existing joints.

## Overview

The `PhysicsJoint2MutatorComponent` is a component used in Noita's entity system to define and modify physics joints between two entities. These joints are fundamental for simulating physical connections, allowing objects to interact realistically. This component is typically found within entity XML definitions and can be manipulated via Lua scripting for dynamic effects.

## Component Properties

The `PhysicsJoint2MutatorComponent` has several properties that define the behavior and characteristics of the physics joint it creates.

### Joint Types

The `joint_type` property specifies the kind of physics joint being created.

| Value        | Description