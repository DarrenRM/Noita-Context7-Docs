---
title: Dripping Acid Gas Entity
category: entities
---

# Dripping Acid Gas Entity

This document describes the `dripping_acid_gas.xml` entity, which represents a source of dripping acid gas in Noita.

## Core Functionality

The `dripping_acid_gas.xml` entity is a specialized version of `base_dripping_liquid.xml`. Its primary function is to emit `acid_gas` particles.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_dripping_liquid.xml"`**: Inherits core properties and behaviors from the generic dripping liquid entity.

### Particle Emitters

This entity utilizes two `ParticleEmitterComponent` instances to generate the acid gas:

1.  **Emitter 1 (Continuous Emission)**
    *   **`emitted_material_name="acid_gas"`**: Specifies the material to be emitted.
    *   **`emission_interval_min_frames="1"`**: Minimum frames between emissions.
    *   **`emission_interval_max_frames="5"`**: Maximum frames between emissions.
    *   **`gravity.y="-100"`**: Applies a downward gravitational force to the emitted particles.

2.  **Emitter 2 (Burst Emission)**
    *   **`emitted_material_name="acid_gas"`**: Specifies the material to be emitted.
    *   **`emission_interval_min_frames="1"`**: Minimum frames between emissions.
    *   **`emission_interval_max_frames="3"`**: Maximum frames between emissions.
    *   **`count_min="1"`**: Minimum number of particles emitted per burst.
    *   **`count_max="4"`**: Maximum number of particles emitted per burst.

## Entity Tags

*   **`tags="mortal,hittable"`**: Indicates that the entity can be destroyed and can be targeted by attacks.