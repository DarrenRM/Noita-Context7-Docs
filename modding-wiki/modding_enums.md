---
title: Modding: Enums
source: https://noita.wiki.gg/wiki/Modding:_Enums
category: modding-wiki
---

# Modding: Enums

This documentation provides a comprehensive list of known enum values used within Noita's modding framework. Understanding these enums is crucial for accurately configuring components, defining entity behaviors, and implementing custom game effects, allowing for more precise and predictable mod development.

## Understanding Enums in Noita Modding

Enums (enumerations) are a way to represent a set of named integer constants. In Noita modding, they are frequently used in component configurations and Lua scripts to specify discrete options or states. This page serves as a reference for these predefined values, helping modders avoid errors and understand the available choices for various game mechanics.

## Enum Lists

### ARC\_TYPE

Used to define the type of arc.

-   MATERIAL
-   LIGHTNING

### AUDIO\_LAYER

Defines the audio layer for sound effects.

-   EFFECT\_GAME
-   EFFECT\_UI
-   AMBIENCE
-   MUSIC

### BIOME\_TYPE

Specifies the type of biome.

-   BIOME\_PROCEDURAL
-   BIOME\_BITMAP
-   BIOME\_WANG\_TILE

### DAMAGE\_TYPES

A comprehensive list of damage types recognized by the game.

-   NONE
-   DAMAGE\_MELEE
-   DAMAGE\_PROJECTILE
-   DAMAGE\_EXPLOSION
-   DAMAGE\_BITE
-   DAMAGE\_FIRE
-   DAMAGE\_MATERIAL
-   DAMAGE\_FALL
-   DAMAGE\_ELECTRICITY
-   DAMAGE\_DROWNING
-   DAMAGE\_PHYSICS\_BODY\_DAMAGED
-   DAMAGE\_DRILL
-   DAMAGE\_SLICE
-   DAMAGE\_ICE
-   DAMAGE\_HEALING
-   DAMAGE\_PHYSICS\_HIT
-   DAMAGE\_RADIOACTIVE
-   DAMAGE\_POISON
-   DAMAGE\_MATERIAL\_WITH\_FLASH
-   DAMAGE\_OVEREATING
-   DAMAGE\_CURSE
-   DAMAGE\_HOLY

### EDGE\_STYLE

Defines how edges are handled.

-   COLOR\_EDGE\_PIXELS
-   EVERYWHERE
-   CARDINAL\_DIRECTIONS
-   NORMAL\_BASED

### EXPLOSION\_TRIGGER\_TYPE

These values are used by `ExplosionComponent`'s `trigger` property to determine when the explosion defined on this component will trigger.

-   ON\_DEATH - Triggers when the entity housing `ExplosionComponent` is killed.
-   ON\_CREATE - Triggers the moment `ExplosionComponent` is added to the entity.
-   ON\_TIMER - Triggers according to the `timeout_frames` property in the `ExplosionComponent`.

### FOG\_OF\_WAR\_TYPE

Defines different types of fog of war behavior.

-   DEFAULT
-   HEAVY\_CLEAR\_AT\_PLAYER
-   HEAVY\_CLEAR\_WITH\_MAGIC
-   HEAVY\_NO\_CLEAR

### GAME\_EFFECT

These are the game effect names defined in Noita, often associated with status effects.

