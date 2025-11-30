---
title: Drunk Shotgunner Entity
category: entities
---

# Drunk Shotgunner Entity

This entity defines a variant of the standard Shotgunner enemy that is permanently drunk.

## Core Components

*   **Base Entity:** Inherits all properties from `data/entities/animals/shotgunner.xml`. This means it possesses the core AI, movement, and attack behaviors of a regular Shotgunner.
*   **Drunk Effect:** Integrates the `data/entities/misc/effect_drunk_forever.xml` entity. This applies a permanent drunk status effect to the Shotgunner, likely influencing its movement, accuracy, or behavior in ways defined by that effect's XML.

## Key Attributes (Inherited from Shotgunner.xml)

While the specific attributes are inherited, the drunk effect will modify their manifestation. Key aspects of the Shotgunner behavior to consider are:

*   **AI:** The underlying AI controlling its movement, target acquisition, and attack patterns.
*   **Weapon:** The type of weapon it wields (likely a shotgun, given the name).
*   **Projectile:** The properties of the projectiles it fires.
*   **Health/Damage:** Its survivability and offensive capabilities.
*   **Movement Speed:** How quickly it traverses the environment.

## Drunk Effect (`effect_drunk_forever.xml`)

The `effect_drunk_forever.xml` entity is responsible for the "drunk" aspect. Its specific implementation would detail:

*   **Visual Effects:** Any visual distortions or particle effects associated with being drunk.
*   **Behavioral Modifiers:** Changes to movement patterns (e.g., erratic movement), aiming accuracy, or attack frequency.
*   **Duration:** The "forever" in the filename implies a permanent state for this entity.

## Usage

This entity is likely used to introduce a more challenging or unpredictable variant of the Shotgunner enemy into the game world, adding a layer of chaos to combat encounters.