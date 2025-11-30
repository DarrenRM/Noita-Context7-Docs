---
title: Crack Ice Entity
category: entities
---

# Crack Ice Entity

This entity represents a crackable ice object that can interact with electricity.

## Key Components

### ElectricityComponent

This component governs the electrical properties of the entity.

*   **`energy`**: The amount of energy the entity can hold or transfer.
    *   Value: `200`
*   **`splitting_energy_min`**: The minimum energy required for electrical splitting.
    *   Value: `0`
*   **`splitting_energy_max`**: The maximum energy that can be used for electrical splitting.
    *   Value: `20`
*   **`speed`**: The speed at which electricity travels through this entity.
    *   Value: `20`
*   **`splittings_min`**: The minimum number of splittings that can occur.
    *   Value: `0`
*   **`splittings_max`**: The maximum number of splittings that can occur.
    *   Value: `2`
*   **`hack_is_material_crack`**: A special flag indicating this entity is related to material cracking.
    *   Value: `1`
*   **`hack_crack_ice`**: A specific flag indicating this entity is designed to crack ice.
    *   Value: `1`

```xml
<Entity>
  <ElectricityComponent
      energy="200"
  	  splitting_energy_min="0"
  	  splitting_energy_max="20"
  	  speed="20"
  	  splittings_min="0"
  	  splittings_max="2"
      hack_is_material_crack="1"
      hack_crack_ice="1"
  >
  </ElectricityComponent>
</Entity>
```