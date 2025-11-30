---
title: Lua Function Documentation Generator
category: scripts
---

# Lua Function Documentation Generator

This script is a utility for generating HTML documentation from Lua function signatures. It parses a list of function signatures, extracts their names, parameters, return values, and descriptions, and then formats this information into a readable HTML table.

## Purpose

The primary goal of this script is to automate the creation of documentation for Lua functions used within the Noita modding environment. This makes it easier for modders to understand and utilize available functions.

## Key Components

### `split_and_classify(s)`

This function takes a single raw function signature string and breaks it down into its constituent parts: function name, parameters, return values, and description.

**Input:**
A string representing a Lua function signature, e.g., `FunctionName( param1:type = default, param2:type ) -> return1:type, return2:type [Description of the function]`

**Output:**
A table containing the parsed components:
*   `func.name`: The name of the function.
*   `func.parameters`: A string containing all parameters.
*   `return_values`: A string containing all return values.
*   `description`: A string containing the function's description.

### `parse(function_signatures)`

This function iterates over a list of raw function signature strings and applies `split_and_classify` to each one.

**Input:**
*   `function_signatures`: A table where each element is a raw function signature string.

**Output:**
A table where each element is the result of `split_and_classify` for a given signature.

### `generate_html(parsed)`

This function takes the parsed function data and constructs an HTML string.

**Input:**
*   `parsed`: The output table from the `parse` function.

**Output:**
A complete HTML document string, formatted as a table, with each row representing a function and its details.

## HTML Styling

The script includes inline CSS (`html_style`) to format the generated HTML table for readability. Key styles include:

*   **Body:** Monospace font, large font size, padding.
*   **Table:** Fixed layout, borders, collapse borders, left alignment, top vertical alignment.
*   **Hover Effect:** Rows highlight on mouse hover.
*   **Class Styles:**
    *   `.function`: Bold black text for function names.
    *   `.field_name`: Normal black text for parameter and return value names.
    *   `.description`: Normal sans-serif text for descriptions.

## Example Usage (Conceptual)

```lua
-- Assume 'in_function_signatures' is a table populated with raw function signature strings
-- Example:
-- in_function_signatures = {
--     "my_function( arg1:number, arg2:string ) -> result:boolean [This is a sample function]",
--     "another_func( ) -> nil [A function with no arguments or returns]"
-- }

local parsed_data = parse(in_function_signatures)
local documentation_html = generate_html(parsed_data)

-- The 'documentation_html' variable now holds the generated HTML string.
-- This string could then be written to a file or displayed.
```