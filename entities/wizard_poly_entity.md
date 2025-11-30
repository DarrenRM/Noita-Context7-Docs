---
title: Wizard Poly Entity
category: entities
---

# Wizard Poly Entity

This document describes the `wizard_poly.xml` entity, which represents a specific type of enemy or creature within Noita.

## Key Attributes

### DamageModelComponent
This component defines the combat-related properties of the entity.

| Attribute              | Value        | Description                                     |
| :--------------------- | :----------- | :---------------------------------------------- |
| `hp`                   | `14`         | Current health points of the entity.            |
| `max_hp`               | `14`         | Maximum health points the entity can have.      |
| `minimum_knockback_force` | `100000`     | Minimum force required to knock back the entity. |

### Entity: cape
This nested entity defines a cape attached to the Wizard Poly.

#### Base: cape.xml
The cape uses a predefined entity from `data/entities/verlet_chains/cape/cape.xml`.

#### VerletPhysicsComponent
This component governs the physics simulation of the cape.

| Attribute         | Value     | Description                               |
| :---------------- | :-------- | :---------------------------------------- |
| `cloth_color_edge` | `0xFFEBD1E6` | The color of the cape's edge.             |
| `cloth_color`     | `0xFF773B3E` | The main color of the cape fabric.        |

```xml
<Entity >
  <Base file="data/entities/animals/wizard_poly.xml">
    <DamageModelComponent 
      hp="14"
      max_hp="14"
	  minimum_knockback_force="100000"
     ></DamageModelComponent >
  </Base>
  
  <Entity name="cape">  
        <Base file="data/entities/verlet_chains/cape/cape.xml">
			<VerletPhysicsComponent
        		cloth_color_edge="0xFFEBD1E6"
        		cloth_color="0xFF773B3E">
        	</VerletPhysicsComponent>
        </Base>  
    </Entity>
</Entity>
```