---
title: Electricity Component (Weak)
category: guides
---

<Entity>
	<ElectricityComponent
		energy="50"
		speed="16"
		probability_to_heat="0.1" >
	</ElectricityComponent>
</Entity>
```

---
title: Electricity Component (Weak)
category: entities
---

# Electricity Component (Weak)

This entity defines a basic, weak electrical effect. It's primarily used for simple electrical hazards or interactions.

## Key Attributes

The `ElectricityComponent` is the core of this entity.

### `ElectricityComponent`

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `energy`              | The amount of energy this electrical effect carries. (50 in this case)        |
| `speed`               | The speed at which the electricity propagates or its effect manifests. (16) |
| `probability_to_heat` | The chance that this electrical effect will also cause heating. (0.1)       |