-   NONE
-   ELECTROCUTION - Used for [Circle of Thunder](https://noita.wiki.gg/wiki/Circle_of_Thunder), [Explosion of Thunder](https://noita.wiki.gg/wiki/Explosion_of_Thunder)
-   FROZEN - Used for [Frozen](https://noita.wiki.gg/wiki/Status_Effects#Frozen)
-   ON\_FIRE - Used for [On fire!](https://noita.wiki.gg/wiki/Status_Effects#On_fire!)
-   POISON - Used for [Poisoned](https://noita.wiki.gg/wiki/Status_Effects#Poisoned)
-   BERSERK - Used for [Berserk](https://noita.wiki.gg/wiki/Status_Effects#Berserk)
-   CHARM - Used for [Charmed](https://noita.wiki.gg/wiki/Status_Effects#Charmed)
-   POLYMORPH - Used for [Polymorph](https://noita.wiki.gg/wiki/Status_Effects#Polymorph)
-   POLYMORPH\_RANDOM - Used for [Chaos polymorph](https://noita.wiki.gg/wiki/Status_Effects#Chaos_polymorph)
-   BLINDNESS - Used for [Blinded](https://noita.wiki.gg/wiki/Status_Effects#Blinded)
-   TELEPATHY
-   TELEPORTATION - Used for [Teleportitis](https://noita.wiki.gg/wiki/Status_Effects#Teleportitis)
-   REGENERATION - Used for [Regeneration](https://noita.wiki.gg/wiki/Status_Effects#Regeneration)
-   LEVITATION - Used for [Faster levitation](https://noita.wiki.gg/wiki/Status_Effects#Faster_levitation)
-   MOVEMENT\_SLOWER - Used for [Clumsy movement](https://noita.wiki.gg/wiki/Status_Effects#Clumsy_movement)
-   FARTS - Used for [Gassy](https://noita.wiki.gg/wiki/Status_Effects#Gassy)
-   DRUNK - Used for [Drunk](https://noita.wiki.gg/wiki/Status_Effects#Drunk)
-   BREATH\_UNDERWATER - Used for [Breathless](https://noita.wiki.gg/wiki/Breathless)
-   RADIOACTIVE - Used for [Toxic](https://noita.wiki.gg/wiki/Status_Effects#Toxic)
-   WET - Used for [Wet](https://noita.wiki.gg/wiki/Status_Effects#Wet)
-   OILED - Used for [Oiled](https://noita.wiki.gg/wiki/Status_Effects#Oiled)
-   BLOODY - Used for [Bloody](https://noita.wiki.gg/wiki/Status_Effects#Bloody)
-   SLIMY - Used for [Slimy](https://noita.wiki.gg/wiki/Status_Effects#Slimy)
-   CRITICAL\_HIT\_BOOST - Used for [Critical Hit +](https://noita.wiki.gg/wiki/Critical_Hit_%2B)
-   CONFUSION - Used for [Confused](https://noita.wiki.gg/wiki/Status_Effects#Confused)
-   MELEE\_COUNTER - Used in [Parrying](https://noita.wiki.gg/wiki/Parrying)
-   WORM\_ATTRACTOR - Used for [Worm Attractor](https://noita.wiki.gg/wiki/Worm_Attractor) and [Worm food](https://noita.wiki.gg/wiki/Status_Effects#Worm_food)
-   WORM\_DETRACTOR
-   FOOD\_POISONING - Used for [Food poisoning](https://noita.wiki.gg/wiki/Status_Effects#Food_poisoning)
-   FRIEND\_THUNDERMAGE - Used for [Ukkoskivi](https://noita.wiki.gg/wiki/Ukkoskivi)
-   FRIEND\_FIREMAGE - Used for [Kiuaskivi](https://noita.wiki.gg/wiki/Kiuaskivi)
-   INTERNAL\_FIRE - Used for [Internal fire](https://noita.wiki.gg/wiki/Status_Effects#Internal_fire)
-   INTERNAL\_ICE - Used for [Chilly](https://noita.wiki.gg/wiki/Status_Effects#Chilly)
-   JARATE - Used for [Jarated](https://noita.wiki.gg/wiki/Status_Effects#Jarated)
-   KNOCKBACK - Used for [Knockback](https://noita.wiki.gg/wiki/Knockback)
-   KNOCKBACK\_IMMUNITY - Used for [No More Knockback](https://noita.wiki.gg/wiki/No_More_Knockback)
-   MOVEMENT\_SLOWER\_2X - Used for [Slower movement](https://noita.wiki.gg/wiki/Status_Effects#Slower_movement)
-   MOVEMENT\_FASTER - Used for [Faster Movement](https://noita.wiki.gg/wiki/Faster_Movement)
-   STAINS\_DROP\_FASTER - Used for [Repelling Cape](https://noita.wiki.gg/wiki/Repelling_Cape)
-   SAVING\_GRACE - Used for [Saving Grace](https://noita.wiki.gg/wiki/Saving_Grace)
-   DAMAGE\_MULTIPLIER - Used for [Glass Cannon](https://noita.wiki.gg/wiki/Glass_Cannon)
-   HEALING\_BLOOD - Used for [Vampirism](https://noita.wiki.gg/wiki/Vampirism)
-   RESPAWN - Used for [Extra Life](https://noita.wiki.gg/wiki/Extra_Life)
-   PROTECTION\_FIRE - Used for [Kiuaskivi](https://noita.wiki.gg/wiki/Kiuaskivi), [Fire Immunity](https://noita.wiki.gg/wiki/Fire_Immunity), [Freeze Field](https://noita.wiki.gg/wiki/Freeze_Field), [Oil Blood](https://noita.wiki.gg/wiki/Oil_Blood)
-   PROTECTION\_RADIOACTIVITY - Used for [Toxic Immunity](https://noita.wiki.gg/wiki/Toxic_Immunity)
-   PROTECTION\_EXPLOSION - Used for [Exploding Corpses](https://noita.wiki.gg/wiki/Exploding_Corpses) and [Explosion Immunity](https://noita.wiki.gg/wiki/Explosion_Immunity)
-   PROTECTION\_MELEE - Used for [Melee Immunity](https://noita.wiki.gg/wiki/Melee_Immunity)
-   PROTECTION\_ELECTRICITY - Used for [Electricity Immunity](https://noita.wiki.gg/wiki/Electricity_Immunity) and [Electricity](https://noita.wiki.gg/wiki/Electricity)
-   TELEPORTITIS - Used for [Teleportitis](https://noita.wiki.gg/wiki/Teleportitis)
-   STAINLESS\_ARMOUR - Used for [Stainless Armour](https://noita.wiki.gg/wiki/Stainless_Armour)
-   GLOBAL\_GORE - Used for [More Blood](https://noita.wiki.gg/wiki/More_Blood)
-   EDIT\_WANDS\_EVERYWHERE - Used for [Tinker with Wands Everywhere](https://noita.wiki.gg/wiki/Tinker_with_Wands_Everywhere)
-   EXPLODING\_CORPSE\_SHOTS - Used for [Exploding Corpses](https://noita.wiki.gg/wiki/Exploding_Corpses)
-   EXPLODING\_CORPSE
-   EXTRA\_MONEY - Used for [Greed](https://noita.wiki.gg/wiki/Greed)
-   EXTRA\_MONEY\_TRICK\_KILL - Used for [Trick Greed](https://noita.wiki.gg/wiki/Trick_Greed)
-   HOVER\_BOOST - Used for [Strong Levitation](https://noita.wiki.gg/wiki/Strong_Levitation)
-   PROJECTILE\_HOMING - Used for [Homing Shots](https://noita.wiki.gg/wiki/Homing_Shots)
-   ABILITY\_ACTIONS\_MATERIALIZED - Used for [Bombs Materialized](https://noita.wiki.gg/wiki/Bombs_Materialized)
-   NO\_DAMAGE\_FLASH
-   NO\_SLIME\_SLOWDOWN - Used for [Slime Blood](https://noita.wiki.gg/wiki/Slime_Blood)
-   MOVEMENT\_FASTER\_2X - Used for [Greased lightning](https://noita.wiki.gg/wiki/Status_Effects#Greased_lightning)
-   NO\_WAND\_EDITING - Used for [No Wand Tinkering](https://noita.wiki.gg/wiki/No_Wand_Tinkering)
-   LOW\_HP\_DAMAGE\_BOOST - Used for [Living on the Edge](https://noita.wiki.gg/wiki/Living_on_the_Edge)
-   FASTER\_LEVITATION - Used for [Faster levitation](https://noita.wiki.gg/wiki/Status_Effects#Faster_levitation) and [Faster Levitation](https://noita.wiki.gg/wiki/Faster_Levitation)
-   STUN\_PROTECTION\_ELECTRICITY
-   STUN\_PROTECTION\_FREEZE
-   IRON\_STOMACH - Used for [Iron Stomach](https://noita.wiki.gg/wiki/Iron_Stomach)
-   PROTECTION\_ALL - Used for [Protection from all](https://noita.wiki.gg/wiki/Status_Effects#Protection_from_all)
-   INVISIBILITY - Used for [Invisible](https://noita.wiki.gg/wiki/Status_Effects#Invisible) and [Invisibility](https://noita.wiki.gg/wiki/Invisibility)
-   REMOVE\_FOG\_OF\_WAR - Used for [All-Seeing Eye](https://noita.wiki.gg/wiki/All-Seeing_Eye)
-   MANA\_REGENERATION - Used for [Mana regeneration](https://noita.wiki.gg/wiki/Status_Effects#Mana_regeneration)
-   PROTECTION\_DURING\_TELEPORT
-   PROTECTION\_POLYMORPH - Used for [Polymorph immunity](https://noita.wiki.gg/wiki/Status_Effects#Polymorph_immunity)
-   PROTECTION\_FREEZE
-   FROZEN\_SPEED\_UP
-   UNSTABLE\_TELEPORTATION - Used for [Unstable teleportitis](https://noita.wiki.gg/wiki/Status_Effects#Unstable_teleportitis)
-   POLYMORPH\_UNSTABLE - Used for [Unstable polymorph](https://noita.wiki.gg/wiki/Status_Effects#Unstable_polymorph)
-   CUSTOM
-   ALLERGY\_RADIOACTIVE
-   RAINBOW\_FARTS - Used for [Rainbow farts](https://noita.wiki.gg/wiki/Status_Effects#Rainbow_farts)
-   WEAKNESS
-   PROTECTION\_FOOD\_POISONING
-   NO\_HEAL
-   PROTECTION\_EDGES
-   PROTECTION\_PROJECTILE
-   POLYMORPH\_CESSATION
-   \_LAST

### GENERAL\_NOISE

Defines various types of general noise algorithms.

-   IQNoise
-   DirtyPeeNoise
-   QemNoise
-   WhiteNoise
-   MixNoise
-   SimplexNoise
-   STB\_Perlin
-   FastBlockNoise
-   SimplexNoise1234

### HIT\_EFFECT

Specifies effects that occur upon hitting a target.

-   NONE
-   LOAD\_ENTITY
-   LOAD\_CHILD\_ENTITY
-   LOAD\_UNIQUE\_CHILD\_ENTITY
-   LOAD\_GAME\_EFFECT
-   LOAD\_UNIQUE\_GAME\_EFFECT
-   CONVERT\_RAGDOLL\_TO\_MATERIAL
-   CRITICAL\_HIT\_BOOST
-   DAMAGE\_BOOST
-   SWAPPER

### INVENTORY\_KIND

Defines the type of inventory.

-   QUICK
-   FULL

### JOINT\_TYPE

Specifies the type of physics joint.

-   REVOLUTE\_JOINT
-   WELD\_JOINT
-   REVOLUTE\_JOINT\_ATTACH\_TO\_NEARBY\_SURFACE
-   WELD\_JOINT\_ATTACH\_TO\_NEARBY\_SURFACE

### LUA\_VM\_TYPE

Determines how Lua virtual machines are managed.

-   SHARED\_BY\_MANY\_COMPONENTS
-   CREATE\_NEW\_EVERY\_EXECUTION
-   ONE\_PER\_COMPONENT\_INSTANCE

### MATERIALAUDIO\_TYPE

Defines the audio type associated with materials.

-   NONE
-   LAVA
-   MAGICAL

### MATERIALBREAKAUDIO\_TYPE

Defines the audio type for material breaking sounds.

-   NONE
-   WOOD
-   CHAIN

### MOVETOSURFACE\_TYPE

Specifies how an entity moves to a surface.

-   ENTITY
-   VERLET\_ROPE\_ONE\_JOINT
-   VERLET\_ROPE\_TWO\_JOINTS

### NOISE\_TYPE

Defines different types of noise algorithms.

-   IQ2\_SIMPLEX1234
-   IQ\_SIMPLEX
-   SIN\_CAPPED\_EVERYTHING
-   SIN\_CAPPED\_SIMPLEX

### PARTICLE\_EMITTER\_CUSTOM\_STYLE

Defines custom styles for particle emitters.

-   NONE
-   FIRE

### PROJECTILE\_TYPE

Specifies the type of projectile.

-   PROJECTILE
-   LIGHTNING
-   VERLET
-   MATERIAL\_PARTICLE

### RAGDOLL\_FX

Used in `ProjectileComponent.ragdoll_fx_on_collision`, among other places. Defines ragdoll effects.

-   NONE
-   NORMAL
-   BLOOD\_EXPLOSION
-   BLOOD\_SPRAY
-   FROZEN
-   CONVERT\_TO\_MATERIAL
-   CUSTOM\_RAGDOLL\_ENTITY
-   DISINTEGRATED
-   NO\_RAGDOLL\_FILE
-   PLAYER\_RAGDOLL\_CAMERA

### VERLET\_TYPE

Defines the type of Verlet physics simulation.

-   CHAIN
-   CLOTH
-   BLOB