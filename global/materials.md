---
title: materials
category: data
source: https://github.com/NathanSnail/noitadata/tree/main/data/materials.xml
---

# materials

The `materials.xml` file is a fundamental data file in Noita that defines the properties and behaviors of every material and substance within the game world. It dictates how these materials interact with each other, with the player, and with the environment. This includes aspects like their physical state (solid, liquid, gas), their flammability, their temperature, their visual appearance, their sound effects, and any special effects or status effects they might impart. Essentially, this file is the blueprint for the game's dynamic simulation of its world.

## File Structure

The `materials.xml` file is structured as an XML document. The root element is `<Materials>`, which contains numerous `<CellData>` and `<CellDataChild>` elements.

*   **`<Materials>`**: The top-level container for all material definitions.
*   **`<CellData>`**: Defines a unique material. It contains various attributes that describe the material's properties.
    *   **`name`**: A unique internal identifier for the material (e.g., "air", "fire", "rock_static").
    *   **`ui_name`**: A localization key for the material's name displayed in the user interface (e.g., "$mat_air", "$mat_fire").
    *   **`tags`**: A space-separated list of keywords enclosed in square brackets (e.g., `[fire]`, `[static]`, `[liquid]`). These tags categorize materials and influence their behavior and interactions.
    *   **`cell_type`**: Specifies the fundamental physical state of the material (e.g., "fire", "liquid", "gas", "solid").
    *   **`wang_color`**: A hexadecimal color code used for certain graphical or internal representations.
    *   **Other Attributes**: A wide array of attributes define specific properties like `density`, `burnable`, `hp` (hit points), `temperature_of_fire`, `liquid_gravity`, `generates_smoke`, `requires_oxygen`, `gfx_glow`, `audio_physics_material_event`, `status_effects`, and more.
*   **`<CellDataChild>`**: This element is used for defining materials that inherit properties from a parent material.
    *   **`_parent`**: Specifies the `name` of the parent `<CellData>` or `<CellDataChild>` element from which properties are inherited.
    *   **`_inherit_reactions`**: A boolean attribute (often `1`) indicating whether reactions defined in the parent should be inherited.
    *   It can override or add new attributes and child elements to the inherited properties.
*   **Child Elements**: Within `<CellData>` and `<CellDataChild>`, other XML elements can be nested to define more complex properties:
    *   **`<Graphics>`**: Contains sub-elements like `<EdgeGraphics>` and `<Image>` to define visual aspects, textures, and edge rendering.
    *   **`<EdgeGraphics>`**: Defines how the edges of a material are rendered, often with specific image files.
    *   **`<Image>`**: Specifies image files used for graphics, potentially with rotation options.
    *   **`<ParticleEffect>`**: Defines particle effects associated with the material, such as when it's spawned or interacts.
    *   **`<StatusEffects>`**: Contains `<Ingestion>` elements which, in turn, define `<StatusEffect>` types and amounts applied when the material is consumed.

## Key Patterns

Several important patterns and organizational principles are evident in the `materials.xml` file:

*   **Tag-Based Categorization**: The `tags` attribute is crucial for grouping materials and defining their fundamental characteristics. Common tags include:
    *   **Physical State**: `[static]`, `[liquid]`, `[gas]`, `[box2d]` (for physics-enabled solids).
    *   **Elemental/Chemical**: `[fire]`, `[water]`, `[acid]`, `[lava]`, `[slime]`, `[plant]`.
    *   **Interaction Properties**: `[corrodible]`, `[meltable]`, `[meltable_to_lava]`, `[molten]`, `[soluble]`, `[evaporable]`, `[frozen]`, `[radioactive]`.
    *   **Gameplay Mechanics**: `[alchemy]`, `[requires_air]`, `[requires_water]`, `[grows_grass]`, `[NO_FUNGAL_SHIFT]` (for specific game mechanics).
    *   **Material Types**: `[earth]`, `[meat]`, `[blood]`.
