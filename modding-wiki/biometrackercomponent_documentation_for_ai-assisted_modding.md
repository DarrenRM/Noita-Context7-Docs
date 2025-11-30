---
title: BiomeTrackerComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:BiomeTrackerComponent
category: modding-wiki
---

# BiomeTrackerComponent Documentation

This documentation covers the `BiomeTrackerComponent` in Noita, a crucial component for managing and tracking biome information within the game. Understanding this component is essential for modders who wish to create custom biomes, influence player progression based on biome discovery, or implement biome-specific mechanics.

## Overview

The `BiomeTrackerComponent` is responsible for keeping track of which biomes the player has visited or discovered. This information can then be used by other game systems or mods to trigger events, unlock content, or modify gameplay based on the player's progress through the game's world.

## Component Properties

The `BiomeTrackerComponent` has several properties that can be configured in the game's XML files. These properties define how the component functions and what data it tracks.

### `biome_map`

This property defines the mapping between biome IDs and their corresponding display names or internal identifiers. This is crucial for the game to correctly interpret and report biome information.

**Example XML:**

```xml
<BiomeTrackerComponent
    biome_map="data/biome_mapping.xml"
    ...
/>
```

The `biome_mapping.xml` file would contain entries like this:

```xml
<BiomeMapping>
    <Biome id="forest" name="The Forest" />
    <Biome id="cave" name="The Caves" />
    <Biome id="snow" name="The Snowlands" />
    <Biome id="hell" name="The Underworld" />
    <Biome id="temple" name="The Temple" />
    <Biome id="coal_mine" name="Coal Mines" />
    <Biome id="fungi_caverns" name="Fungi Caverns" />
    <Biome id="wandering_haunted_ruins" name="Wandering Haunted Ruins" />
    <Biome id="ancient_temple" name="Ancient Temple" />
    <Biome id="lake" name="The Lake" />
    <Biome id="wasteland" name="The Wasteland" />
    <Biome id="cursed_caves" name="Cursed Caves" />
    <Biome id="crystal_cave" name="Crystal Cave" />
    <Biome id="coward_cave" name="Coward Cave" />
    <Biome id="unholy_catacombs" name="Unholy Catacombs" />
    <Biome id="skylands" name="Skylands" />
    <Biome id="dream" name="The Dream" />
    <Biome id="hell_2" name="The Underworld II" />
    <Biome id="hell_3" name="The Underworld III" />
    <Biome id="hell_4" name="The Underworld IV" />
    <Biome id="hell_5" name="The Underworld V" />
    <Biome id="hell_6" name="The Underworld VI" />
    <Biome id="hell_7" name="The Underworld VII" />
    <Biome id="hell_8" name="The Underworld VIII" />
    <Biome id="hell_9" name="The Underworld IX" />
    <Biome id="hell_10" name="The Underworld X" />
    <Biome id="hell_11" name="The Underworld XI" />
    <Biome id="hell_12" name="The Underworld XII" />
    <Biome id="hell_13" name="The Underworld XIII" />
    <Biome id="hell_14" name="The Underworld XIV" />
    <Biome id="hell_15" name="The Underworld XV" />
    <Biome id="hell_16" name="The Underworld XVI" />
    <Biome id="hell_17" name="The Underworld XVII" />
    <Biome id="hell_18" name="The Underworld XVIII" />
    <Biome id="hell_19" name="The Underworld XIX" />
    <Biome id="hell_20" name="The Underworld XX" />
    <Biome id="hell_21" name="The Underworld XXI" />
    <Biome id="hell_22" name="The Underworld XXII" />
    <Biome id="hell_23" name="The Underworld XXIII" />
    <Biome id="hell_24" name="The Underworld XXIV" />
    <Biome id="hell_25" name="The Underworld XXV" />
    <Biome id="hell_26" name="The Underworld XXVI" />
    <Biome id="hell_27" name="The Underworld XXVII" />
    <Biome id="hell_28" name="The Underworld XXVIII" />
    <Biome id="hell_29" name="The Underworld XXIX" />
    <Biome id="hell_30" name="The Underworld XXX" />
    <Biome id="hell_31" name="The Underworld XXXI" />
    <Biome id="hell_32" name="The Underworld XXXII" />
    <Biome id="hell_33" name="The Underworld XXXIII" />
    <Biome id="hell_34" name="The Underworld XXXIV" />
    <Biome id="hell_35" name="The Underworld XXXV" />
    <Biome id="hell_36" name="The Underworld XXXVI" />
    <Biome id="hell_37" name="The Underworld XXXVII" />
    <Biome id="hell_38" name="The Underworld XXXVIII" />
    <Biome id="hell_39" name="The Underworld XXXIX" />
    <Biome id="hell_40" name="The Underworld XL" />
    <Biome id="hell_41" name="The Underworld XLI" />
    <Biome id="hell_42" name="The Underworld XLII" />
    <Biome id="hell_43" name="The Underworld XLIII" />
    <Biome id="hell_44" name="The Underworld XLIV" />
    <Biome id="hell_45" name="The Underworld XLV" />
    <Biome id="hell_46" name="The Underworld XLVI" />
    <Biome id="hell_47" name="The Underworld XLVII" />
    <Biome id="hell_48" name="The Underworld XLVIII" />
    <Biome id="hell_49" name="The Underworld XLIX" />
    <Biome id="hell_50" name="The Underworld L" />
    <Biome id="hell_51" name="The Underworld LI" />
    <Biome id="hell_52" name="The Underworld LII" />
    <Biome id="hell_53" name="The Underworld LIII" />
    <Biome id="hell_54" name="The Underworld LIV" />
    <Biome id="hell_55" name="The Underworld LV" />
    <Biome id="hell_56" name="The Underworld LVI" />
    <Biome id="hell_57" name="The Underworld LVII" />
    <Biome id="hell_58" name="The Underworld LVIII" />
    <Biome id="hell_59" name="The Underworld LIX" />
    <Biome id="hell_60" name="The Underworld LX" />
    <Biome id="hell_61" name="The Underworld LXI" />
    <Biome id="hell_62" name="The Underworld LXII" />
    <Biome id="hell_63" name="The Underworld LXIII" />
    <Biome id="hell_64" name="The Underworld LXIV" />
    <Biome id="hell_65" name="The Underworld LXV" />
    <Biome id="hell_66" name="The Underworld LXVI" />
    <Biome id="hell_67" name="The Underworld LXVII" />
    <Biome id="hell_68" name="The Underworld LXVIII" />
    <Biome id="hell_69" name="The Underworld LXIX" />
    <Biome id="hell_70" name="The Underworld LXX" />
    <Biome id="hell_71" name="The Underworld LXXI" />
    <Biome id="hell_72" name="The Underworld LXXII" />
    <Biome id="hell_73" name="The Underworld LXXIII" />
    <Biome id="hell_74" name="The Underworld LXXIV" />
    <Biome id="hell_75" name="The Underworld LXXV" />
    <Biome id="hell_76" name="The Underworld LXXVI" />
    <Biome id="hell_77" name="The Underworld LXXVII" />
    <Biome id="hell_78" name="The Underworld LXXVIII" />
    <Biome id="hell_79" name="The Underworld LXXIX" />
    <Biome id="hell_80" name="The Underworld LXXX" />
    <Biome id="hell_81" name="The Underworld LXXXI" />
    <Biome id="hell_82" name="The Underworld LXXXII" />
    <Biome id="hell_83" name="The Underworld LXXXIII" />
    <Biome id="hell_84" name="The Underworld LXXXIV" />
    <Biome id="hell_85" name="The Underworld LXXXV" />
    <Biome id="hell_86" name="The Underworld LXXXVI" />
    <Biome id="hell_87" name="The Underworld LXXXVII" />
    <Biome id="hell_88" name="The Underworld LXXXVIII" />
    <Biome id="hell_89" name="The Underworld LXXXIX" />
    <Biome id="hell_90" name="The Underworld XC" />
    <Biome id="hell_91" name="The Underworld XCI" />
    <Biome id="hell_92" name="The Underworld XCII" />
    <Biome id="hell_93" name="The Underworld XCIII" />
    <Biome id="hell_94" name="The Underworld XCIV" />
    <Biome id="hell_95" name="The Underworld XCV" />
    <Biome id="hell_96" name="The Underworld XCVI" />
    <Biome id="hell_97" name="The Underworld XCVII" />
    <Biome id="hell_98" name="The Underworld XCVIII" />
    <Biome id="hell_99" name="The Underworld XCIX" />
    <Biome id="hell_100" name="The Underworld C" />
    <Biome id="hell_101" name="The Underworld CI" />
    <Biome id="hell_102" name="The Underworld CII" />
    <Biome id="hell_103" name="The Underworld CIII" />
    <Biome id="hell_104" name="The Underworld CIV" />
    <Biome id="hell_105" name="The Underworld CV" />
    <Biome id="hell_106" name="The Underworld CVI" />
    <Biome id="hell_107" name="The Underworld CVII" />
    <Biome id="hell_108" name="The Underworld CVIII" />
    <Biome id="hell_109" name="The Underworld CIX" />
    <Biome id="hell_110" name="The Underworld CX" />
    <Biome id="hell_111" name="The Underworld CXI" />
    <Biome id="hell_112" name="The Underworld CXII" />
    <Biome id="hell_113" name="The Underworld CXIII" />
    <Biome id="hell_114" name="The Underworld CXIV" />
    <Biome id="hell_115" name="The Underworld CXV" />
    <Biome id="hell_116" name="The Underworld CXVI" />
    <Biome id="hell_117" name="The Underworld CXVII" />
    <Biome id="hell_118" name="The Underworld CXVIII" />
    <Biome id="hell_119" name="The Underworld CXIX" />
    <Biome id="hell_120" name="The Underworld CXX" />
    <Biome id="hell_121" name="The Underworld CXXI" />
    <Biome id="hell_122" name="The Underworld CXXII" />
    <Biome id="hell_123" name="The Underworld CXXIII" />
    <Biome id="hell_124" name="The Underworld CXXIV" />
    <Biome id="hell_125" name="The Underworld CXXV" />
    <Biome id="hell_126" name="The Underworld CXXVI" />
    <Biome id="hell_127" name="The Underworld CXXVII" />
    <Biome id="hell_128" name="The Underworld CXXVIII" />
    <Biome id="hell_129" name="The Underworld CXXIX" />
    <Biome id="hell_130" name="The Underworld CXXX" />
    <Biome id="hell_131" name="The Underworld CXXXI" />
    <Biome id="hell_132" name="The Underworld CXXXII" />
    <Biome id="hell_133" name="The Underworld CXXXIII" />
    <Biome id="hell_134" name="The Underworld CXXXIV" />
    <Biome id="hell_135" name="The Underworld CXXXV" />
    <Biome id="hell_136" name="The Underworld CXXXVI" />
    <Biome id="hell_137" name="The Underworld CXXXVII" />
    <Biome id="hell_138" name="The Underworld CXXXVIII" />
    <Biome id="hell_139" name="The Underworld CXXXIX" />
    <Biome id="hell_140" name="The Underworld CXL" />
    <Biome id="hell_141" name="The Underworld CXLI" />
    <Biome id="hell_142" name="The Underworld CXLII" />
    <Biome id="hell_143" name="The Underworld CXLIII" />
    <Biome id="hell_144" name="The Underworld CXLIV" />
    <Biome id="hell_145" name="The Underworld CXLV" />
    <Biome id="hell_146" name="The Underworld CXLVI" />
    <Biome id="hell_147" name="The Underworld CXLVII" />
    <Biome id="hell_148" name="The Underworld CXLVIII" />
    <Biome id="hell_149" name="The Underworld CXLIX" />
    <Biome id="hell_150" name="The Underworld CL" />
    <Biome id="hell_151" name="The Underworld CLI" />
    <Biome id="hell_152" name="The Underworld CLII" />
    <Biome id="hell_153" name="The Underworld CLIII" />
    <Biome id="hell_154" name="The Underworld CLIV" />
    <Biome id="hell_155" name="The Underworld CLV" />
    <Biome id="hell_156" name="The Underworld CLVI" />
    <Biome id="hell_157" name="The Underworld CLVII" />
    <Biome id="hell_158" name="The Underworld CLVIII" />
    <Biome id="hell_159" name="The Underworld CLIX" />
    <Biome id="hell_160" name="The Underworld CLX" />
    <Biome id="hell_161" name="The Underworld CLXI" />
    <Biome id="hell_162" name="The Underworld CLXII" />
    <Biome id="hell_163" name="The Underworld CLXIII" />
    <Biome id="hell_164" name="The Underworld CLXIV" />
    <Biome id="hell_165" name="The Underworld CLXV" />
    <Biome id="hell_166" name="The Underworld CLXVI" />
    <Biome id="hell_167" name="The Underworld CLXVII" />
    <Biome id="hell_168" name="The Underworld CLXVIII" />
    <Biome id="hell_169" name="The Underworld CLXIX" />
    <Biome id="hell_170" name="The Underworld CLXX" />
    <Biome id="hell_171" name="The Underworld CLXXI" />
    <Biome id="hell_172" name="The Underworld CLXXII" />
    <Biome id="hell_173" name="The Underworld CLXXIII" />
    <Biome id="hell_174" name="The Underworld CLXXIV" />
    <Biome id="hell_175" name="The Underworld CLXXV" />
    <Biome id="hell_176" name="The Underworld CLXXVI" />
    <Biome id="hell_177" name="The Underworld CLXXVII" />
    <Biome id="hell_178" name="The Underworld CLXXVIII" />
    <Biome id="hell_179" name="The Underworld CLXXIX" />
    <Biome id="hell_180" name="The Underworld CLXXX" />
    <Biome id="hell_181" name="The Underworld CLXXXI" />
    <Biome id="hell_182" name="The Underworld CLXXXII" />
    <Biome id="hell_183" name="The Underworld CLXXXIII" />
    <Biome id="hell_184" name="The Underworld CLXXXIV" />
    <Biome id="hell_185" name="The Underworld CLXXXV" />
    <Biome id="hell_186" name="The Underworld CLXXXVI" />
    <Biome id="hell_187" name="The Underworld CLXXXVII" />
    <Biome id="hell_188" name="The Underworld CLXXXVIII" />
    <Biome id="hell_189" name="The Underworld CLXXXIX" />
    <Biome id="hell_190" name="The Underworld CXC" />
    <Biome id="hell_191" name="The Underworld CXCI" />
    <Biome id="hell_192" name="The Underworld CXCII" />
    <Biome id="hell_193" name="The Underworld CXCIII" />
    <Biome id="hell_194" name="The Underworld CXCIV" />
    <Biome id="hell_195" name="The Underworld CXCV" />
    <Biome id="hell_196" name="The Underworld CXCVI" />
    <Biome id="hell_197" name="The Underworld CXCVII" />
    <Biome id="hell_198" name="The Underworld CXCVIII" />
    <Biome id="hell_199" name="The Underworld CXCIX" />
    <Biome id="hell_200" name="The Underworld CC" />
    <Biome id="hell_201" name="The Underworld CCI" />
    <Biome id="hell_202" name="The Underworld CCII" />
    <Biome id="hell_203" name="The Underworld CCIII" />
    <Biome id="hell_204" name="The Underworld CCIV" />
    <Biome id="hell_205" name="The Underworld CCV" />
    <Biome id="hell_206" name="The Underworld CCVI" />
    <Biome id="hell_207" name="The Underworld CCVII" />
    <Biome id="hell_208" name="The Underworld CCVIII" />
    <Biome id="hell_209" name="The Underworld CCIX" />
    <Biome id="hell_210" name="The Underworld CCX" />
    <Biome id="hell_211" name="The Underworld CCXI" />
    <Biome id="hell_212" name="The Underworld CCXII" />
    <Biome id="hell_213" name="The Underworld CCXIII" />
    <Biome id="hell_214" name="The Underworld CCXIV" />
    <Biome id="hell_215" name="The Underworld CCXV" />
    <Biome id="hell_216" name="The Underworld CCXVI" />
    <Biome id="hell_217" name="The Underworld CCXVII" />
    <Biome id="hell_218" name="The Underworld CCXVIII" />
    <Biome id="hell_219" name="The Underworld CCXIX" />
    <Biome id="hell_220" name="The Underworld CCXX" />
    <Biome id="hell_221" name="The Underworld CCXXI" />
    <Biome id="hell_222" name="The Underworld CCXXII" />
    <Biome id="hell_223" name="The Underworld CCXXIII" />
    <Biome id="hell_224" name="The Underworld CCXXIV" />
    <Biome id="hell_225" name="The Underworld CCXXV" />
    <Biome id="hell_226" name="The Underworld CCXXVI" />
    <Biome id="hell_227" name="The Underworld CCXXVII" />
    <Biome id="hell_228" name="The Underworld CCXXVIII" />
    <Biome id="hell_229" name="The Underworld CCXXIX" />
    <Biome id="hell_230" name="The Underworld CCXXX" />
    <Biome id="hell_231" name="The Underworld CCXXXI" />
    <Biome id="hell_232" name="The Underworld CCXXXII" />
    <Biome id="hell_233" name="The Underworld CCXXXIII" />
    <Biome id="hell_234" name="The Underworld CCXXXIV" />
    <Biome id="hell_235" name="The Underworld CCXXXV" />
    <Biome id="hell_236" name="The Underworld CCXXXVI" />
    <Biome id="hell_237" name="The Underworld CCXXXVII" />
    <Biome id="hell_238" name="The Underworld CCXXXVIII" />
    <Biome id="hell_239" name="The Underworld CCXXXIX" />
    <Biome id="hell_240" name="The Underworld CCXL" />
    <Biome id="hell_241" name="The Underworld CCXLI" />
    <Biome id="hell_242" name="The Underworld CCXLII" />
    <Biome id="hell_243" name="The Underworld CCXLIII" />
    <Biome id="hell_244" name="The Underworld CCXLIV" />
    <Biome id="hell_245" name="The Underworld CCXLV" />
    <Biome id="hell_246" name="The Underworld CCXLVI" />
    <Biome id="hell_247" name="The Underworld CCXLVII" />
    <Biome id="hell_248" name="The Underworld CCXLVIII" />
    <Biome id="hell_249" name="The Underworld CCXLIX" />
    <Biome id="hell_250" name="The Underworld CCL" />
    <Biome id="hell_251" name="The Underworld CCLI" />
    <Biome id="hell_252" name="The Underworld CCLII" />
    <Biome id="hell_253" name="The Underworld CCLIII" />
    <Biome id="hell_254" name="The Underworld CCLIV" />
    <Biome id="hell_255" name="The Underworld CCLV" />
    <Biome id="hell_256" name="The Underworld CCLVI" />
    <Biome id="hell_257" name="The Underworld CCLVII" />
    <Biome id="hell_258" name="The Underworld CCLVIII" />
    <Biome id="hell_259" name="The Underworld CCLIX" />
    <Biome id="hell_260" name="The Underworld CCLX" />
    <Biome id="hell_261" name="The Underworld CCLXI" />
    <Biome id="hell_262" name="The Underworld CCLXII" />
    <Biome id="hell_263" name="The Underworld CCLXIII" />
    <Biome id="hell_264" name="The Underworld CCLXIV" />
    <Biome id="hell_265" name="The Underworld CCLXV" />
    <Biome id="hell_266" name="The Underworld CCLXVI" />
    <Biome id="hell_267" name="The Underworld CCLXVII" />
    <Biome id="hell_268" name="The Underworld CCLXVIII" />
    <Biome id="hell_269" name="The Underworld CCLXIX" />
    <Biome id="hell_270" name="The Underworld CCLXX" />
    <Biome id="hell_271" name="The Underworld CCLXXI" />
    <Biome id="hell_272" name="The Underworld CCLXXII" />
    <Biome id="hell_273" name="The Underworld CCLXXIII" />
    <Biome id="hell_274" name="The Underworld CCLXXIV" />
    <Biome id="hell_275" name="The Underworld CCLXXV" />
    <Biome id="hell_276" name="The Underworld CCLXXVI" />
    <Biome id="hell_277" name="The Underworld CCLXXVII" />
    <Biome id="hell_278" name="The Underworld CCLXXVIII" />
    <Biome id="hell_279" name="The Underworld CCLXXIX" />
    <Biome id="hell_280" name="The Underworld CCLXXX" />
    <Biome id="hell_281" name="The Underworld CCLXXXI" />
    <Biome id="hell_282" name="The Underworld CCLXXXII" />
    <Biome id="hell_283" name="The Underworld CCLXXXIII" />
    <Biome id="hell_284" name="The Underworld CCLXXXIV" />
    <Biome id="hell_285" name="The Underworld CCLXXXV" />
    <Biome id="hell_286" name="The Underworld CCLXXXVI" />
    <Biome id="hell_287" name="The Underworld CCLXXXVII" />
    <Biome id="hell_288" name="The Underworld CCLXXXVIII" />
    <Biome id="hell_289" name="The Underworld CCLXXXIX" />
    <Biome id="hell_290" name="The Underworld CCXC" />
    <Biome id="hell_291" name="The Underworld CCXCI" />
    <Biome id="hell_292" name="The Underworld CCXCII" />
    <Biome id="hell_293" name="The Underworld CCXCIII" />
    <Biome id="hell_294" name="The Underworld CCXCIV" />
    <Biome id="hell_295" name="The Underworld CCXCV" />
    <Biome id="hell_296" name="The Underworld CCXCVI" />
    <Biome id="hell_297" name="The Underworld CCXCVII" />
    <Biome id="hell_298" name="The Underworld CCXCVIII" />
    <Biome id="hell_299" name="The Underworld CCXCIX" />
    <Biome id="hell_300" name="The Underworld CCC" />
    <Biome id="hell_301" name="The Underworld CCCI" />
    <Biome id="hell_302" name="The Underworld CCCII" />
    <Biome id="hell_303" name="The Underworld CCCIII" />
    <Biome id="hell_304" name="The Underworld CCCIV" />
    <Biome id="hell_305" name="The Underworld CCCV" />
    <Biome id="hell_306" name="The Underworld CCCVI" />
    <Biome id="hell_307" name="The Underworld CCCVII" />
    <Biome id="hell_308" name="The Underworld CCCVIII" />
    <Biome id="hell_309" name="The Underworld CCCIX" />
    <Biome id="hell_310" name="The Underworld CCCX" />
    <Biome id="hell_311" name="The Underworld CCCXI" />
    <Biome id="hell_312" name="The Underworld CCCXII" />
    <Biome id="hell_313" name="The Underworld CCCXIII" />
    <Biome id="hell_314" name="The Underworld CCCXIV" />
    <Biome id="hell_315" name="The Underworld CCCXV" />
    <Biome id="hell_316" name="The Underworld CCCXVI" />
    <Biome id="hell_317" name="The Underworld CCCXVII" />
    <Biome id="hell_318" name="The Underworld CCCXVIII" />
    <Biome id="hell_319" name="The Underworld CCCXIX" />
    <Biome id="hell_320" name="The Underworld CCCXX" />
    <Biome id="hell_321" name="The Underworld CCCXXI" />
    <Biome id="hell_322" name="The Underworld CCCXXII" />
    <Biome id="hell_323" name="The Underworld CCCXXIII" />
    <Biome id="hell_324" name="The Underworld CCCXXIV" />
    <Biome id="hell_325" name="The Underworld CCCXXV" />
    <Biome id="hell_326" name="The Underworld CCCXXVI" />
    <Biome id="hell_327" name="The Underworld CCCXXVII" />
    <Biome id="hell_328" name="The Underworld CCCXXVIII" />
    <Biome id="hell_329" name="The Underworld CCCXXIX" />
    <Biome id="hell_330" name="The Underworld CCCXXX" />
    <Biome id="hell_331" name="The Underworld CCCXXXI" />
    <Biome id="hell_332" name="The Underworld CCCXXXII" />
    <Biome id="hell_333" name="The Underworld CCCXXXIII" />
    <Biome id="hell_334" name="The Underworld CCCXXXIV" />
    <Biome id="hell_335" name="The Underworld CCCXXXV" />
    <Biome id="hell_336" name="The Underworld CCCXXXVI" />
    <Biome id="hell_337" name="The Underworld CCCXXXVII" />
    <Biome id="hell_338" name="The Underworld CCCXXXVIII" />
    <Biome id="hell_339" name="The Underworld CCCXXXIX" />
    <Biome id="hell_340" name="The Underworld CCCXL" />
    <Biome id="hell_341" name="The Underworld CCCXLI" />
    <Biome id="hell_342" name="The Underworld CCCXLII" />
    <Biome id="hell_343" name="The Underworld CCCXLIII" />
    <Biome id="hell_344" name="The Underworld CCCXLIV" />
    <Biome id="hell_345" name="The Underworld CCCXLV" />
    <Biome id="hell_346" name="The Underworld CCCXLVI" />
    <Biome id="hell_347" name="The Underworld CCCXLVII" />
    <Biome id="hell_348" name="The Underworld CCCXLVIII" />
    <Biome id="hell_349" name="The Underworld CCCXLIX" />
    <Biome id="hell_350" name="The Underworld CCCL" />
    <Biome id="hell_351" name="The Underworld CCCLI" />
    <Biome id="hell_352" name="The Underworld CCCLII" />
    <Biome id="hell_353" name="The Underworld CCCLIII" />
    <Biome id="hell_354" name="The Underworld CCCLIV" />
    <Biome id="hell_355" name="The Underworld CCCLV" />
    <Biome id="hell_356" name="The Underworld CCCLVI" />
    <Biome id="hell_357" name="The Underworld CCCLVII" />
    <Biome id="hell_358" name="The Underworld CCCLVIII" />
    <Biome id="hell_359" name="The Underworld CCCLIX" />
    <Biome id="hell_360" name="The Underworld CCCLX" />
    <Biome id="hell_361" name="The Underworld CCCLXI" />
    <Biome id="hell_362" name="The Underworld CCCLXII" />
    <Biome id="hell_363" name="The Underworld CCCLXIII" />
    <Biome id="hell_364" name="The Underworld CCCLXIV" />
    <Biome id="hell_365" name="The Underworld CCCLXv" />
    <Biome id="hell_366" name="The Underworld CCCLXVI" />
    <Biome id="hell_367" name="The Underworld CCCLXVII" />
    <Biome id="hell_368" name="The Underworld CCCLXVIII" />
    <Biome id="hell_369" name="The Underworld CCCLXIX" />
    <Biome id="hell_370" name="The Underworld CCCLXX" />
    <Biome id="hell_371" name="The Underworld CCCLXXI" />
    <Biome id="hell_372" name="The Underworld CCCLXXII" />
    <Biome id="hell_373" name="The Underworld CCCLXXIII" />
    <Biome id="hell_374" name="The Underworld CCCLXXIV" />
    <Biome id="hell_375" name="The Underworld CCCLXXV" />
    <Biome id="hell_376" name="The Underworld CCCLXXVI" />
    <Biome id="hell_377" name="The Underworld CCCLXXVII" />
    <Biome id="hell_378" name="The Underworld CCCLXXVIII" />
    <Biome id="hell_379" name="The Underworld CCCLXXIX" />
    <Biome id="hell_380" name="The Underworld CCCLXXX" />
    <Biome id="hell_381" name="The Underworld CCCLXXXI" />
    <Biome id="hell_382" name="The Underworld CCCLXXXII" />
    <Biome id="hell_383" name="The Underworld CCCLXXXIII" />
    <Biome id="hell_384" name="The Underworld CCCLXXXIV" />
    <Biome id="hell_385" name="The Underworld CCCLXXXV" />
    <Biome id="hell_386" name="The Underworld CCCLXXXVI" />
    <Biome id="hell_387" name="The Underworld CCCLXXXVII" />
    <Biome id="hell_388" name="The Underworld CCCLXXXVIII" />
    <Biome id="hell_389" name="The Underworld CCCLXXXIX" />
    <Biome id="hell_390" name="The Underworld CCCXC" />
    <Biome id="hell_391" name="The Underworld CCCXCI" />
    <Biome id="hell_392" name="The Underworld CCCXCII" />
    <Biome id="hell_393" name="The Underworld CCCXCIII" />
    <Biome id="hell_394" name="The Underworld CCCXCIV" />
    <Biome id="hell_395" name="The Underworld CCCXCV" />
    <Biome id="hell_396" name="The Underworld CCCXCVI" />
    <Biome id="hell_397" name="The Underworld CCCXCVII" />
    <Biome id="hell_398" name="The Underworld CCCXCVIII" />
    <Biome id="hell_399" name="The Underworld CCCXCIX" />
    <Biome id="hell_400" name="The Underworld CD" />
    <Biome id="hell_401" name="The Underworld CDI" />
    <Biome id="hell_402" name="The Underworld CDII" />
    <Biome id="hell_403" name="The Underworld CDIII" />
    <Biome id="hell_404" name="The Underworld CDIV" />
    <Biome id="hell_405" name="The Underworld CDV" />
    <Biome id="hell_406" name="The Underworld CDVI" />
    <Biome id="hell_407" name="The Underworld CDVII" />
    <Biome id="hell_408" name="The Underworld CDVIII" />
    <Biome id="hell_409" name="The Underworld CDIX" />
    <Biome id="hell_410" name="The Underworld CDX" />
    <Biome id="hell_411" name="The Underworld CDXI" />
    <Biome id="hell_412" name="The Underworld CDXII" />
    <Biome id="hell_413" name="The Underworld CDXIII" />
    <Biome id="hell_414" name="The Underworld CDXIV" />
    <Biome id="hell_415" name="The Underworld CDXV" />
    <Biome id="hell_416" name="The Underworld CDXVI" />
    <Biome id="hell_417" name="The Underworld CDXVII" />
    <Biome id="hell_418" name="The Underworld CDXVIII" />
    <Biome id="hell_419" name="The Underworld CDXIX" />
    <Biome id="hell_420" name="The Underworld CDXX" />
    <Biome id="hell_421" name="The Underworld CDXXI" />
    <Biome id="hell_422" name="The Underworld CDXXII" />
    <Biome id="hell_423" name="The Underworld CDXXIII" />
    <Biome id="hell_424" name="The Underworld CDXXIV" />
    <Biome id="hell_425" name="The Underworld CDXXV" />
    <Biome id="hell_426" name="The Underworld CDXXVI" />
    <Biome id="hell_427" name="The Underworld CDXXVII" />
    <Biome id="hell_428" name="The Underworld CDXXVIII" />
    <Biome id="hell_429" name="The Underworld CDXXIX" />
    <Biome id="hell_430" name="The Underworld CDXXX" />
    <Biome id="hell_431" name="The Underworld CDXXXI" />
    <Biome id="hell_432" name="The Underworld CDXXXII" />
    <Biome id="hell_433" name="The Underworld CDXXXIII" />
    <Biome id="hell_434" name="The Underworld CDXXXIV" />
    <Biome id="hell_435" name="The Underworld CDXXXV" />
    <Biome id="hell_436" name="The Underworld CDXXXVI" />
    <Biome id="hell_437" name="The Underworld CDXXXVII" />
    <Biome id="hell_438" name="The Underworld CDXXXVIII" />
    <Biome id="hell_439" name="The Underworld CDXXXIX" />
    <Biome id="hell_440" name="The Underworld CDXL" />
    <Biome id="hell_441" name="The Underworld CDXLI" />
    <Biome id="hell_442" name="The Underworld CDXLII" />
    <Biome id="hell_443" name="The Underworld CDXLIII" />
    <Biome id="hell_444" name="The Underworld CDXLIV" />
    <Biome id="hell_445" name="The Underworld CDXLV" />
    <Biome id="hell_446" name="The Underworld CDXLVI" />
    <Biome id="hell_447" name="The Underworld CDXLVII" />
    <Biome id="hell_448" name="The Underworld CDXLVIII" />
    <Biome id="hell_449" name="The Underworld CDXLIX" />
    <Biome id="hell_450" name="The Underworld CDL" />
    <Biome id="hell_451" name="The Underworld CDLI" />
    <Biome id="hell_452" name="The Underworld CDLII" />
    <Biome id="hell_453" name="The Underworld CDLIII" />
    <Biome id="hell_454" name="The Underworld CDLIV" />
    <Biome id="hell_455" name="The Underworld CDLV" />
    <Biome id="hell_456" name="The Underworld CDLVI" />
    <Biome id="hell_457" name="The Underworld CDLVII" />
    <Biome id="hell_458" name="The Underworld CDLVIII" />
    <Biome id="hell_459" name="The Underworld CDLIX" />
    <Biome id="hell_460" name="The Underworld CDLX" />
    <Biome id="hell_461" name="The Underworld CDLXI" />
    <Biome id="hell_462" name="The Underworld CDLXII" />
    <Biome id="hell_463" name="The Underworld CDLXIII" />
    <Biome id="hell_464" name="The Underworld CDLXIV" />
    <Biome id="hell_465" name="The Underworld CDLXv" />
    <Biome id="hell_466" name="The Underworld CDLXVI" />
    <Biome id="hell_467" name="The Underworld CDLXVII" />
    <Biome id="hell_468" name="The Underworld CDLXVIII" />
    <Biome id="hell_469" name="The Underworld CDLXIX" />
    <Biome id="hell_470" name="The Underworld CDLXX" />
    <Biome id="hell_471" name="The Underworld CDLXXI" />
    <Biome id="hell_472" name="The Underworld CDLXXII" />
    <Biome id="hell_473" name="The Underworld CDLXXIII" />
    <Biome id="hell_474" name="The Underworld CDLXXIV" />
    <Biome id="hell_475" name="The Underworld CDLXXV" />
    <Biome id="hell_476" name="The Underworld CDLXXVI" />
    <Biome id="hell_477" name="The Underworld CDLXXVII" />
    <Biome id="hell_478" name="The Underworld CDLXXVIII" />
    <Biome id="hell_479" name="The Underworld CDLXXIX" />
    <Biome id="hell_480" name="The Underworld CDLXXX" />
    <Biome id="hell_481" name="The Underworld CDLXXXI" />
    <Biome id="hell_482" name="The Underworld CDLXXXII" />
    <Biome id="hell_483" name="The Underworld CDLXXXIII" />
    <Biome id="hell_484" name="The Underworld CDLXXXIV" />
    <Biome id="hell_485" name="The Underworld CDLXXXV" />
    <Biome id="hell_486" name="The Underworld CDLXXXVI" />
    <Biome id="hell_487" name="The Underworld CDLXXXVII" />
    <Biome id="hell_488" name="The Underworld CDLXXXVIII" />
    <Biome id="hell_489" name="The Underworld CDLXXXIX" />
    <Biome id="hell_490" name="The Underworld CDXC" />
    <Biome id="hell_491" name="The Underworld CDXCI" />
    <Biome id="hell_492" name="The Underworld CDXCII" />
    <Biome id="hell_493" name="The Underworld CDXCIII" />
    <Biome id="hell_494" name="The Underworld CDXCIV" />
    <Biome id="hell_495" name="The Underworld CDXCV" />
    <Biome id="hell_496" name="The Underworld CDXCVI" />
    <Biome id="hell_497" name="The Underworld CDXCVII" />
    <Biome id="hell_498" name="The Underworld CDXCVIII" />
    <Biome id="hell_499" name="The Underworld CDXCIX" />
    <Biome id="hell_500" name="The Underworld D" />
    <Biome id="hell_501" name="The Underworld DI" />
    <Biome id="hell_502" name="The Underworld DII" />
    <Biome id="hell_503" name="The Underworld DIII" />
    <Biome id="hell_504" name="The Underworld DIV" />
    <Biome id="hell_505" name="The Underworld DV" />
    <Biome id="hell_506" name="The Underworld DVI" />
    <Biome id="hell_507" name="The Underworld DVII" />
    <Biome id="hell_508" name="The Underworld DVIII" />
    <Biome id="hell_509" name="The Underworld DIX" />
    <Biome id="hell_510" name="The Underworld DX" />
    <Biome id="hell_511" name="The Underworld DXI" />
    <Biome id="hell_512" name="The Underworld DXII" />
    <Biome id="hell_513" name="The Underworld DXIII" />
    <Biome id="hell_514" name="The Underworld DXIV" />
    <Biome id="hell_515" name="The Underworld DXV" />
    <Biome id="hell_516" name="The Underworld DXVI" />
    <Biome id="hell_517" name="The Underworld DXVII" />
    <Biome id="hell_518" name="The Underworld DXVIII" />
    <Biome id="hell_519" name="The Underworld DXIX" />
    <Biome id="hell_520" name="The Underworld DXX" />
    <Biome id="hell_521" name="The Underworld DXXI" />
    <Biome id="hell_522" name="The Underworld DXXII" />
    <Biome id="hell_523" name="The Underworld DXXIII" />
    <Biome id="hell_524" name="The Underworld DXXIV" />
    <Biome id="hell_525" name="The Underworld DXXV" />
    <Biome id="hell_526" name="The Underworld DXXVI" />
    <Biome id="hell_527" name="The Underworld DXXVII" />
    <Biome id="hell_528" name="The Underworld DXXVIII" />
    <Biome id="hell_529" name="The Underworld DXXIX" />
    <Biome id="hell_530" name="The Underworld DXXX" />
    <Biome id="hell_531" name="The Underworld DXXXI" />
    <Biome id="hell_532" name="The Underworld DXXXII" />
    <Biome id="hell_533" name="The Underworld DXXXIII" />
    <Biome id="hell_534" name="The Underworld DXXXIV" />
    <Biome id="hell_535" name="The Underworld DXXXV" />
    <Biome id="hell_536" name="The Underworld DXXXVI" />
    <Biome id="hell_537" name="The Underworld DXXXVII" />
    <Biome id="hell_538" name="The Underworld DXXXVIII" />
    <Biome id="hell_539" name="The Underworld DXXXIX" />
    <Biome id="hell_540" name="The Underworld DXl" />
    <Biome id="hell_541" name="The Underworld DXLI" />
    <Biome id="hell_542" name="The Underworld DXlII" />
    <Biome id="hell_543" name="The Underworld DXlIII" />
    <Biome id="hell_544" name="The Underworld DXlIV" />
    <Biome id="hell_545" name="The Underworld DXlV" />
    <Biome id="hell_546" name="The Underworld DXlVI" />
    <Biome id="hell_547" name="The Underworld DXlVII" />
    <Biome id="hell_548" name="The Underworld DXlVIII" />
    <Biome id="hell_549" name="The Underworld DXlIX" />
    <Biome id="hell_550" name="The Underworld DL" />
    <Biome id="hell_551" name="The Underworld DLI" />
    <Biome id="hell_552" name="The Underworld DLII" />
    <Biome id="hell_553" name="The Underworld DLIII" />
    <Biome id="hell_554" name="The Underworld DLIV" />
    <Biome id="hell_555" name="The Underworld DLV" />
    <Biome id="hell_556" name="The Underworld DLVI" />
    <Biome id="hell_557" name="The Underworld DLVII" />
    <Biome id="hell_558" name="The Underworld DLVIII" />
    <Biome id="hell_559" name="The Underworld DLIX" />
    <Biome id="hell_560" name="The Underworld DLX" />
    <Biome id="hell_561" name="The Underworld DLXI" />
    <Biome id="hell_562" name="The Underworld DLXII" />
    <Biome id="hell_563" name="The Underworld DLXIII" />
    <Biome id="hell_564" name="The Underworld DLXIV" />
    <Biome id="hell_565" name="The Underworld DLxv" />
    <Biome id="hell_566" name="The Underworld DLXVI" />
    <Biome id="hell_567" name="The Underworld DLXVII" />
    <Biome id="hell_568" name="The Underworld DLXVIII" />
    <Biome id="hell_569" name="The Underworld DLXIX" />
    <Biome id="hell_570" name="The Underworld DLXX" />
    <Biome id="hell_571" name="The Underworld DLXXI" />
    <Biome id="hell_572" name="The Underworld DLXXII" />
    <Biome id="hell_573" name="The Underworld DLXXIII" />
    <Biome id="hell_574" name="The Underworld DLXXIV" />
    <Biome id="hell_575" name="The Underworld DLXXV" />
    <Biome id="hell_576" name="The Underworld DLXXVI" />
    <Biome id="hell_577" name="The Underworld DLXXVII" />
    <Biome id="hell_578" name="The Underworld DLXXVIII" />
    <Biome id="hell_579" name="The Underworld DLXXIX" />
    <Biome id="hell_580" name="The Underworld DLXXX" />
    <Biome id="hell_581" name="The Underworld DLXXXI" />
    <Biome id="hell_582" name="The Underworld DLXXXII" />
    <Biome id="hell_583" name="The Underworld DLXXXIII" />
    <Biome id="hell_584" name="The Underworld DLXXXIV" />
    <Biome id="hell_585" name="The Underworld DLXXXV" />
    <Biome id="hell_586" name="The Underworld DLXXXVI" />
    <Biome id="hell_587" name="The Underworld DLXXXVII" />
    <Biome id="hell_588" name="The Underworld DLXXXVIII" />
    <Biome id="hell_589" name="The Underworld DLXXXIX" />
    <Biome id="hell_590" name="The Underworld DXC" />
    <Biome id="hell_591" name="The Underworld DXCI" />
    <Biome id="hell_592" name="The Underworld DXCII" />
    <Biome id="hell_593" name="The Underworld DXCIII" />
    <Biome id="hell_594" name="The Underworld DXCIV" />
    <Biome id="hell_595" name="The Underworld DXCV" />
    <Biome id="hell_596" name="The Underworld DXCVI" />
    <Biome id="hell_597" name="The Underworld DXCVII" />
    <Biome id="hell_598" name="The Underworld DXCVIII" />
    <Biome id="hell_599" name="The Underworld DXCIX" />
    <Biome id="hell_600" name="The Underworld DC" />
    <Biome id="hell_601" name="The Underworld DCI" />
    <Biome id="hell_602" name="The Underworld DCII" />
    <Biome id="hell_603" name="The Underworld DCIII" />
    <Biome id="hell_604" name="The Underworld DCIV" />
    <Biome id="hell_605" name="The Underworld DCV" />
    <Biome id="hell_606" name="The Underworld DCVI" />
    <Biome id="hell_607" name="The Underworld DCVII" />
    <Biome id="hell_608" name="The Underworld DCVIII" />
    <Biome id="hell_609" name="The Underworld DCIX" />
    <Biome id="hell_610" name="The Underworld DCX" />
    <Biome id="hell_611" name="The Underworld DCXI" />
    <Biome id="hell_612" name="The Underworld DCXII" />
    <Biome id="hell_613" name="The Underworld DCXIII" />
    <Biome id="hell_614" name="The Underworld DCXIV" />
    <Biome id="hell_615" name="The Underworld DCXV" />
    <Biome id="hell_616" name="The Underworld DCXVI" />
    <Biome id="hell_617" name="The Underworld DCXVII" />
    <Biome id="hell_618" name="The Underworld DCXVIII" />
    <Biome id="hell_619" name="The Underworld DCXIX" />
    <Biome id="hell_620" name="The Underworld DCXX" />
    <Biome id="hell_621" name="The Underworld DCXXI" />
    <Biome id="hell_622" name="The Underworld DCXXII" />
    <Biome id="hell_623" name="The Underworld DCXXIII" />
    <Biome id="hell_624" name="The Underworld DCXXIV" />
    <Biome id="hell_625" name="The Underworld DCXXV" />
    <Biome id="hell_626" name="The Underworld DCXXVI" />
    <Biome id="hell_627" name="The Underworld DCXXVII" />
    <Biome id="hell_628" name="The Underworld DCXXVIII" />
    <Biome id="hell_629" name="The Underworld DCXXIX" />
    <Biome id="hell_630" name="The Underworld DCXXX" />
    <Biome id="hell_631" name="The Underworld DCXXXI" />
    <Biome id="hell_632" name="The Underworld DCXXXII" />
    <Biome id="hell_633" name="The Underworld DCXXXIII" />
    <Biome id="hell_634" name="The Underworld DCXXXIV" />
    <Biome id="hell_635" name="The Underworld DCXXXV" />
    <Biome id="hell_636" name="The Underworld DCXXXVI" />
    <Biome id="hell_637" name="The Underworld DCXXXVII" />
    <Biome id="hell_638" name="The Underworld DCXXXVIII" />
    <Biome id="hell_639" name="The Underworld DCXXXIX" />
    <Biome id="hell_640" name="The Underworld DCXL" />
    <Biome id="hell_641" name="The Underworld DCXLI" />
    <Biome id="hell_642" name="The Underworld DCXLII" />
    <Biome id="hell_643" name="The Underworld DCXLIII" />
    <Biome id="hell_644" name="The Underworld DCXLIV" />
    <Biome id="hell_645" name="The Underworld DCXLV" />
    <Biome id="hell_646" name="The Underworld DCXLVI" />
    <Biome id="hell_647" name="The Underworld DCXLVII" />
    <Biome id="hell_648" name="The Underworld DCXLVIII" />
    <Biome id="hell_649" name="The Underworld DCXLIX" />
    <Biome id="hell_650" name="The Underworld DCL" />
    <Biome id="hell_651" name="The Underworld DCLI" />
    <Biome id="hell_652" name="The Underworld DCLII" />
    <Biome id="hell_653" name="The Underworld DCLIII" />
    <Biome id="hell_654" name="The Underworld DCLIV" />
    <Biome id="hell_655" name="The Underworld DCLV" />
    <Biome id="hell_656" name="The Underworld DCLVI" />
    <Biome id="hell_657" name="The Underworld DCLVII" />
    <Biome id="hell_658" name="The Underworld DCLVIII" />
    <Biome id="hell_659" name="The Underworld DCLIX" />
    <Biome id="hell_660" name="The Underworld DCLX" />
    <Biome id="hell_661" name="The Underworld DCLXI" />
    <Biome id="hell_662" name="The Underworld DCLXII" />
    <Biome id="hell_663" name="The Underworld DCLXIII" />
    <Biome id="hell_664" name="The Underworld DCLXIV" />
    <Biome id="hell_665" name="The Underworld DCLxv" />
    <Biome id="hell_666" name="The Underworld DCLXVI" />
    <Biome id="hell_667" name="The Underworld DCLXVII" />
    <Biome id="hell_668" name="The Underworld DCLXVIII" />
    <Biome id="hell_669" name="The Underworld DCLXIX" />
    <Biome id="hell_670" name="The Underworld DCLXX" />
    <Biome id="hell_671" name="The Underworld DCLXXI" />
    <Biome id="hell_672" name="The Underworld DCLXXII" />
    <Biome id="hell_673" name="The Underworld DCLXXIII" />
    <Biome id="hell_674" name="The Underworld DCLXXIV" />
    <Biome id="hell_675" name="The Underworld DCLXXV" />
    <Biome id="hell_676" name="The Underworld DCLXXVI" />
    <Biome id="hell_677" name="The Underworld DCLXXVII" />
    <Biome id="hell_678" name="The Underworld DCLXXVIII" />
    <Biome id="hell_679" name="The Underworld DCLXXIX" />
    <Biome id="hell_680" name="The Underworld DCLXXX" />
    <Biome id="hell_681" name="The Underworld DCLXXXI" />
    <Biome id="hell_682" name="The Underworld DCLXXXII" />
    <Biome id="hell_683" name="The Underworld DCLXXXIII" />
    <Biome id="hell_684" name="The Underworld DCLXXXIV" />
    <Biome id="hell_685" name="The Underworld DCLXXXV" />
    <Biome id="hell_686" name="The Underworld DCLXXXVI" />
    <Biome id="hell_687" name="The Underworld DCLXXXVII" />
    <Biome id="hell_688" name="The Underworld DCLXXXVIII" />
    <Biome id="hell_689" name="The Underworld DCLXXXIX" />
    <Biome id="hell_690" name="The Underworld DCXC" />
    <Biome id="hell_691" name="The Underworld DCXCI" />
    <Biome id="hell_692" name="The Underworld DCXCII" />
    <Biome id="hell_693" name="The Underworld DCXCIII" />
    <Biome id="hell_694" name="The Underworld DCXCIV" />
    <Biome id="hell_695" name="The Underworld DCXCV" />
    <Biome id="hell_696" name="The Underworld DCXCVI" />
    <Biome id="hell_697" name="The Underworld DCXCVII" />
    <Biome id="hell_698" name="The Underworld DCXCVIII" />
    <Biome id="hell_699" name="The Underworld DCXCIX" />
    <Biome id="hell_700" name="The Underworld DCC" />
    <Biome id="hell_701" name="The Underworld DCCI" />
    <Biome id="hell_702" name="The Underworld DCCII" />
    <Biome id="hell_703" name="The Underworld DCCIII" />
    <Biome id="hell_704" name="The Underworld DCCIV" />
    <Biome id="hell_705" name="The Underworld DCCV" />
    <Biome id="hell_706" name="The Underworld DCCVI" />
    <Biome id="hell_707" name="The Underworld DCCVII" />
    <Biome id="hell_708" name="The Underworld DCCVIII" />
    <Biome id="hell_709" name="The Underworld DCCIX" />
    <Biome id="hell_710" name="The Underworld DCCX" />
    <Biome id="hell_711" name="The Underworld DCCXI" />
    <Biome id="hell_712" name="The Underworld DCCXII" />
    <Biome id="hell_713" name="The Underworld DCCXIII" />
    <Biome id="hell_714" name="The Underworld DCCXIV" />
    <Biome id="hell_715" name="The Underworld DCCXV" />
    <Biome id="hell_716" name="The Underworld DCCXVI" />
    <Biome id="hell_717" name="The Underworld DCCXVII" />
    <Biome id="hell_718" name="The Underworld DCCXVIII" />
    <Biome id="hell_719" name="The Underworld DCCXIX" />
    <Biome id="hell_720" name="The Underworld DCCXX" />
    <Biome id="hell_721" name="The Underworld DCCXXI" />
    <Biome id="hell_722" name="The Underworld DCCXXII" />
    <Biome id="hell_723" name="The Underworld DCCXXIII" />
    <Biome id="hell_724" name="The Underworld DCCXXIV" />
    <Biome id="hell_725" name="The Underworld DCCXXV" />
    <Biome id="hell_726" name="The Underworld DCCXXVI" />
    <Biome id="hell_727" name="The Underworld DCCXXVII" />
    <Biome id="hell_728" name="The Underworld DCCXXVIII" />
    <Biome id="hell_729" name="The Underworld DCCXXIX" />
    <Biome id="hell_730" name="The Underworld DCCXXX" />
    <Biome id="hell_731" name="The Underworld DCCXXXI" />
    <Biome id="hell_732" name="The Underworld DCCXXXII" />
    <Biome id="hell_733" name="The Underworld DCCXXXIII" />
    <Biome id="hell_734" name="The Underworld DCCXXXIV" />
    <Biome id="hell_735" name="The Underworld DCCXXXV" />
    <Biome id="hell_736" name="The Underworld DCCXXXVI" />
    <Biome id="hell_737" name="The Underworld DCCXXXVII" />
    <Biome id="hell_738" name="The Underworld DCCXXXVIII" />
    <Biome id="hell_739" name="The Underworld DCCXXXIX" />
    <Biome id="hell_740" name="The Underworld DCCXL" />
    <Biome id="hell_741" name="The Underworld DCCXLI" />
    <Biome id="hell_742" name="The Underworld DCCXLII" />
    <Biome id="hell_743" name="The Underworld DCCXLIII" />
    <Biome id="hell_744" name="The Underworld DCCXLIV" />
    <Biome id="hell_745" name="The Underworld DCCXLV" />
    <Biome id="hell_746" name="The Underworld DCCXLVI" />
    <Biome id="hell_747" name="The Underworld DCCXLVII" />
    <Biome id="hell_748" name="The Underworld DCCXLVIII" />
    <Biome id="hell_749" name="The Underworld DCCXLIX" />
    <Biome id="hell_750" name="The Underworld DCCL" />
    <Biome id="hell_751" name="The Underworld DCCLI" />
    <Biome id="hell_752" name="The Underworld DCCLII" />
    <Biome id="hell_753" name="The Underworld DCCLIII" />
    <Biome id="hell_754" name="The Underworld DCCLIV" />
    <Biome id="hell_755" name="The Underworld DCCLV" />
    <Biome id="hell_756" name="The Underworld DCCLVI" />
    <Biome id="hell_757" name="The Underworld DCCLVII" />
    <Biome id="hell_758" name="The Underworld DCCLVIII" />
    <Biome id="hell_759" name="The Underworld DCCLIX" />
    <Biome id="hell_760" name="The Underworld DCCLX" />
    <Biome id="hell_761" name="The Underworld DCCLXI" />
    <Biome id="hell_762" name="The Underworld DCCLXII" />
    <Biome id="hell_763" name="The Underworld DCCLXIII" />
    <Biome id="hell_764" name="The Underworld DCCLXIV" />
    <Biome id="hell_765" name="The Underworld DCCLXv" />
    <Biome id="hell_766" name="The Underworld DCCLXVI" />
    <Biome id="hell_767" name="The Underworld DCCLXVII" />
    <Biome id="hell_768" name="The Underworld DCCLXVIII" />
    <Biome id="hell_769" name="The Underworld DCCLXIX" />
    <Biome id="hell_770" name="The Underworld DCCLXX" />
    <Biome id="hell_771" name="The Underworld DCCLXXI" />
    <Biome id="hell_772" name="The Underworld DCCLXXII" />
    <Biome id="hell_773" name="The Underworld DCCLXXIII" />
    <Biome id="hell_774" name="The Underworld DCCLXXIV" />
    <Biome id="hell_775" name="The Underworld DCCLXXV" />
    <Biome id="hell_776" name="The Underworld DCCLXXVI" />
    <Biome id="hell_777" name="The Underworld DCCLXXVII" />
    <Biome id="hell_778" name="The Underworld DCCLXXVIII" />
    <Biome id="hell_779" name="The Underworld DCCLXXIX" />
    <Biome id="hell_780" name="The Underworld DCCLXXX" />
    <Biome id="hell_781" name="The Underworld DCCLXXXI" />
    <Biome id="hell_782" name="The Underworld DCCLXXXII" />
    <Biome id="hell_783" name="The Underworld DCCLXXXIII" />
    <Biome id="hell_784" name="The Underworld DCCLXXXIV" />
    <Biome id="hell_785" name="The Underworld DCCLXXXV" />
    <Biome id="hell_786" name="The Underworld DCCLXXXVI" />
    <Biome id="hell_787" name="The Underworld DCCLXXXVII" />
    <Biome id="hell_788" name="The Underworld DCCLXXXVIII" />
    <Biome id="hell_789" name="The Underworld DCCLXXXIX" />
    <Biome id="hell_790" name="The Underworld DCCXC" />
    <Biome id="hell_791" name="The Underworld DCCXCI" />
    <Biome id="hell_792" name="The Underworld DCCXCII" />
    <Biome id="hell_793" name="The Underworld DCCXCIII" />
    <Biome id="hell_794" name="The Underworld DCCXCIV" />
    <Biome id="hell_795" name="The Underworld DCCXCV" />
    <Biome id="hell_796" name="The Underworld DCCXCVI" />
    <Biome id="hell_797" name="The Underworld DCCXCVII" />
    <Biome id="hell_798" name="The Underworld DCCXCVIII" />
    <Biome id="hell_799" name="The Underworld DCCXCIX" />
    <Biome id="hell_800" name="The Underworld DCCC" />
    <Biome id="hell_801" name="The Underworld DCCI" />
    <Biome id="hell_802" name="The Underworld DCCII" />
    <Biome id="hell_803" name="The Underworld DCCIII" />
    <Biome id="hell_804" name="The Underworld DCCIV" />
    <Biome id="hell_805" name="The Underworld DCCV" />
    <Biome id="hell_806" name="The Underworld DCCVI" />
    <Biome id="hell_807" name="The Underworld DCCVII" />
    <Biome id="hell_808" name="The Underworld DCCVIII" />
    <Biome id="hell_809" name="The Underworld DCCIX" />
    <Biome id="hell_810" name="The Underworld DCCX" />
    <Biome id="hell_811" name="The Underworld DCCXI" />
    <Biome id="hell_812" name="The Underworld DCCXII" />
    <Biome id="hell_813" name="The Underworld DCCXIII" />
    <Biome id="hell_814" name="The Underworld DCCXIV" />
    <Biome id="hell_815" name="The Underworld DCCXV" />
    <Biome id="hell_816" name="The Underworld DCCXVI" />
    <Biome id="hell_817" name="The Underworld DCCXVII" />
    <Biome id="hell_818" name="The Underworld DCCXVIII" />
    <Biome id="hell_819" name="The Underworld DCCXIX" />
    <Biome id="hell_820" name="The Underworld DCCXX" />
    <Biome id="hell_821" name="The Underworld DCCXXI" />
    <Biome id="hell_822" name="The Underworld DCCXXII" />
    <Biome id="hell_823" name="The Underworld DCCXXIII" />
    <Biome id="hell_824" name="The Underworld DCCXXIV" />
    <Biome id="hell_825" name="The Underworld DCCXXV" />
    <Biome id="hell_826" name="The Underworld DCCXXVI" />
    <Biome id="hell_827" name="The Underworld DCCXXVII" />
    <Biome id="hell_828" name="The Underworld DCCXXVIII" />
    <Biome id="hell_829" name="The Underworld DCCXXIX" />
    <Biome id="hell_830" name="The Underworld DCCXXX" />
    <Biome id="hell_831" name="The Underworld DCCXXXI" />
    <Biome id="hell_832" name="The Underworld DCCXXXII" />
    <Biome id="hell_833" name="The Underworld DCCXXXIII" />
    <Biome id="hell_834" name="The Underworld DCCXXXIV" />
    <Biome id="hell_835" name="The Underworld DCCXXXV" />
    <Biome id="hell_836" name="The Underworld DCCXXXVI" />
    <Biome id="hell_837" name="The Underworld DCCXXXVII" />
    <Biome id="hell_838" name="The Underworld DCCXXXVIII" />
    <Biome id="hell_839" name="The Underworld DCCXXXIX" />
    <Biome id="hell_840" name="The Underworld DCCXL" />
    <Biome id="hell_841" name="The Underworld DCCXLI" />
    <Biome id="hell_842" name="The Underworld DCCXLII" />
    <Biome id="hell_843" name="The Underworld DCCXLIII" />
    <Biome id="hell_844" name="The Underworld DCCXLIV" />
    <Biome id="hell_845" name="The Underworld DCCXLV" />
    <Biome id="hell_846" name="The Underworld DCCXLVI" />
    <Biome id="hell_847" name="The Underworld DCCXLVII" />
    <Biome id="hell_848" name="The Underworld DCCXLVIII" />
    <Biome id="hell_849" name="The Underworld DCCXLIX" />
    <Biome id="hell_850" name="The Underworld DCCL" />
    <Biome id="hell_851" name="The Underworld DCCLI" />
    <Biome id="hell_852" name="The Underworld DCCLII" />
    <Biome id="hell_853" name="The Underworld DCCLIII" />
    <Biome id="hell_854" name="The Underworld DCCLIV" />
    <Biome id="hell_855" name="The Underworld DCCLV" />
    <Biome id="hell_856" name="The Underworld DCCLVI" />
    <Biome id="hell_857" name="The Underworld DCCLVII" />
    <Biome id="hell_858" name="The Underworld DCCLVIII" />
    <Biome id="hell_859" name="The Underworld DCCLIX" />
    <Biome id="hell_860" name="The Underworld DCCLX" />
    <Biome id="hell_861" name="The Underworld DCCLXI" />
    <Biome id="hell_862" name="The Underworld DCCLXII" />
    <Biome id="hell_863" name="The Underworld DCCLXIII" />
    <Biome id="hell_864" name="The Underworld DCCLXIV" />
    <Biome id="hell_865" name="The Underworld DCCLXv" />
    <Biome id="hell_866" name="The Underworld DCCLXVI" />
    <Biome id="hell_867" name="The Underworld DCCLXVII" />
    <Biome id="hell_868" name="The Underworld DCCLXVIII" />
    <Biome id="hell_869" name="The Underworld DCCLXIX" />
    <Biome id="hell_870" name="The Underworld DCCLXX" />
    <Biome id="hell_871" name="The Underworld DCCLXXI" />
    <Biome id="hell_872" name="The Underworld DCCLXXII" />
    <Biome id="hell_873" name="The Underworld DCCLXXIII" />
    <Biome id="hell_874" name="The Underworld DCCLXXIV" />
    <Biome id="hell_875" name="The Underworld DCCLXXV" />
    <Biome id="hell_876" name="The Underworld DCCLXXVI" />
    <Biome id="hell_877" name="The Underworld DCCLXXVII" />
    <Biome id="hell_878" name="The Underworld DCCLXXVIII" />
    <Biome id="hell_879" name="The Underworld DCCLXXIX" />
    <Biome id="hell_880" name="The Underworld DCCLXXX" />
    <Biome id="hell_881" name="The Underworld DCCLXXXI" />
    <Biome id="hell_882" name="The Underworld DCCLXXXII" />
    <Biome id="hell_883" name="The Underworld DCCLXXXIII" />
    <Biome id="hell_884" name="The Underworld DCCLXXXIV" />
    <Biome id="hell_885" name="The Underworld DCCLXXXV" />
    <Biome id="hell_886" name="The Underworld DCCLXXXVI" />
    <Biome id="hell_887" name="The Underworld DCCLXXXVII" />
    <Biome id="hell_888" name="The Underworld DCCLXXXVIII" />
    <Biome id="hell_889" name="The Underworld DCCLXXXIX" />
    <Biome id="hell_890" name="The Underworld DCCXC" />
    <Biome id="hell_891" name="The Underworld DCCXCI" />
    <Biome id="hell_892" name="The Underworld DCCXCII" />
    <Biome id="hell_893" name="The Underworld DCCXCIII" />
    <Biome id="hell_894" name="The Underworld DCCXCIV" />
    <Biome id="hell_895" name="The Underworld DCCXCV" />
    <Biome id="hell_896" name="The Underworld DCCXCVI" />
    <Biome id="hell_897" name="The Underworld DCCXCVII" />
    <Biome id="hell_898" name="The Underworld DCCXCVIII" />
    <Biome id="hell_899" name="The Underworld DCCXCIX" />
    <Biome id="hell_900" name="The Underworld DCCC" />
    <Biome id="hell_901" name="The Underworld DCCI" />
    <Biome id="hell_902" name="The Underworld DCCII" />
    <Biome id="hell_903" name="The Underworld DCCIII" />
    <Biome id="hell_904" name="The Underworld DCCIV" />
    <Biome id="hell_905" name="The Underworld DCCV" />
    <Biome id="hell_906" name="The Underworld DCCVI" />
    <Biome id="hell_907" name="The Underworld DCCVII" />
    <Biome id="hell_908" name="The Underworld DCCVIII" />
    <Biome id="hell_909" name="The Underworld DCCIX" />
    <Biome id="hell_910" name="The Underworld DCCX" />
    <Biome id="hell_911" name="The Underworld DCCXI" />
    <Biome id="hell_912" name="The Underworld DCCXII" />
    <Biome id="hell_913" name="The Underworld DCCXIII" />
    <Biome id="hell_914" name="The Underworld DCCXIV" />
    <Biome id="hell_915" name="The Underworld DCCXV" />
    <Biome id="hell_916" name="The Underworld DCCXVI" />
    <Biome id="hell_917" name="The Underworld DCCXVII" />
    <Biome id="hell_918" name="The Underworld DCCXVIII" />
    <Biome id="hell_919" name="The Underworld DCCXIX" />
    <Biome id="hell_920" name="The Underworld DCCXX" />
    <Biome id="hell_921" name="The Underworld DCCXXI" />
    <Biome id="hell_922" name="The Underworld DCCXXII" />
    <Biome id="hell_923" name="The Underworld DCCXXIII" />
    <Biome id="hell_924" name="The Underworld DCCXXIV" />
    <Biome id="hell_925" name="The Underworld DCCXXV" />
    <Biome id="hell_926" name="The Underworld DCCXXVI" />
    <Biome id="hell_927" name="The Underworld DCCXXVII" />
    <Biome id="hell_928" name="The Underworld DCCXXVIII" />
    <Biome id="hell_929" name="The Underworld DCCXXIX" />
    <Biome id="hell_930" name="The Underworld DCCXXX" />
    <Biome id="hell_931" name="The Underworld DCCXXXI" />
    <Biome id="hell_932" name="The Underworld DCCXXXII" />
    <Biome id="hell_933" name="The Underworld DCCXXXIII" />
    <Biome id="hell_934" name="The Underworld DCCXXXIV" />
    <Biome id="hell_935" name="The Underworld DCCXXXV" />
    <Biome id="hell_936" name="The Underworld DCCXXXVI" />
    <Biome id="hell_937" name="The Underworld DCCXXXVII" />
    <Biome id="hell_938" name="The Underworld DCCXXXVIII" />
    <Biome id="hell_939" name="The Underworld DCCXXXIX" />
    <Biome id="hell_940" name="The Underworld DCCXL" />
    <Biome id="hell_941" name="The Underworld DCCXLI" />
    <Biome id="hell_942" name="The Underworld DCCXLII" />
    <Biome id="hell_943" name="The Underworld DCCXLIII" />
    <Biome id="hell_944" name="The Underworld DCCXLIV" />
    <Biome id="hell_945" name="The Underworld DCCXLV" />
    <Biome id="hell_946" name="The Underworld DCCXLVI" />
    <Biome id="hell_947" name="The Underworld DCCXLVII" />
    <Biome id="hell_948" name="The Underworld DCCXLVIII" />
    <Biome id="hell_949" name="The Underworld DCCXLIX" />
    <Biome id="hell_950" name="The Underworld DCCL" />
    <Biome id="hell_951" name="The Underworld DCCLI" />
    <Biome id="hell_952" name="The Underworld DCCLII" />
    <Biome id="hell_953" name="The Underworld DCCLIII" />
    <Biome id="hell_954" name="The Underworld DCCLIV" />
    <Biome id="hell_955" name="The Underworld DCCLV" />
    <Biome id="hell_956" name="The Underworld DCCLVI" />
    <Biome id="hell_957" name="The Underworld DCCLVII" />
    <Biome id="hell_958" name="The Underworld DCCLVIII" />
    <Biome id="hell_959" name="The Underworld DCCLIX" />
    <Biome id="hell_960" name="The Underworld DCCLX" />
    <Biome id="hell_961" name="The Underworld DCCLXI" />
    <Biome id="hell_962" name="The Underworld DCCLXII" />
    <Biome id="hell_963" name="The Underworld DCCLXIII" />
    <Biome id="hell_964" name="The Underworld DCCLXIV" />
    <Biome id="hell_965" name="The Underworld DCCLXv" />
    <Biome id="hell_966" name="The Underworld DCCLXVI" />
    <Biome id="hell_967" name="The Underworld DCCLXVII" />
    <Biome id="hell_968" name="The Underworld DCCLXVIII" />
    <Biome id="hell_969" name="The Underworld DCCLXIX" />
    <Biome id="hell_970" name="The Underworld DCCLXX" />
    <Biome id="hell_971" name="The Underworld DCCLXXI" />
    <Biome id="hell_972" name="The Underworld DCCLXXII" />
    <Biome id="hell_973" name="The Underworld DCCLXXIII" />
    <Biome id="hell_974" name="The Underworld DCCLXXIV" />
    <Biome id="hell_975" name="The Underworld DCCLXXV" />
    <Biome id="hell_976" name="The Underworld DCCLXXVI" />
    <Biome id="hell_977" name="The Underworld DCCLXXVII" />
    <Biome id="hell_978" name="The Underworld DCCLXXVIII" />
    <Biome id="hell_979" name="The Underworld DCCLXXIX" />
    <Biome id="hell_980" name="The Underworld DCCLXXX" />
    <Biome id="hell_981" name="The Underworld DCCLXXXI" />
    <Biome id="hell_982" name="The Underworld DCCLXXXII" />
    <Biome id="hell_983" name="The Underworld DCCLXXXIII" />
    <Biome id="hell_984" name="The Underworld DCCLXXXIV" />
    <Biome id="hell_985" name="The Underworld DCCLXXXV" />
    <Biome id="hell_986" name="The Underworld DCCLXXXVI" />
    <Biome id="hell_987" name="The Underworld DCCLXXXVII" />
    <Biome id="hell_988" name="The Underworld DCCLXXXVIII" />
    <Biome id="hell_989" name="The Underworld DCCLXXXIX" />
    <Biome id="hell_990" name="The Underworld DCCXC" />
    <Biome id="hell_991" name="The Underworld DCCXCI" />
    <Biome id="hell_992" name="The Underworld DCCXCII" />
    <Biome id="hell_993" name="The Underworld DCCXCIII" />
    <Biome id="hell_994" name="The Underworld DCCXCIV" />
    <Biome id="hell_995" name="The Underworld DCCXCV" />
    <Biome id="hell_996" name="The Underworld DCCXCVI" />
    <Biome id="hell_997" name="The Underworld DCCXCVII" />
    <Biome id="hell_998" name="The Underworld DCCXCVIII" />
    <Biome id="hell_999" name="The Underworld DCCXCIX" />
    <Biome id="hell_1000" name="The Underworld M" />
</BiomeMapping>
```

