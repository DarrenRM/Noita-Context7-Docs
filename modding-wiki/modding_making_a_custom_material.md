---
title: Modding: Making a Custom Material
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_material
category: modding-wiki
---

# Modding: Making a Custom Material

This documentation explains how to create custom materials in Noita, including defining their properties, appearance, and interactions with other materials and game elements. Understanding custom materials is crucial for modders looking to expand the game's world with new substances, unique environmental effects, and complex reaction systems.

## Getting Started

To create a custom material, you'll need to define it in an XML file, typically structured like `data/materials.xml`. This file will contain `<CellData>` or `<CellDataChild>` elements to define your material's properties.

Here's a minimal example:

```xml
<Materials>

  <CellData
    name="my_custom_material"
    ui_name="$mat_my_custom_material"
    wang_color="ff223344"
    >
  </CellData>

  <CellDataChild
    _parent="my_custom_material"
    name="my_custom_material2"
    ui_name="$mat_my_custom_material2"
    wang_color="ff223345"
    >
  </CellDataChild>

  <Reaction probability="1"
    input_cell1="my_custom_material"    input_cell2="air"
    output_cell1="my_custom_material2"  output_cell2="air"
    >
  </Reaction>

</Materials>
```

After creating your XML file (e.g., `mods/your_mod/custom_materials.xml`), you must register it with the game in your mod's `init.lua` file:

```lua
ModMaterialsFileAdd("mods/your_mod/custom_materials.xml")
```

This example adds two new materials and a reaction that transforms the first into the second when exposed to air. Without specified properties, they will use default values.

To ensure your custom material's name appears correctly in-game (e.g., when hovering or in flasks), you need to add translation entries in `init.lua`:

```lua
local content = ModTextFileGetContent("data/translations/common.csv")
content = content .. [[\
mat_my_custom_material,Custom Name,,,,,,,,,,,,,\
mat_my_custom_material2,Custom Name 2,,,,,,,,,,,,,\
]]
content = content:gsub("\r","")
content = content:gsub("\n+","\n")
ModTextFileSetContent("data/translations/common.csv",content)
```

## Basics

### Naming and Inheritance

*   **`name`**: This is the internal identifier for your material. It must be unique. It's recommended to prefix it with your mod's name (e.g., `coolmaterialmod_superpoison`) to avoid conflicts.
*   **`ui_name`**: This is the name displayed to the player. It should be prefixed with `$` if it refers to a translation key (e.g., `$mat_my_custom_material`).
*   **`<CellData>`**: Use this to define a completely new material.
*   **`<CellDataChild>`**: Use this to create a material based on an existing one. You **must** specify a `_parent` attribute.

### `wang_color`

The `wang_color` is a unique hexadecimal ARGB (Alpha, Red, Green, Blue) color value. The game uses these colors to identify and place materials in the world via wang tiles and pixel scenes. Ensure your `wang_color` is unique to avoid overwriting existing materials.

### Inheriting and Modifying Materials

You can create variations of existing materials by using `<CellDataChild>` and overriding specific properties. For example, to make a liquid version of sand:

```xml
<CellDataChild
  _parent="sand"
  name="mymod_liquid_sand"
  ui_name="Liquid sand"
  wang_color="ff0b4115"
  liquid_sand="0"
  >
</CellDataChild>
```

In this example, `liquid_sand="0"` overrides the parent's `liquid_sand="1"` property, making it flow like a liquid rather than acting as solid ground.

## Adding Graphics and Texture

If no graphics are specified, the `wang_color` with full opacity will be used as the material's visual representation. To define custom graphics:

*   **Color:** Use the `<Graphics>` child element with a `color` attribute (ARGB format).

    ```xml
    <CellDataChild
      _parent="sand"
      name="mymod_liquid_sand"
      ui_name="Liquid sand"
      wang_color="ff0b4115"
      liquid_sand="0"
      >
      <Graphics color="8000ff00">
      </Graphics>
    </CellDataChild>
    ```
    This makes the material translucent green.

*   **Texture:** Use the `<Graphics>` child element with a `texture_file` attribute pointing to your texture.

    ```xml
    <Graphics texture_file="data/materials_gfx/lavarock.png">
    </Graphics>
    ```

You can also define textures for edges and different orientations, but this is more advanced.

## Material Types

A material's type is primarily determined by the `cell_type` property, which can be one of: `solid`, `liquid`, `fire`, or `gas`.

*   **`solid`**: Typically used for physics objects like boxes, ice, and glass, which are simulated using the Box2D physics system. Using too many `solid` materials can impact performance.
*   **`liquid`**: Includes substances like water, lava, and acid. Materials like sand are technically `liquid` but have the `liquid_sand="1"` property, allowing them to be stood upon.
*   **`fire`**: Represents flames and burning materials.
*   **`gas`**: For gaseous substances.

Most material behaviors are a combination of properties. Referencing existing materials in `data/materials.xml` is the best way to understand how to achieve specific effects. Properties starting with `liquid_` generally apply only to `liquid` types, `solid_` to `solid` types, and so on.

## Stain and Ingestion Effects

Liquids (and sometimes sand) can apply stains to entities or have ingestion effects when consumed.

To define these effects, use child elements within your `<CellData>` or `<CellDataChild>`:

```xml
<CellDataChild
  _parent="sand"
  name="mymod_liquid_sand"
  ui_name="Liquid sand"
  wang_color="ff0b4115"
  liquid_sand="0"
  liquid_stains="2"
  >
  <StatusEffects>
    <Stains>
      <StatusEffect type="SLIMY" />
    </Stains>
    <Ingestion>
      <StatusEffect type="FOOD_POISONING" amount="0.2" />
    </Ingestion>
  </StatusEffects>
</CellDataChild>
```

