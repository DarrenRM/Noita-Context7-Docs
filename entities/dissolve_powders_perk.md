---
title: Dissolve Powders Perk
category: guides
---

<Entity>
    <InheritTransformComponent/>
    <CellEaterComponent
        eat_probability="50"
        radius="10"
        limited_materials="1"
        materials="sand,soil,bone,fungisoil,mud,sandstone,snow,snow_sticky,sand_herb,wax,coal,sulphur,salt,gunpowder,gunpowder_unstable,gunpowder_explosive,gunpowder_tnt,poo,glass_broken"
    />
</Entity>
```

---
title: Dissolve Powders Perk
category: entities
---

# Dissolve Powders Perk

This entity represents a perk that causes the player to dissolve certain materials in their vicinity.

## Key Components

### `CellEaterComponent`

This component governs the behavior of the entity as a "cell eater," meaning it consumes adjacent cells (materials) based on specific criteria.

*   **`eat_probability`**: (float) The chance (0-100) that the entity will attempt to eat a cell.
    *   **Value**: `50`
*   **`radius`**: (float) The area of effect around the entity within which it can consume cells.
    *   **Value**: `10`
*   **`limited_materials`**: (bool) If true, the `materials` attribute specifies the *only* materials that can be eaten. If false, it specifies materials that *cannot* be eaten.
    *   **Value**: `1` (true)
*   **`materials`**: (string) A comma-separated list of material names that the `CellEaterComponent` will target for consumption.
    *   **Value**: `sand,soil,bone,fungisoil,mud,sandstone,snow,snow_sticky,sand_herb,wax,coal,sulphur,salt,gunpowder,gunpowder_unstable,gunpowder_explosive,gunpowder_tnt,poo,glass_broken`