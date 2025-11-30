---
title: Critical Hit Oil Effect
category: guides
---

<Entity>
    
    <HitEffectComponent 
        condition_effect="OILED"
        effect_hit="CRITICAL_HIT_BOOST"
        value="100" >
	</HitEffectComponent >

</Entity>
```

---
title: Critical Hit Oil Effect
category: entities
---

# Critical Hit Oil Effect

This entity defines a special hit effect that triggers when an entity is "OILED" and receives a critical hit.

## HitEffectComponent

This component governs the effects that occur when an entity is hit under specific conditions.

### Key Attributes:

*   **`condition_effect`**: Specifies the condition that must be met for the effect to trigger. In this case, it's `"OILED"`, meaning the target must be covered in oil.
*   **`effect_hit`**: Defines the type of effect applied upon a critical hit. Here, it's `"CRITICAL_HIT_BOOST"`, indicating an enhancement to critical hits.
*   **`value`**: The numerical value associated with the effect. A value of `"100"` suggests a significant boost or multiplier for the critical hit.