*   **`liquid_stains="2"`**: This is required for the material to apply stains and visual effects to the world. Other values for `liquid_stains` exist for different staining behaviors.

## Reactions

Reactions define how materials interact with each other. This includes melting, dissolving, transforming, and more.

A basic reaction is defined as follows:

```xml
<Reaction probability="1"
  input_cell1="my_custom_material"    input_cell2="air"
  output_cell1="my_custom_material2"  output_cell2="air"
  >
</Reaction>
```

*   **`probability`**: Controls the reaction speed.
*   **`input_cell1`, `input_cell2`**: The materials required for the reaction.
*   **`output_cell1`, `output_cell2`**: The materials produced by the reaction.

### Tag-Based Reactions

Reactions can also use tags for more flexible interactions:

```xml
<Reaction probability="20"
  input_cell1="[meltable]"              input_cell2="[lava]"
  output_cell1="[meltable]_molten"      output_cell2="[lava]"
  >
</Reaction>
```

This reaction applies to any material tagged `[meltable]` when it comes into contact with a material tagged `[lava]`. The output material's name is formed by appending `_molten` to the input material's name (e.g., `wax` becomes `wax_molten`). Ensure the output material exists.

## Making Materials Deal Damage

A material's damage is not a direct property but is handled by the `DamageModelComponent` of the entity being damaged. To make a material deal damage:

1.  **Modify the `DamageModelComponent`**: You need to add your material to the `materials_that_damage` and `materials_how_much_damage` properties of the target entity's `DamageModelComponent`. These are comma-separated strings.

    *   `materials_that_damage="acid,lava,magic_gas_hp_regeneration"`
    *   `materials_how_much_damage="0.005,0.003,-0.005"`

    Damage is calculated per particle, per tick, divided by 25. For example, 0.1 damage per particle requires a value of `0.004`.

2.  **Use Helper Functions (Lua)**: Modifying comma-separated strings can be cumbersome. The following Lua functions can help manage damage properties:

    ```lua
    local function stringsplit(inputstr, sep)
      sep = sep or "%s"
      local t = {}
      for str in string.gmatch(inputstr, "([^"..sep.."]+)") do
        table.insert(t, str)
      end
      return t
    end

    -- Returns a key-value table, where the keys are the material name and the values the damage.
    function get_materials_that_damage(entity_id)
      local out = {}
      local damage_model_component = EntityGetFirstComponentIncludingDisabled(entity_id, "DamageModelComponent")
      if damage_model_component then
        local materials_that_damage = ComponentGetValue2(damage_model_component, "materials_that_damage")
        materials_that_damage = stringsplit(materials_that_damage, ",")
        local materials_how_much_damage = ComponentGetValue2(damage_model_component, "materials_how_much_damage")
        materials_how_much_damage = stringsplit(materials_how_much_damage, ",")
        for i, v in ipairs(materials_that_damage) do
          out[v] = materials_how_much_damage[i]
        end
        return out
      end
    end

    -- <materials> should be a key-value table with the keys being the name of the material to change and the value the new damage.
    -- For instance: change_materials_that_damage(entity_id, { lava = 0, new_material = 0.004 }) would make the entity immune to lava
    -- and the material with name="new_material" would deal 0.004 damage.
    function change_materials_that_damage(entity_id, materials)
      -- At the time of writing (1st of September 2020) changes to DamageModelComponent:materials_that_damage
      -- do not take effect. One of the ways to work around that is to remove and re-add the component with
      -- the changes applied and the same old values for everything else
      local damage_model_component = EntityGetFirstComponentIncludingDisabled(entity_id, "DamageModelComponent")
      if damage_model_component then
        -- Retrieve and store all old values of the DamageModelComponent
        local old_values = {}
        local old_damage_multipliers = {}
        for k,v in pairs(ComponentGetMembers(damage_model_component)) do
          -- ComponentGetMembers does not return the value for ragdoll_fx_forced, ComponentGetValue2 is necessary
          if k == "ragdoll_fx_forced" then
            v = ComponentGetValue2(damage_model_component, k)
          end
          old_values[k] = v
        end
        for k,_ in pairs(ComponentObjectGetMembers(damage_model_component, "damage_multipliers")) do
          old_damage_multipliers[k] = ComponentObjectGetValue(damage_model_component, "damage_multipliers", k)
        end
        -- Build comma separated string
        old_values.materials_that_damage = ""
        old_values.materials_how_much_damage = ""
        local old_materials_that_damage = get_materials_that_damage(entity_id)
        for material, damage in pairs(materials) do
          old_materials_that_damage[material] = damage
        end
        for material, damage in pairs(old_materials_that_damage) do
          local comma = old_values.materials_that_damage == "" and "" or ","
          old_values.materials_that_damage = old_values.materials_that_damage .. comma .. material
          old_values.materials_how_much_damage = old_values.materials_how_much_damage .. comma .. damage
        end
        EntityRemoveComponent(entity_id, damage_model_component)
        damage_model_component = EntityAddComponent(entity_id, "DamageModelComponent", old_values)
        ComponentSetValue2(damage_model_component, "ragdoll_fx_forced", old_values.ragdoll_fx_forced)
        for k, v in pairs(old_damage_multipliers) do
          ComponentObjectSetValue(damage_model_component, "damage_multipliers", k, v)
        end
      end
    end
    ```

    **Usage in `init.lua`**:

    ```lua
    function OnPlayerSpawned(player_entity)
      change_materials_that_damage(player_entity, { your_new_material = 0.004 })
    end
    ```

Making enemies take damage from materials is more complex and requires individual modification of each enemy's `DamageModelComponent`.

## List of All Known Material Properties

This list details various properties you can assign to materials.

### General Properties

| Property                      | Value Type / Range      | Info