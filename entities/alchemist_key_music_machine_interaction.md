---
title: Alchemist Key Music Machine Interaction
category: entities
---

# Alchemist Key Music Machine Interaction

This script handles the interaction between the Alchemist's Key and music machines within the game. It tracks how many music machines have been activated and updates the key's description and particle effects accordingly.

## Core Functionality

The script identifies nearby music machines and checks their activation status. When a music machine is activated for the first time, it increments a counter stored within the Alchemist's Key. This counter influences the key's visual appearance and in-game messages.

## Key Components and Logic

### Entity Initialization

*   **`entity_id`**: Retrieves the unique identifier for the entity running this script.
*   **`x`, `y`**: Gets the current position of the entity.
*   **`radius`**: Defines the search radius (96 units) for nearby music machines.
*   **`status`**: An integer variable to track the number of activated music machines. Initialized to 0.
*   **`scomp`**: A variable to store the `VariableStorageComponent` if found.

### Variable Storage Component Handling

The script searches for a `VariableStorageComponent` attached to the entity. If found, it specifically looks for a variable named `"music_machine"`.

*   **`name == "music_machine"`**: Identifies the target variable.
*   **`status = ComponentGetValue2( v, "value_int" )`**: Reads the current activation count from the variable.
*   **`scomp = v`**: Stores the component itself for later modification.

### Music Machine Detection and Interaction

The script searches for entities with the tag `"musicmachine"` within the defined radius.

*   **`targets = EntityGetInRadiusWithTag( x, y, radius, "musicmachine" )`**: Gets a list of nearby music machine entities.
*   **`mm = { "musicmachine1", "musicmachine2", "musicmachine3", "musicmachine4" }`**: A list of specific tags used to identify individual music machines.

The script iterates through each detected music machine:

*   **`EntityGetTags( v )`**: Retrieves the tags associated with the music machine.
*   **Tag Matching**: It checks if the music machine's tags contain any of the predefined `"mm"` tags.
*   **Flag Checks**:
    *   **`GameHasFlagRun( mm_flag )`**: Checks if the specific music machine has been activated.
    *   **`GameHasFlagRun( mm_flag .. "_done" ) == false`**: Ensures this is the first time this specific music machine is being processed in this run.
*   **Activation Logic**:
    *   **`GameAddFlagRun( mm_flag .. "_done" )`**: Marks the music machine as processed.
    *   **`status = status + 1`**: Increments the activation counter.
    *   **`desc_text = "$itemdesc_alchemy_key_musicbox_" .. tostring( math.min( math.max( status, 1 ), 4 ) )`**: Dynamically generates the description text for the Alchemist's Key based on the `status`. The `math.min` and `math.max` ensure the status value stays within the range of 1 to 4 for description lookup.

### Visual and Informational Feedback

Based on the `status` of activated music machines, the script provides visual and textual feedback.

*   **`edit_component( entity_id, "ItemComponent", function(comp,vars) ... end)`**: Modifies the `ItemComponent` of the Alchemist's Key.
    *   **`ComponentSetValue2( comp, "ui_description", desc_text )`**: Updates the key's UI description.
*   **Particle Effects**:
    *   **`if ( status < 4 ) then ... else ... end`**: Conditional loading of particle effects.
        *   **`EntityLoadToEntity( "data/entities/animals/boss_alchemist/key_particles_first_alt.xml", entity_id )`**: Loads particles for intermediate activation stages.
        *   **`EntityLoadToEntity( "data/entities/animals/boss_alchemist/key_particles_second_alt.xml", entity_id )`**: Loads particles for the final activation stage.
*   **Important Game Messages**:
    *   **`GamePrintImportant( "$log_alchemist_key_alt_first", "$logdesc_alchemist_key_alt_first" )`**: Displays a message for intermediate activations.
    *   **`GamePrintImportant( "$log_alchemist_key_alt_second", "$logdesc_alchemist_key_alt_second" )`**: Displays a message for the final activation.

### Updating Variable Storage

Finally, the script updates the `VariableStorageComponent` with the new `status` value.

*   **`if ( scomp ~= nil ) and ( scomp ~= 0 ) then ... end`**: Ensures the component was found before attempting to modify it.
*   **`ComponentSetValue2( scomp, "value_int", status )`**: Saves the updated activation count.