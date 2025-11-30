---
title: IKLimbWalkerComponent
source: https://noita.wiki.gg/wiki/Documentation:IKLimbWalkerComponent
category: modding-wiki
---

# IKLimbWalkerComponent

This documentation page details the `IKLimbWalkerComponent` in Noita, a crucial component for creating entities that can walk and interact with the environment using inverse kinematics. Understanding this component is essential for modders aiming to implement custom characters, enemies, or even environmental hazards with complex locomotion.

## Overview

The `IKLimbWalkerComponent` is responsible for enabling entities to walk and navigate terrain. It utilizes inverse kinematics (IK) to control the movement of limbs, allowing for more natural and responsive animations. This component is fundamental for any entity that needs to move on its own, especially in dynamic environments.

## Component Properties

The `IKLimbWalkerComponent` has several properties that can be configured to alter its behavior. These properties are typically defined within the entity's XML definition file.

### Core Properties

| Property Name        | Type    | Description