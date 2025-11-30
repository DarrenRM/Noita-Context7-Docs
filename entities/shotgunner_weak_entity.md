---
title: Shotgunner (Weak) Entity
category: entities
---

# Shotgunner (Weak) Entity

This document describes the `shotgunner_weak.xml` entity, a basic variant of the Shotgunner enemy in Noita, with an added "drunk forever" effect.

## Entity Definition

The core of this entity is its inheritance from a base Shotgunner definition, with the addition of a persistent drunk effect.

```xml
<Entity name="$animal_shotgunner">
 	<Base file="data/entities/animals/shotgunner_weak.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
</Entity>
```

### Key Elements

*   **`<Base file="data/entities/animals/shotgunner_weak.xml" include_children="1" />`**: This line indicates that the entity inherits all properties and child elements from `shotgunner_weak.xml`. This is the primary definition for the weak shotgunner's behavior and appearance.
*   **`<Entity>`**: A nested entity is introduced to apply additional effects.
*   **`<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />`**: This applies the `effect_drunk_forever.xml` to the shotgunner, causing it to perpetually be under the influence of alcohol, likely affecting its movement and aiming.

## Inherited Behavior (from `shotgunner_weak.xml`)

While the specific details of `shotgunner_weak.xml` are not provided here, it's understood to define the following core aspects of a weak shotgunner:

*   **AI/Behavior**: How it moves, targets the player, and attacks.
*   **Attacks**: Likely includes a shotgun-like projectile attack.
*   **Visuals**: Sprite, animations, and other visual representations.
*   **Stats**: Health, damage, speed, etc.

## Added Effect (from `effect_drunk_forever.xml`)

The inclusion of `effect_drunk_forever.xml` adds the following characteristic:

*   **Drunk State**: The entity will permanently exhibit behaviors associated with being drunk, such as erratic movement, potentially altered accuracy, or other visual cues.