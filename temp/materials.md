---
title: materials
category: temp
source: https://github.com/NathanSnail/noitadata/tree/main/data/temp/materials.xml
---

# materials

This `materials.xml` file is a core component of Noita's data, defining the properties and behaviors of every material that exists within the game world. It dictates how these materials interact with each other, with the player, and with the environment. This includes their physical characteristics (density, gravity, state), their reactions to heat and fire, their visual appearance, and their unique gameplay effects. Essentially, this file is the blueprint for the game's dynamic simulation of its world.

## File Structure

The `materials.xml` file is structured as an XML document. The root element is `<Materials>`, which contains individual definitions for each material.

Each material is defined by a `<CellData>` element. This element has numerous attributes that specify the material's properties. Some attributes are common across many materials, while others are specific to certain types of interactions or behaviors.

There are also `<CellDataChild>` elements, which appear to be used for creating variations of existing materials, inheriting properties from a parent material and then overriding or adding specific attributes.

Key XML tags and attributes observed:

*   **`<Materials>`**: The root element enclosing all material definitions.
*   **`<CellData>`**: Defines a specific material.
    *   **`name`**: A unique identifier for the material (e.g., "air", "fire", "water", "gunpowder").
    *   **`tags`**: A string containing space-separated tags enclosed in square brackets (e.g., `[fire]`, `[static]`, `[liquid]`, `[corrodible]`). These tags categorize materials and influence their interactions.
    *   **`burnable`**: Indicates if the material can burn (0 for no, 1 for yes).
    *   **`density`**: The material's density, affecting its movement and interaction with other fluids.
    *   **`cell_type`**: The general classification of the material (e.g., "fire", "liquid", "gas", "solid").
    *   **`wang_color`**: A hexadecimal color string, likely used for internal mapping or rendering.
    *   **`generates_smoke`**: How much smoke is generated when this material is active or burning.
    *   **`liquid_gravity`**: The gravitational pull on this liquid material.
    *   **`liquid_sand`**: Indicates if the liquid behaves like sand (e.g., falls through gaps).
    *   **`liquid_static`**: If the liquid is static or doesn't flow easily.
    *   **`on_fire`**: Whether the material is inherently on fire.
    *   **`requires_oxygen`**: If the material needs oxygen to exist or burn.
    *   **`temperature_of_fire`**: The base temperature of the material when it's on fire.
    *   **`cell_type`**: The general classification of the material (e.g., "fire", "liquid", "gas", "solid").
    *   **`wang_color`**: A hexadecimal color string, likely used for internal mapping or rendering.
    *   **`generates_smoke`**: How much smoke is generated when this material is active or burning.
    *   **`liquid_gravity`**: The gravitational pull on this liquid material.
    *   **`liquid_sand`**: Indicates if the liquid behaves like sand (e.g., falls through gaps).
    *   **`liquid_static`**: If the liquid is static or doesn't flow easily.
    *   **`on_fire`**: Whether the material is inherently on fire.
    *   **`requires_oxygen`**: If the material needs oxygen to exist or burn.
    *   **`temperature_of_fire`**: The base temperature of the material when it's on fire.
    *   **`gfx_glow`**: The intensity of the material's glow effect.
    *   **`hp`**: Hit points or durability of the material.
    *   **`convert_to_box2d_material`**: Specifies a Box2D physics material to convert to.
    *   **`solid_restitution`**: The bounciness of a solid material.
    *   **`solid_break_to_type`**: The material it breaks into when destroyed.
    *   **`solid_on_collision_material`**: The material it becomes when colliding with a solid.
    *   **`solid_on_collision_splash_power`**: The splash effect when colliding with a solid.
    *   **`autoignition_temperature`**: The temperature at which the material ignites spontaneously.
    *   **`fire_hp`**: How much damage fire can inflict on this material.
    *   **`explosion_sprite`**: Path to a sprite for explosions.
    *   **`create_cell_probability`**: Probability of creating a new cell upon explosion.
    *   **`create_cell_material`**: The material to create upon explosion.
    *   **`spark_material`**: The material of sparks generated.
    *   **`r`, `g`, `b`**: RGB color components for specific effects.
*   **`<Graphics>`**: Contains visual properties for the material.
    *   **`color`**: The primary color of the material.
    *   **`texture_file`**: Path to the texture image for the material.
*   **`<CellDataChild>`**: Defines a variation of a parent material.
    *   **`_parent`**: The name of the parent `CellData` element.
    *   Other attributes can be overridden or added.
