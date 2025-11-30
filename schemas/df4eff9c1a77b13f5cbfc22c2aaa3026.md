---
title: df4eff9c1a77b13f5cbfc22c2aaa3026
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/df4eff9c1a77b13f5cbfc22c2aaa3026.xml
---

# df4eff9c1a77b13f5cbfc22c2aaa3026

This XML file defines the structure and properties of various game components used in Noita. These components dictate the behavior, appearance, and interactions of entities within the game world. Essentially, this file acts as a blueprint for how different game elements are constructed and function, providing data that the game engine reads to instantiate and manage objects like enemies, spells, environmental elements, and more. Understanding this schema is crucial for anyone looking to modify or deeply analyze Noita's game mechanics.

## File Structure

The file is structured as a collection of `<Component>` elements, each representing a distinct type of game logic or data. The root element is `<Schema>`, which contains these components.

Each `<Component>` element has a `component_name` attribute that uniquely identifies the type of component it defines. Inside each `<Component>`, there are multiple `<Var>` elements.

Each `<Var>` element represents a specific variable or property associated with that component. These `<Var>` elements have the following key attributes:

*   **`name`**: The name of the variable.
*   **`size`**: The size of the variable in bytes. This often hints at the data type.
*   **`type`**: The data type of the variable. This can range from primitive types like `int`, `float`, `bool` to more complex C++ types like `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` (string) or `class ceng::math::CVector2<float>` (a 2D vector of floats).

The structure is hierarchical: `<Schema>` contains `<Component>`s, and `<Component>`s contain `<Var>`s.

## Key Patterns

*   **Component-Based Design**: The entire file is organized around distinct game components, each encapsulating a specific set of functionalities or data. This is a common pattern in game development for modularity.
*   **Variable Definitions**: Each component's properties are defined by `<Var>` tags, specifying their names, sizes, and types. This provides a clear schema for how data is stored and interpreted.
*   **Data Type Variety**: The file showcases a range of data types, from simple booleans and integers to complex C++ class representations for strings, vectors, and mathematical structures like 2D vectors.
*   **AI and Behavior**: Components like `AIAttackComponent` and `AIComponent` suggest a focus on defining enemy AI, attack patterns, movement, and decision-making.
*   **Physical Properties**: Components like `PhysicsImageShapeComponent` and `AreaDamageComponent` indicate definitions related to physics, collision, and damage application.
*   **Visual and Transformational Data**: Components like `InheritTransformComponent` and `ArcComponent` point towards definitions for how entities are positioned, transformed, and visually represented.
*   **Ingestion and Material Handling**: `IngestionComponent` suggests mechanics related to consuming or interacting with different materials in the game world.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`AIAttackComponent`**:
    ```xml
    <Component component_name="AIAttackComponent" >
      <Var name="use_probability" size="4" type="int" >
      </Var>
      <Var name="min_distance" size="4" type="float" >
      </Var>
      <Var name="max_distance" size="4" type="float" >
      </Var>
      <Var name="angular_range_deg" size="4" type="float" >
      </Var>
      <Var name="animation_name" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      </Component>
    ```
    This component defines parameters for an AI's attack capabilities. It includes variables for attack probability, range (`min_distance`, `max_distance`), aiming (`angular_range_deg`), associated animations (`animation_name`), and details about ranged attacks, such as the entity file to spawn (`attack_ranged_entity_file`).

2.  **`ArcComponent`**:
    ```xml
    <Component component_name="ArcComponent" >
      <Var name="type" size="4" type="enum ARC_TYPE::Enum" >
      </Var>
      <Var name="material" size="4" type="int" >
      </Var>
      <Var name="lifetime" size="4" type="int" >
      </Var>
    </Component>
    ```
    This component likely defines visual or functional arcs, perhaps for spells or environmental effects. It specifies the `type` of arc (likely an enumeration), the `material` it's composed of, and its `lifetime` in frames.

3.  **`IngestionComponent`**:
    ```xml
    <Component component_name="IngestionComponent" >
      <Var name="ingested_materials" size="12" type="class std::vector<double,class std::allocator<double> >" >
      </Var>
      <Var name="inhaled_materials" size="12" type="class std::vector<double,class std::allocator<double> >" >
      </Var>
      <Var name="ingestible_materials" size="12" type="class std::vector<unsigned char,class std::allocator<unsigned char> >" >
      </Var>
      <Var name="inhalable_materials" size="12" type="class std::vector<unsigned char,class std::allocator<unsigned char> >" >
      </Var>
    </Component>
    ```
    This component deals with how an entity interacts with different materials. It lists materials that can be `ingested_materials`, `inhaled_materials`, and those that are `ingestible_materials` or `inhalable_materials`. The use of `double` and `unsigned char` suggests these might be material IDs or properties.

## Reference

This file contains 5964 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/df4eff9c1a77b13f5cbfc22c2aaa3026.xml).

---