### `biome_id_override`

This property allows you to specify a biome ID that should be considered active, overriding the default biome detection. This can be useful for testing or forcing specific biome states.

**Example XML:**

```xml
<BiomeTrackerComponent
    biome_id_override="forest"
    ...
/>
```

### `biome_trigger_on_enter`

When set to `true`, this property causes the `BiomeTrackerComponent` to trigger events or actions when the player enters a new biome.

**Example XML:**

```xml
<BiomeTrackerComponent
    biome_trigger_on_enter="true"
    ...
/>
```

### `biome_trigger_on_exit`

When set to `true`, this property causes the `BiomeTrackerComponent` to trigger events or actions when the player exits a biome.

**Example XML:**

```xml
<BiomeTrackerComponent
    biome_trigger_on_exit="true"
    ...
/>
```

### `biome_trigger_on_discovery`

When set to `true`, this property causes the `BiomeTrackerComponent` to trigger events or actions when the player *discovers* a biome for the first time. This is distinct from simply entering it.

**Example XML:**

```xml
<BiomeTrackerComponent
    biome_trigger_on_discovery="true"
    ...
/>
```

## Lua API Integration

The `BiomeTrackerComponent` can be interacted with and queried using Lua scripting. This allows for dynamic mod behavior based on biome tracking.