*   **Inheritance for Variants**: The `<CellDataChild>` element with the `_parent` attribute is extensively used to create variations of existing materials. For example, different types of "meat" or "rock" can inherit base properties and then have specific status effects or visual differences.
*   **Order of Definition**: Comments in the file suggest a general ordering of material definitions, starting with fundamental elements like "air" and "fire," moving through static and dynamic solids, liquids, gases, and then special or "hax" materials. This order might be significant for internal processing or load times.
*   **Comments for Explanation**: The file is heavily commented, providing explanations for tags, attribute meanings, and intended behaviors. These comments are invaluable for understanding the purpose of various definitions.
*   **Material Interactions**: Attributes like `burnable`, `density`, `liquid_gravity`, `on_fire`, `requires_oxygen`, and `meltable_to_X` define how materials interact with each other and the environment.
*   **Visual and Audio Definitions**: `<Graphics>` and related elements, along with `audio_physics_material_event` and similar attributes, link materials to their visual representations and sound effects.
*   **Status Effects**: The `<StatusEffects>` and `<Ingestion>` structures are used to define how consuming a material affects the player or other entities.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`air`**:
    ```xml
      <CellData
    	name="air"
      	ui_name="$mat_air"
    	wang_color="ff000042" >
      </CellData>
    ```
    This is a basic definition for "air." It has a `name`, a `ui_name` for display, and a `wang_color`. It lacks many specific attributes, indicating it's a fundamental, simple material.

2.  **`fire`**:
    ```xml
      <CellData
    	name="fire"
      	ui_name="$mat_fire"
      	tags="[fire],[hot]"
    	burnable="0"
    	density="1"
    	cell_type="fire"
    	wang_color="7fFF6060"
    	generates_smoke="0"
    	liquid_gravity="0.5"
    	liquid_sand="0"
    	on_fire="1"
    	requires_oxygen="1"
    	temperature_of_fire="100"
    	gfx_glow="255"
      >
      </CellData>
    ```
    This defines "fire." It's tagged as `[fire]` and `[hot]`, has `cell_type="fire"`, and possesses attributes like `on_fire="1"` (meaning it is on fire itself, perhaps paradoxically), `requires_oxygen="1"`, and `temperature_of_fire="100"`. It also has graphical properties like `gfx_glow`.

3.  **`rock_static_trip_secret`**:
    ```xml
      <CellDataChild
      	_parent="rock_static"
      	_inherit_reactions="1"
    	tags="[static],[alchemy],[solid],[earth]"
      	name="rock_static_trip_secret"
    	ui_name="$mat_rock_static"
    	wang_color="ff0abba4"
    	hp="160000"
    	audio_physics_material_event="rock"
    	audio_physics_material_wall="rock"
    	audio_physics_material_solid="rock"
    	>
    	<Graphics
    		texture_file="data/materials_gfx/rock.png"
    		color="ff313b36"
    		pixel_all_around="ff313b36"
    		>
    		<Edge>
    			<EdgeGraphics
    				color="ff233112"
    			>
    				<Images>
    					<Image
    						allow_random_rotation="1"
    						filename="data/materials_gfx/edge_files/edge_rock_1.png"
    					/>
    					<!-- ... other edge images ... -->
    				</Images>
    			</EdgeGraphics>
    		</Edge>
    	</Graphics>
      </CellDataChild>
    ```
    This entry demonstrates inheritance. `rock_static_trip_secret` inherits from `rock_static`. It has tags like `[static]`, `[alchemy]`, `[solid]`, and `[earth]`. It defines specific graphical elements, including multiple edge graphics files for visual variation, and sets a high `hp` value.

4.  **`cloud_radioactive`**:
    ```xml
      <CellData
    	name="cloud_radioactive"
    	ui_name="$mat_cloud_radioactive"
      	tags="[liquid],[radioactive],[impure],[liquid_common]"
    	burnable="0"
    	density="1"
    	cell_type="liquid"
    	wang_color="1101FF34"
    	gfx_glow="130"
    	generates_smoke="0"
    	liquid_gravity="0"
    	liquid_sand="0"
    	liquid_stains="2"
    	liquid_stains_self="1"
    	on_fire="0"
    	>
    	<ParticleEffect
    		vel.y="-40"
    		vel_random.min_y="-20.21"
    		vel_random.max_y="-2.861"
    		vel_random.min_x="-6.667"
    		vel_random.max_x="6.667"
    		lifetime.min="0.3238"
    		lifetime.max="9.3238"
    		gravity.y="-100"
    		render_on_grid="1"
    		airflow_force="10"
    		airflow_scale="6.857"
    		draw_as_long="0"
    		friction="1.352"
    		probability="0.0343"
    	>
    	</ParticleEffect>
    	<StatusEffects>
    		<Ingestion>
    			<StatusEffect type="FOOD_POISONING" amount="0.2" />
    		</Ingestion>
    	</StatusEffects>
      </CellData>
    ```
    This defines a "radioactive cloud." It's tagged as `[liquid]` and `[radioactive]`. It has a `cell_type="liquid"` but `liquid_gravity="0"`, suggesting it might behave differently from typical liquids. It includes a `ParticleEffect` definition for visual effects and a `StatusEffects` entry for `FOOD_POISONING` upon ingestion.

## Reference

This file contains 17030 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/materials.xml).

---