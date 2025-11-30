---
title: utilities
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/lib/utilities.lua
---

# utilities

The `utilities.lua` file is a crucial library script within the Noita data files, providing a collection of helper functions that streamline common programming tasks. These functions are designed to simplify interactions with the game's entity-component system, perform mathematical operations, handle random number generation, and manipulate data structures. By offering reusable code snippets, this file promotes efficiency and consistency in other scripts that rely on its functionality.

## File Structure

The file primarily consists of Lua functions. There are no explicit XML tags or attributes in the sampled content. The structure is a straightforward collection of function definitions, often separated by comment lines (`----------------------------------------------------------------------------------------`).

Key patterns observed in the function definitions include:

*   **Function Definitions:** Standard Lua `function function_name(parameters) ... end` syntax.
*   **Parameter Passing:** Functions accept various data types as parameters, including numbers, strings, tables, and entity IDs.
*   **Return Values:** Functions can return single values, multiple values (Lua's multiple return capability), or `nil`.
*   **Conditional Logic:** `if`, `elseif`, and `else` statements are frequently used for decision-making.
*   **Loops:** `for` loops are used for iterating over collections or performing actions a specific number of times.
*   **Table Manipulation:** Functions operate on Lua tables, accessing elements by index (`t[i]`) or key (`t[key]`).
*   **Game API Interaction:** Many functions interact with Noita's internal game API, such as `GetUpdatedEntityID()`, `EntityGetComponent()`, `ComponentSetValue()`, `EntityLoad()`, and `EntityAddComponent()`.

## Key Patterns

Several recurring patterns and categories of utility functions are evident in the samples:

*   **Random Number Generation:** A suite of functions for generating random numbers, including basic random floats, random integers within a range, and more complex weighted random selections from tables. These often utilize a procedural random generator (`ProceduralRandomf`, `ProceduralRandomi`).
    *   `rand(low, high)`: Generates a random float between `low` and `high`.
    *   `random_from_array(varray)`: Selects a random element from a given array.
    *   `pick_random_from_table_weighted(rnd, t)`: Selects an item from a table based on defined probabilities.

*   **Entity and Component Manipulation:** Functions designed to interact with Noita's entity-component system, simplifying common operations like getting, setting, and editing component values.
    *   `for_comps(name, do_what)`: Iterates over all components of a specific type attached to the current entity.
    *   `edit_all_components(entity_id, type_name, do_what)`: Applies a modification function to all components of a given type on an entity.
    *   `edit_nth_component(entity_id, type_name, n, do_what)`: Applies a modification function to a specific (n-th) component of a given type.
    *   `component_get_value(...)`: (Signature shown, implementation not in sample) Likely retrieves a specific value from a component.

*   **Vector/Coordinate Operations:** Functions for performing mathematical operations on 2D vectors or coordinates.
    *   `vec_sub(x1, y1, x2, y2)`: Subtracts one vector from another.
    *   `vec_mult(x, y, multiplier)`: Multiplies a vector by a scalar.
    *   `vec_div(x, y, divider)`: Divides a vector by a scalar.
    *   `vec_scale(x1, y1, x2, y2)`: Scales one vector by another (element-wise multiplication).
    *   `vec_equals(x1, y1, x2, y2)`: Checks if two vectors are equal.
    *   `vec_normalize(x, y)`: Returns a unit vector in the same direction.

*   **String and Data Validation:** Basic utility functions for checking string emptiness or entity validity.
    *   `string_isempty(s)`: Checks if a string is `nil` or empty.
    *   `is_valid_entity(entity_id)`: (Implied by usage) Likely checks if an entity ID refers to a valid, existing entity.

*   **Entity Loading and Component Addition:** Functions that handle loading entities from files and adding specific components.
    *   `load_verlet_rope_with_two_joints(...)`: A specialized function for loading and configuring entities that represent Verlet ropes with two joints.
    *   `load_verlet_rope_with_one_joint(...)`: Similar to the above, but for ropes with a single joint.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`random_next( rnd, min, max )`**
    This function is part of a procedural random number generation system. It takes a random state object (`rnd`) and a range (`min`, `max`) and returns a float within that range. Crucially, it also increments the `y` component of the `rnd` state, ensuring that subsequent calls with the same `rnd.x` will produce different, yet procedurally determined, random numbers. This is useful for generating sequences of random values that are reproducible if the initial `rnd` state is the same.

    ```lua
    function random_next( rnd, min, max )
        local result = ProceduralRandomf( rnd.x, rnd.y, min, max )
        rnd.y = rnd.y + 1
        return result
    end
    ```

2.  **`edit_all_components( entity_id, type_name, do_what )`**
    This function provides a powerful way to modify multiple components of the same type on a given entity. It first retrieves all components of `type_name` attached to `entity_id`. Then, for each component, it calls the provided `do_what` function. The `do_what` function can then modify the component directly or populate a `modified_vars` table, which is then used to update the component's values using `ComponentSetValue`. This pattern is common for batch operations on entity properties.

    ```lua
    function edit_all_components( entity_id, type_name, do_what )
        if not is_valid_entity( entity_id ) then
            return
        end

        local comps = EntityGetComponent( entity_id, type_name )
        if comps ~= nil then
            for i,comp in ipairs(comps) do
                local modified_vars = { }
                do_what( comp, modified_vars )
                for key,value in pairs( modified_vars ) do
                    ComponentSetValue( comp, key, to_string(value) )
                end
            end
        end
    end
    ```

3.  **`vec_normalize(x, y)`**
    This function takes a 2D vector (represented by `x` and `y` coordinates) and returns a normalized version of it. Normalization means scaling the vector so that its magnitude (length) becomes 1, while preserving its direction. It first calculates the magnitude using `get_magnitude` (presumably another utility function not shown in this sample) and then divides each component by the magnitude. It includes a check to prevent division by zero if the magnitude is 0.

    ```lua
    function vec_normalize(x, y)
        local m = get_magnitude(x, y)
        if m == 0 then return 0,0 end
        x = x / m
        y = y / m
        return x,y
    end
    ```

## Reference

This file contains 1082 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/lib/utilities.lua).

---