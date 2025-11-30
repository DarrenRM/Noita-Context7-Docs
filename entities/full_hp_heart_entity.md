---
title: Full HP Heart Entity
category: entities
---

# Full HP Heart Entity

This entity represents a collectible item that fully restores the player's HP.

## Entity Structure

The `heart_fullhp.xml` file defines a simple entity with a `Base` component that inherits from `parallel_tentacles.xml`. This inheritance suggests it might share some underlying mechanics or visual elements with parallel world tentacles, though its primary function is distinct.

### Key Components

*   **`<Base>`**:
    *   `file`: Specifies the base entity file to inherit from (`data/entities/animals/parallel/tentacles/parallel_tentacles.xml`).
    *   `include_children`: Set to `1`, indicating that child elements from the base entity are included.

*   **`<DamageModelComponent>`**:
    *   `hp`: The current health of the entity. Set to `90`.
    *   `max_hp`: The maximum health of the entity. Set to `90`.

## Usage in Modding

This entity can be used as a pickup item that provides a significant health boost to the player. Its simplicity makes it a good candidate for direct modification or as a base for creating custom health-restoring items.

**Example Modification:**

To change the amount of HP restored, you would modify the `hp` and `max_hp` attributes within the `DamageModelComponent`.

```xml
<Entity >
  <Base file="data/entities/animals/parallel/tentacles/parallel_tentacles.xml" include_children="1">
    <DamageModelComponent 
      hp="100"  <!-- Increased HP restored -->
      max_hp="100" <!-- Increased Max HP -->
     ></DamageModelComponent >
  </Base>
</Entity>
```