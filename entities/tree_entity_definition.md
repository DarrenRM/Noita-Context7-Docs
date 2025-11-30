---
title: Tree Entity Definition
category: guides
---

<Entity 
  name="tree_entity" 
  tags="vegetation" >

  <SimplePhysicsComponent 
    can_go_up="0"
    >
  </SimplePhysicsComponent >
  
  <VelocityComponent />
  
</Entity>
```

---
title: Tree Entity Definition
category: entities
---

# Tree Entity Definition

This document describes the `tree_entity.xml` file, which defines a basic tree entity in Noita.

## Key Attributes

The `Entity` element is the root for this definition.

### `name`
- **Description:** The internal name of the entity.
- **Value:** `tree_entity`

### `tags`
- **Description:** Tags associated with the entity, used for game logic and identification.
- **Value:** `vegetation`

## Key Components

### `SimplePhysicsComponent`
- **Description:** Defines basic physics properties for the entity.
- **Key Attributes:**
    - `can_go_up`: A boolean (0 for false, 1 for true) indicating if the entity can move upwards. In this case, it's set to `0`, meaning trees cannot move upwards.

### `VelocityComponent`
- **Description:** This component is present but has no specific attributes defined in this minimal example. It typically handles the entity's velocity and movement.

---