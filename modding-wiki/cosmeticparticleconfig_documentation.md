---
title: CosmeticParticleConfig Documentation
source: https://noita.wiki.gg/wiki/Documentation:grid::CosmeticParticleConfig
category: modding-wiki
---

# CosmeticParticleConfig Documentation

This documentation covers the `CosmeticParticleConfig` grid component in Noita, which is crucial for defining and customizing the visual effects of cosmetic particles used in the game. Understanding this component allows modders to create unique particle behaviors, appearances, and interactions, significantly enhancing the visual flair of their mods.

## Overview

The `CosmeticParticleConfig` component is a fundamental part of Noita's visual effects system. It dictates how cosmetic particles behave and appear, influencing aspects like their lifespan, movement, color, and emission patterns. By modifying or creating new `CosmeticParticleConfig` entries, modders can introduce entirely new visual elements or alter existing ones to fit their mod's theme and gameplay.

## Structure of a CosmeticParticleConfig

A `CosmeticParticleConfig` is typically defined within an XML file, often in a structure similar to this:

```xml
<noita_cosmetic_particle_config>
    <cosmetic_particle_config name="my_custom_particle">
        <!-- Configuration options go here -->
    </cosmetic_particle_config>
</noita_cosmetic_particle_config>
```

The `name` attribute is a unique identifier for your particle configuration.

## Key Configuration Options

The following are common and important parameters you can set within a `cosmetic_particle_config` tag.

### General Properties

These settings control the basic behavior and appearance of the particles.

| Property             | Type    | Description