*   **`<ExplosionConfig>`**: Defines parameters for explosions.
    *   **`cell_explosion_power`**: The power of the explosion on cells.
    *   **`cell_explosion_damage_required`**: Damage required to trigger the explosion.
    *   **`cell_explosion_radius_min`**: Minimum radius of the explosion.
    *   **`ray_energy`**: Energy of rays emitted by the explosion.

Comments (`<!-- ... -->`) are used extensively to explain the purpose of sections, provide lists of required materials, suggest ordering, and define tag meanings.

## Key Patterns

*   **Categorization by Tags**: The `tags` attribute is a crucial organizational tool. Materials are grouped by their fundamental properties and behaviors (e.g., `[fire]`, `[static]`, `[liquid]`, `[corrodible]`, `[meltable]`, `[radioactive]`). This allows for efficient lookup and application of game logic.
*   **Material States and Transformations**: Many materials have properties that define their state (e.g., `frozen`, `molten`) and how they transform into other materials (e.g., `meltable_to_lava`, `convert_to_box2d_material`, `solid_break_to_type`).
*   **Interaction Properties**: Attributes like `burnable`, `density`, `liquid_gravity`, `requires_oxygen`, `autoignition_temperature`, and `hp` define how materials interact with each other and with game entities.
*   **Visual Representation**: The `<Graphics>` tag, with its `color` and `texture_file` attributes, dictates the visual appearance of each material.
*   **Hierarchical Definitions**: The use of `<CellDataChild>` suggests a system for defining base materials and then creating specialized variants with minor modifications, promoting code reuse and organization.
*   **Order and Dependencies**: Comments indicate a suggested order for materials, possibly for loading or processing efficiency, and list materials that are required for certain game mechanics.
*   **Physics Integration**: Attributes like `cell_type="solid"`, `solid_restitution`, and `convert_to_box2d_material` show integration with physics engines.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `air` Material:**

```xml
  <CellData 
	name="air"  
	wang_color="ff000042" >
  </CellData>
```

*   **Explanation**: This is a very basic definition for "air". It has a name and a `wang_color`. It lacks many attributes, suggesting it's a fundamental, inert material that serves as a baseline for other gaseous or empty spaces.

**2. `fire` Material:**

```xml
  <CellData 
	name="fire"  
  	tags="[fire]"
	burnable="0"  
	density="1"  
	cell_type="fire" 
	wang_color="ffFF6060"
	generates_smoke="5"  
	liquid_gravity="0.5"  
	liquid_sand="0"  
	on_fire="1"  
	requires_oxygen="1"  
	temperature_of_fire="100"
	gfx_glow="255" >
	<Graphics
		color="ffff6000" >
	</Graphics>
  </CellData>
```

*   **Explanation**: This defines the "fire" material. It's tagged as `[fire]`, has a density, is of `cell_type="fire"`, generates smoke, requires oxygen, and has a high `temperature_of_fire`. The `burnable="0"` attribute is interesting, implying fire itself doesn't burn but rather *is* burning. It also has a glowing visual effect.

**3. `gunpowder` Material:**

```xml
  <CellData
	name="gunpowder"
  	tags="[sand_other],[corrodible],[alchemy]"
	burnable="1"
	density="7"
	cell_type="liquid"
	wang_color="ffb89e57"
	generates_smoke="10"
	liquid_gravity="0.5"
	liquid_sand="1"
	on_fire="0"
	requires_oxygen="1"
	temperature_of_fire="50"
	autoignition_temperature="80"
	hp="1000" 
	fire_hp="300"
	>
	<ExplosionConfig 
		cell_explosion_power="40"
		cell_explosion_damage_required="10"
		cell_explosion_radius_min="5"
	
		ray_energy="50000"
		>
	</ExplosionConfig>
    <Graphics
	  texture_file="data/materials_gfx/gunpowder.png"
	  color="ffb89e57" >
    </Graphics>
  </CellData>
```

*   **Explanation**: This defines "gunpowder". It's tagged as `[sand_other]`, `[corrodible]`, and `[alchemy]`. It's burnable, has a density, behaves like a liquid sand, and has an `autoignition_temperature`. Crucially, it includes an `<ExplosionConfig>` block, detailing its explosive properties like power, damage threshold, and radius. It also has a specific texture file.

## Reference

This file contains 5905 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/temp/materials.xml).

---