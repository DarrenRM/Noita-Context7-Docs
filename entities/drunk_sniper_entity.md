---
title: Drunk Sniper Entity
category: entities
---

# Drunk Sniper Entity

This entity represents a "drunk" variant of the standard sniper enemy in Noita. It inherits its core behavior from `data/entities/animals/sniper.xml` and gains a permanent drunk effect from `data/entities/misc/effect_drunk_forever.xml`.

## Key Components

### Base Entity
*   **`data/entities/animals/sniper.xml`**: This file defines the fundamental properties and behaviors of the sniper enemy, including its movement, AI, and attack patterns. The `include_children="1"` attribute ensures that all elements from this base file are incorporated.

### Drunk Effect
*   **`data/entities/misc/effect_drunk_forever.xml`**: This entity applies a persistent drunk effect to the sniper. This likely influences its movement, aiming, or other behaviors in a way that simulates intoxication. The `include_children="1"` attribute ensures this effect is applied.

## XML Structure

```xml
<Entity name="$animal_sniper" >
 	<Base file="data/entities/animals/sniper.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
</Entity>
```