### Accessing the Component

You can get a reference to the `BiomeTrackerComponent` of an entity using the `GetComponent` function from the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

**Example Lua:**

```lua
local biome_tracker = entity:GetComponent("BiomeTrackerComponent")
if biome_tracker then
    -- Interact with the biome_tracker
end
```

### Key Lua Functions

While the specific Lua functions for direct interaction with `BiomeTrackerComponent` might not be extensively documented in the original source, common patterns suggest functions for:

*   **`IsBiomeDiscovered(biome_id)`**: Checks if a specific biome has been discovered by the player.
*   **`DiscoverBiome(biome_id)`**: Marks a biome as discovered.
*   **`GetCurrentBiome()`**: Returns the ID of the biome the player is currently in.
*   **`GetAllDiscoveredBiomes()`**: Returns a list of all biome IDs that have been discovered.

**Note:** The exact function names and their availability may vary. Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for the most up-to-date information.

## Modding Use Cases

The `BiomeTrackerComponent` is invaluable for several modding scenarios:

*   **Progression Gates**: Create areas or items that only become accessible after the player has discovered specific biomes.
*   **Custom Biome Events**: Trigger unique events, encounters, or environmental changes when the player enters or exits custom-designed biomes.
*   **Lore and Storytelling**: Uncover lore entries or trigger narrative events based on the player's exploration progress.
*   **Player Statistics**: Track and display statistics related to biome discovery for players.
*   **Dynamic Difficulty**: Adjust game difficulty or enemy types based on the number of biomes discovered.

## Related Components and Concepts

*   **Biome Generation**: Understanding how biomes are defined and generated is crucial for creating custom biomes that the `BiomeTrackerComponent` can track.
*   **Entity Components**: The `BiomeTrackerComponent` is one of many components that can be attached to entities in Noita.
*   **Event System**: Mods can hook into game events triggered by biome changes to implement custom logic.

## Further Information

*   [Modding:Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Modding:Components](https://noita.wiki.gg/wiki/Modding:_Components)
*   [Modding:XML Documentation](https://noita.wiki.gg/wiki/Modding:_XML_Documentation)