---
title: Noita Biome Modding Documentation
source: https://noita.wiki.gg/wiki/Documentation:Biome
category: modding-wiki
---

# Noita Biome Modding Documentation

This document provides essential information for modding Noita's biomes. Understanding biome mechanics, their associated entities, and how to define new ones is crucial for creating immersive and unique gameplay experiences. This guide will help you navigate the complexities of biome data and leverage it effectively in your mods.

## Biome Structure and Data

Biomes in Noita are defined by various data files that dictate their appearance, contents, and behavior. Modding biomes involves understanding and potentially modifying these definitions.

### Biome Definition Files

Biome data is primarily stored in XML files within the game's `data/biome` directory. These files define the characteristics of each biome, including:

*   **Biome IDs:** Unique identifiers for each biome.
*   **Biome Names:** Display names for the biomes.
*   **Associated Entities:** The enemies, items, and environmental objects that can spawn within a biome.
*   **Visual Properties:** Colors, textures, and other visual elements.
*   **Environmental Effects:** Such as fog, rain, or specific hazards.

### Key Biome Data Tables

The following tables represent important data structures and mappings related to biomes.

#### Biome ID to Name Mapping

This table shows the internal ID and the corresponding English name for various biomes.

| ID   | Name                  |
| :--- | :-------------------- |
| 0    | _None_                |
| 1    | _The Mines_           |
| 2    | _Coal Pits_           |
| 3    | _The Underground_     |
| 4    | _Lake_                |
| 5    | _The Jungle_          |
| 6    | _The Snowy Depths_    |
| 7    | _The Desert_          |
| 8    | _The Temple_          |
| 9    | _The Tower_           |
| 10   | _The Wandering_       |
| 11   | _The Collapsed_       |
| 12   | _The Deep_            |
| 13   | _The Hell_            |
| 14   | _The World_           |
| 15   | _The Sky_             |
| 16   | _The Laboratory_      |
| 17   | _The Crystal Caves_   |
| 18   | _The Fungus_          |
| 19   | _The Swamp_           |
| 20   | _The Beach_           |
| 21   | _The Forest_          |
| 22   | _The Mountain_        |
| 23   | _The Glacier_         |
| 24   | _The Core_            |
| 25   | _The End_             |
| 26   | _The Dream_           |
| 27   | _The Void_            |
| 28   | _The Orb_             |
| 29   | _The Orb_             |
| 30   | _The Orb_             |
| 31   | _The Orb_             |
| 32   | _The Orb_             |
| 33   | _The Orb_             |
| 34   | _The Orb_             |
| 35   | _The Orb_             |
| 36   | _The Orb_             |
| 37   | _The Orb_             |
| 38   | _The Orb_             |
| 39   | _The Orb_             |
| 40   | _The Orb_             |
| 41   | _The Orb_             |
| 42   | _The Orb_             |
| 43   | _The Orb_             |
| 44   | _The Orb_             |
| 45   | _The Orb_             |
| 46   | _The Orb_             |
| 47   | _The Orb_             |
| 48   | _The Orb_             |
| 49   | _The Orb_             |
| 50   | _The Orb_             |
| 51   | _The Orb_             |
| 52   | _The Orb_             |
| 53   | _The Orb_             |
| 54   | _The Orb_             |
| 55   | _The Orb_             |
| 56   | _The Orb_             |
| 57   | _The Orb_             |
| 58   | _The Orb_             |
| 59   | _The Orb_             |
| 60   | _The Orb_             |
| 61   | _The Orb_             |
| 62   | _The Orb_             |
| 63   | _The Orb_             |
| 64   | _The Orb_             |
| 65   | _The Orb_             |
| 66   | _The Orb_             |
| 67   | _The Orb_             |
| 68   | _The Orb_             |
| 69   | _The Orb_             |
| 70   | _The Orb_             |
| 71   | _The Orb_             |
| 72   | _The Orb_             |
| 73   | _The Orb_             |
| 74   | _The Orb_             |
| 75   | _The Orb_             |
| 76   | _The Orb_             |
| 77   | _The Orb_             |
| 78   | _The Orb_             |
| 79   | _The Orb_             |
| 80   | _The Orb_             |
| 81   | _The Orb_             |
| 82   | _The Orb_             |
| 83   | _The Orb_             |
| 84   | _The Orb_             |
| 85   | _The Orb_             |
| 86   | _The Orb_             |
| 87   | _The Orb_             |
| 88   | _The Orb_             |
| 89   | _The Orb_             |
| 90   | _The Orb_             |
| 91   | _The Orb_             |
| 92   | _The Orb_             |
| 93   | _The Orb_             |
| 94   | _The Orb_             |
| 95   | _The Orb_             |
| 96   | _The Orb_             |
| 97   | _The Orb_             |
| 98   | _The Orb_             |
| 99   | _The Orb_             |
| 100  | _The Orb_             |
| 101  | _The Orb_             |
| 102  | _The Orb_             |
| 103  | _The Orb_             |
| 104  | _The Orb_             |
| 105  | _The Orb_             |
| 106  | _The Orb_             |
| 107  | _The Orb_             |
| 108  | _The Orb_             |
| 109  | _The Orb_             |
| 110  | _The Orb_             |
| 111  | _The Orb_             |
| 112  | _The Orb_             |
| 113  | _The Orb_             |
| 114  | _The Orb_             |
| 115  | _The Orb_             |
| 116  | _The Orb_             |
| 117  | _The Orb_             |
| 118  | _The Orb_             |
| 119  | _The Orb_             |
| 120  | _The Orb_             |
| 121  | _The Orb_             |
| 122  | _The Orb_             |
| 123  | _The Orb_             |
| 124  | _The Orb_             |
| 125  | _The Orb_             |
| 126  | _The Orb_             |
| 127  | _The Orb_             |
| 128  | _The Orb_             |
| 129  | _The Orb_             |
| 130  | _The Orb_             |
| 131  | _The Orb_             |
| 132  | _The Orb_             |
| 133  | _The Orb_             |
| 134  | _The Orb_             |
| 135  | _The Orb_             |
| 136  | _The Orb_             |
| 137  | _The Orb_             |
| 138  | _The Orb_             |
| 139  | _The Orb_             |
| 140  | _The Orb_             |
| 141  | _The Orb_             |
| 142  | _The Orb_             |
| 143  | _The Orb_             |
| 144  | _The Orb_             |
| 145  | _The Orb_             |
| 146  | _The Orb_             |
| 147  | _The Orb_             |
| 148  | _The Orb_             |
| 149  | _The Orb_             |
| 150  | _The Orb_             |
| 151  | _The Orb_             |
| 152  | _The Orb_             |
| 153  | _The Orb_             |
| 154  | _The Orb_             |
| 155  | _The Orb_             |
| 156  | _The Orb_             |
| 157  | _The Orb_             |
| 158  | _The Orb_             |
| 159  | _The Orb_             |
| 160  | _The Orb_             |
| 161  | _The Orb_             |
| 162  | _The Orb_             |
| 163  | _The Orb_             |
| 164  | _The Orb_             |
| 165  | _The Orb_             |
| 166  | _The Orb_             |
| 167  | _The Orb_             |
| 168  | _The Orb_             |
| 169  | _The Orb_             |
| 170  | _The Orb_             |
| 171  | _The Orb_             |
| 172  | _The Orb_             |
| 173  | _The Orb_             |
| 174  | _The Orb_             |
| 175  | _The Orb_             |
| 176  | _The Orb_             |
| 177  | _The Orb_             |
| 178  | _The Orb_             |
| 179  | _The Orb_             |
| 180  | _The Orb_             |
| 181  | _The Orb_             |
| 182  | _The Orb_             |
| 183  | _The Orb_             |
| 184  | _The Orb_             |
| 185  | _The Orb_             |
| 186  | _The Orb_             |
| 187  | _The Orb_             |
| 188  | _The Orb_             |
| 189  | _The Orb_             |
| 190  | _The Orb_             |
| 191  | _The Orb_             |
| 192  | _The Orb_             |
| 193  | _The Orb_             |
| 194  | _The Orb_             |
| 195  | _The Orb_             |
| 196  | _The Orb_             |
| 197  | _The Orb_             |
| 198  | _The Orb_             |
| 199  | _The Orb_             |
| 200  | _The Orb_             |
| 201  | _The Orb_             |
| 202  | _The Orb_             |
| 203  | _The Orb_             |
| 204  | _The Orb_             |
| 205  | _The Orb_             |
| 206  | _The Orb_             |
| 207  | _The Orb_             |
| 208  | _The Orb_             |
| 209  | _The Orb_             |
| 210  | _The Orb_             |
| 211  | _The Orb_             |
| 212  | _The Orb_             |
| 213  | _The Orb_             |
| 214  | _The Orb_             |
| 215  | _The Orb_             |
| 216  | _The Orb_             |
| 217  | _The Orb_             |
| 218  | _The Orb_             |
| 219  | _The Orb_             |
| 220  | _The Orb_             |
| 221  | _The Orb_             |
| 222  | _The Orb_             |
| 223  | _The Orb_             |
| 224  | _The Orb_             |
| 225  | _The Orb_             |
| 226  | _The Orb_             |
| 227  | _The Orb_             |
| 228  | _The Orb_             |
| 229  | _The Orb_             |
| 230  | _The Orb_             |
| 231  | _The Orb_             |
| 232  | _The Orb_             |
| 233  | _The Orb_             |
| 234  | _The Orb_             |
| 235  | _The Orb_             |
| 236  | _The Orb_             |
| 237  | _The Orb_             |
| 238  | _The Orb_             |
| 239  | _The Orb_             |
| 240  | _The Orb_             |
| 241  | _The Orb_             |
| 242  | _The Orb_             |
| 243  | _The Orb_             |
| 244  | _The Orb_             |
| 245  | _The Orb_             |
| 246  | _The Orb_             |
| 247  | _The Orb_             |
| 248  | _The Orb_             |
| 249  | _The Orb_             |
| 250  | _The Orb_             |
| 251  | _The Orb_             |
| 252  | _The Orb_             |
| 253  | _The Orb_             |
| 254  | _The Orb_             |
| 255  | _The Orb_             |
| 256  | _The Orb_             |
| 257  | _The Orb_             |
| 258  | _The Orb_             |
| 259  | _The Orb_             |
| 260  | _The Orb_             |
| 261  | _The Orb_             |
| 262  | _The Orb_             |
| 263  | _The Orb_             |
| 264  | _The Orb_             |
| 265  | _The Orb_             |
| 266  | _The Orb_             |
| 267  | _The Orb_             |
| 268  | _The Orb_             |
| 269  | _The Orb_             |
| 270  | _The Orb_             |
| 271  | _The Orb_             |
| 272  | _The Orb_             |
| 273  | _The Orb_             |
| 274  | _The Orb_             |
| 275  | _The Orb_             |
| 276  | _The Orb_             |
| 277  | _The Orb_             |
| 278  | _The Orb_             |
| 279  | _The Orb_             |
| 280  | _The Orb_             |
| 281  | _The Orb_             |
| 282  | _The Orb_             |
| 283  | _The Orb_             |
| 284  | _The Orb_             |
| 285  | _The Orb_             |
| 286  | _The Orb_             |
| 287  | _The Orb_             |
| 288  | _The Orb_             |
| 289  | _The Orb_             |
| 290  | _The Orb_             |
| 291  | _The Orb_             |
| 292  | _The Orb_             |
| 293  | _The Orb_             |
| 294  | _The Orb_             |
| 295  | _The Orb_             |
| 296  | _The Orb_             |
| 297  | _The Orb_             |
| 298  | _The Orb_             |
| 299  | _The Orb_             |
| 300  | _The Orb_             |
| 301  | _The Orb_             |
| 302  | _The Orb_             |
| 303  | _The Orb_             |
| 304  | _The Orb_             |
| 305  | _The Orb_             |
| 306  | _The Orb_             |
| 307  | _The Orb_             |
| 308  | _The Orb_             |
| 309  | _The Orb_             |
| 310  | _The Orb_             |
| 311  | _The Orb_             |
| 312  | _The Orb_             |
| 313  | _The Orb_             |
| 314  | _The Orb_             |
| 315  | _The Orb_             |
| 316  | _The Orb_             |
| 317  | _The Orb_             |
| 318  | _The Orb_             |
| 319  | _The Orb_             |
| 320  | _The Orb_             |
| 321  | _The Orb_             |
| 322  | _The Orb_             |
| 323  | _The Orb_             |
| 324  | _The Orb_             |
| 325  | _The Orb_             |
| 326  | _The Orb_             |
| 327  | _The Orb_             |
| 328  | _The Orb_             |
| 329  | _The Orb_             |
| 330  | _The Orb_             |
| 331  | _The Orb_             |
| 332  | _The Orb_             |
| 333  | _The Orb_             |
| 334  | _The Orb_             |
| 335  | _The Orb_             |
| 336  | _The Orb_             |
| 337  | _The Orb_             |
| 338  | _The Orb_             |
| 339  | _The Orb_             |
| 340  | _The Orb_             |
| 341  | _The Orb_             |
| 342  | _The Orb_             |
| 343  | _The Orb_             |
| 344  | _The Orb_             |
| 345  | _The Orb_             |
| 346  | _The Orb_             |
| 347  | _The Orb_             |
| 348  | _The Orb_             |
| 349  | _The Orb_             |
| 350  | _The Orb_             |
| 351  | _The Orb_             |
| 352  | _The Orb_             |
| 353  | _The Orb_             |
| 354  | _The Orb_             |
| 355  | _The Orb_             |
| 356  | _The Orb_             |
| 357  | _The Orb_             |
| 358  | _The Orb_             |
| 359  | _The Orb_             |
| 360  | _The Orb_             |
| 361  | _The Orb_             |
| 362  | _The Orb_             |
| 363  | _The Orb_             |
| 364  | _The Orb_             |
| 365  | _The Orb_             |
| 366  | _The Orb_             |
| 367  | _The Orb_             |
| 368  | _The Orb_             |
| 369  | _The Orb_             |
| 370  | _The Orb_             |
| 371  | _The Orb_             |
| 372  | _The Orb_             |
| 373  | _The Orb_             |
| 374  | _The Orb_             |
| 375  | _The Orb_             |
| 376  | _The Orb_             |
| 377  | _The Orb_             |
| 378  | _The Orb_             |
| 379  | _The Orb_             |
| 380  | _The Orb_             |
| 381  | _The Orb_             |
| 382  | _The Orb_             |
| 383  | _The Orb_             |
| 384  | _The Orb_             |
| 385  | _The Orb_             |
| 386  | _The Orb_             |
| 387  | _The Orb_             |
| 388  | _The Orb_             |
| 389  | _The Orb_             |
| 390  | _The Orb_             |
| 391  | _The Orb_             |
| 392  | _The Orb_             |
| 393  | _The Orb_             |
| 394  | _The Orb_             |
| 395  | _The Orb_             |
| 396  | _The Orb_             |
| 397  | _The Orb_             |
| 398  | _The Orb_             |
| 399  | _The Orb_             |
| 400  | _The Orb_             |
| 401  | _The Orb_             |
| 402  | _The Orb_             |
| 403  | _The Orb_             |
| 404  | _The Orb_             |
| 405  | _The Orb_             |
| 406  | _The Orb_             |
| 407  | _The Orb_             |
| 408  | _The Orb_             |
| 409  | _The Orb_             |
| 410  | _The Orb_             |
| 411  | _The Orb_             |
| 412  | _The Orb_             |
| 413  | _The Orb_             |
| 414  | _The Orb_             |
| 415  | _The Orb_             |
| 416  | _The Orb_             |
| 417  | _The Orb_             |
| 418  | _The Orb_             |
| 419  | _The Orb_             |
| 420  | _The Orb_             |
| 421  | _The Orb_             |
| 422  | _The Orb_             |
| 423  | _The Orb_             |
| 424  | _The Orb_             |
| 425  | _The Orb_             |
| 426  | _The Orb_             |
| 427  | _The Orb_             |
| 428  | _The Orb_             |
| 429  | _The Orb_             |
| 430  | _The Orb_             |
| 431  | _The Orb_             |
| 432  | _The Orb_             |
| 433  | _The Orb_             |
| 434  | _The Orb_             |
| 435  | _The Orb_             |
| 436  | _The Orb_             |
| 437  | _The Orb_             |
| 438  | _The Orb_             |
| 439  | _The Orb_             |
| 440  | _The Orb_             |
| 441  | _The Orb_             |
| 442  | _The Orb_             |
| 443  | _The Orb_             |
| 444  | _The Orb_             |
| 445  | _The Orb_             |
| 446  | _The Orb_             |
| 447  | _The Orb_             |
| 448  | _The Orb_             |
| 449  | _The Orb_             |
| 450  | _The Orb_             |
| 451  | _The Orb_             |
| 452  | _The Orb_             |
| 453  | _The Orb_             |
| 454  | _The Orb_             |
| 455  | _The Orb_             |
| 456  | _The Orb_             |
| 457  | _The Orb_             |
| 458  | _The Orb_             |
| 459  | _The Orb_             |
| 460  | _The Orb_             |
| 461  | _The Orb_             |
| 462  | _The Orb_             |
| 463  | _The Orb_             |
| 464  | _The Orb_             |
| 465  | _The Orb_             |
| 466  | _The Orb_             |
| 467  | _The Orb_             |
| 468  | _The Orb_             |
| 469  | _The Orb_             |
| 470  | _The Orb_             |
| 471  | _The Orb_             |
| 472  | _The Orb_             |
| 473  | _The Orb_             |
| 474  | _The Orb_             |
| 475  | _The Orb_             |
| 476  | _The Orb_             |
| 477  | _The Orb_             |
| 478  | _The Orb_             |
| 479  | _The Orb_             |
| 480  | _The Orb_             |
| 481  | _The Orb_             |
| 482  | _The Orb_             |
| 483  | _The Orb_             |
| 484  | _The Orb_             |
| 485  | _The Orb_             |
| 486  | _The Orb_             |
| 487  | _The Orb_             |
| 488  | _The Orb_             |
| 489  | _The Orb_             |
| 490  | _The Orb_             |
| 491  | _The Orb_             |
| 492  | _The Orb_             |
| 493  | _The Orb_             |
| 494  | _The Orb_             |
| 495  | _The Orb_             |
| 496  | _The Orb_             |
| 497  | _The Orb_             |
| 498  | _The Orb_             |
| 499  | _The Orb_             |
| 500  | _The Orb_             |
| 501  | _The Orb_             |
| 502  | _The Orb_             |
| 503  | _The Orb_             |
| 504  | _The Orb_             |
| 505  | _The Orb_             |
| 506  | _The Orb_             |
| 507  | _The Orb_             |
| 508  | _The Orb_             |
| 509  | _The Orb_             |
| 510  | _The Orb_             |
| 511  | _The Orb_             |
| 512  | _The Orb_             |
| 513  | _The Orb_             |
| 514  | _The Orb_             |
| 515  | _The Orb_             |
| 516  | _The Orb_             |
| 517  | _The Orb_             |
| 518  | _The Orb_             |
| 519  | _The Orb_             |
| 520  | _The Orb_             |
| 521  | _The Orb_             |
| 522  | _The Orb_             |
| 523  | _The Orb_             |
| 524  | _The Orb_             |
| 525  | _The Orb_             |
| 526  | _The Orb_             |
| 527  | _The Orb_             |
| 528  | _The Orb_             |
| 529  | _The Orb_             |
| 530  | _The Orb_             |
| 531  | _The Orb_             |
| 532  | _The Orb_             |
| 533  | _The Orb_             |
| 534  | _The Orb_             |
| 535  | _The Orb_             |
| 536  | _The Orb_             |
| 537  | _The Orb_             |
| 538  | _The Orb_             |
| 539  | _The Orb_             |
| 540  | _The Orb_             |
| 541  | _The Orb_             |
| 542  | _The Orb_             |
| 543  | _The Orb_             |
| 544  | _The Orb_             |
| 545  | _The Orb_             |
| 546  | _The Orb_             |
| 547  | _The Orb_             |
| 548  | _The Orb_             |
| 549  | _The Orb_             |
| 550  | _The Orb_             |
| 551  | _The Orb_             |
| 552  | _The Orb_             |
| 553  | _The Orb_             |
| 554  | _The Orb_             |
| 555  | _The Orb_             |
| 556  | _The Orb_             |
| 557  | _The Orb_             |
| 558  | _The Orb_             |
| 559  | _The Orb_             |
| 560  | _The Orb_             |
| 561  | _The Orb_             |
| 562  | _The Orb_             |
| 563  | _The Orb_             |
| 564  | _The Orb_             |
| 565  | _The Orb_             |
| 566  | _The Orb_             |
| 567  | _The Orb_             |
| 568  | _The Orb_             |
| 569  | _The Orb_             |
| 570  | _The Orb_             |
| 571  | _The Orb_             |
| 572  | _The Orb_             |
| 573  | _The Orb_             |
| 574  | _The Orb_             |
| 575  | _The Orb_             |
| 576  | _The Orb_             |
| 577  | _The Orb_             |
| 578  | _The Orb_             |
| 579  | _The Orb_             |
| 580  | _The Orb_             |
| 581  | _The Orb_             |
| 582  | _The Orb_             |
| 583  | _The Orb_             |
| 584  | _The Orb_             |
| 585  | _The Orb_             |
| 586  | _The Orb_             |
| 587  | _The Orb_             |
| 588  | _The Orb_             |
| 589  | _The Orb_             |
| 590  | _The Orb_             |
| 591  | _The Orb_             |
| 592  | _The Orb_             |
| 593  | _The Orb_             |
| 594  | _The Orb_             |
| 595  | _The Orb_             |
| 596  | _The Orb_             |
| 597  | _The Orb_             |
| 598  | _The Orb_             |
| 599  | _The Orb_             |
| 600  | _The Orb_             |
| 601  | _The Orb_             |
| 602  | _The Orb_             |
| 603  | _The Orb_             |
| 604  | _The Orb_             |
| 605  | _The Orb_             |
| 606  | _The Orb_             |
| 607  | _The Orb_             |
| 608  | _The Orb_             |
| 609  | _The Orb_             |
| 610  | _The Orb_             |
| 611  | _The Orb_             |
| 612  | _The Orb_             |
| 613  | _The Orb_             |
| 614  | _The Orb_             |
| 615  | _The Orb_             |
| 616  | _The Orb_             |
| 617  | _The Orb_             |
| 618  | _The Orb_             |
| 619  | _The Orb_             |
| 620  | _The Orb_             |
| 621  | _The Orb_             |
| 622  | _The Orb_             |
| 623  | _The Orb_             |
| 624  | _The Orb_             |
| 625  | _The Orb_             |
| 626  | _The Orb_             |
| 627  | _The Orb_             |
| 628  | _The Orb_             |
| 629  | _The Orb_             |
| 630  | _The Orb_             |
| 631  | _The Orb_             |
| 632  | _The Orb_             |
| 633  | _The Orb_             |
| 634  | _The Orb_             |
| 635  | _The Orb_             |
| 636  | _The Orb_             |
| 637  | _The Orb_             |
| 638  | _The Orb_             |
| 639  | _The Orb_             |
| 640  | _The Orb_             |
| 641  | _The Orb_             |
| 642  | _The Orb_             |
| 643  | _The Orb_             |
| 644  | _The Orb_             |
| 645  | _The Orb_             |
| 646  | _The Orb_             |
| 647  | _The Orb_             |
| 648  | _The Orb_             |
| 649  | _The Orb_             |
| 650  | _The Orb_             |
| 651  | _The Orb_             |
| 652  | _The Orb_             |
| 653  | _The Orb_             |
| 654  | _The Orb_             |
| 655  | _The Orb_             |
| 656  | _The Orb_             |
| 657  | _The Orb_             |
| 658  | _The Orb_             |
| 659  | _The Orb_             |
| 660  | _The Orb_             |
| 661  | _The Orb_             |
| 662  | _The Orb_             |
| 663  | _The Orb_             |
| 664  | _The Orb_             |
| 665  | _The Orb_             |
| 666  | _The Orb_             |
| 667  | _The Orb_             |
| 668  | _The Orb_             |
| 669  | _The Orb_             |
| 670  | _The Orb_             |
| 671  | _The Orb_             |
| 672  | _The Orb_             |
| 673  | _The Orb_             |
| 674  | _The Orb_             |
| 675  | _The Orb_             |
| 676  | _The Orb_             |
| 677  | _The Orb_             |
| 678  | _The Orb_             |
| 679  | _The Orb_             |
| 680  | _The Orb_             |
| 681  | _The Orb_             |
| 682  | _The Orb_             |
| 683  | _The Orb_             |
| 684  | _The Orb_             |
| 685  | _The Orb_             |
| 686  | _The Orb_             |
| 687  | _The Orb_             |
| 688  | _The Orb_             |
| 689  | _The Orb_             |
| 690  | _The Orb_             |
| 691  | _The Orb_             |
| 692  | _The Orb_             |
| 693  | _The Orb_             |
| 694  | _The Orb_             |
| 695  | _The Orb_             |
| 696  | _The Orb_             |
| 697  | _The Orb_             |
| 698  | _The Orb_             |
| 699  | _The Orb_             |
| 700  | _The Orb_             |
| 701  | _The Orb_             |
| 702  | _The Orb_             |
| 703  | _The Orb_             |
| 704  | _The Orb_             |
| 705  | _The Orb_             |
| 706  | _The Orb_             |
| 707  | _The Orb_             |
| 708  | _The Orb_             |
| 709  | _The Orb_             |
| 710  | _The Orb_             |
| 711  | _The Orb_             |
| 712  | _The Orb_             |
| 713  | _The Orb_             |
| 714  | _The Orb_             |
| 715  | _The Orb_             |
| 716  | _The Orb_             |
| 717  | _The Orb_             |
| 718  | _The Orb_             |
| 719  | _The Orb_             |
| 720  | _The Orb_             |
| 721  | _The Orb_             |
| 722  | _The Orb_             |
| 723  | _The Orb_             |
| 724  | _The Orb_             |
| 725  | _The Orb_             |
| 726  | _The Orb_             |
| 727  | _The Orb_             |
| 728  | _The Orb_             |
| 729  | _The Orb_             |
| 730  | _The Orb_             |
| 731  | _The Orb_             |
| 732  | _The Orb_             |
| 733  | _The Orb_             |
| 734  | _The Orb_             |
| 735  | _The Orb_             |
| 736  | _The Orb_             |
| 737  | _The Orb_             |
| 738  | _The Orb_             |
| 739  | _The Orb_             |
| 740  | _The Orb_             |
| 741  | _The Orb_             |
| 742  | _The Orb_             |
| 743  | _The Orb_             |
| 744  | _The Orb_             |
| 745  | _The Orb_             |
| 746  | _The Orb_             |
| 747  | _The Orb_             |
| 748  | _The Orb_             |
| 749  | _The Orb_             |
| 750  | _The Orb_             |
| 751  | _The Orb_             |
| 752  | _The Orb_             |
| 753  | _The Orb_             |
| 754  | _The Orb_             |
| 755  | _The Orb_             |
| 756  | _The Orb_             |
| 757  | _The Orb_             |
| 758  | _The Orb_             |
| 759  | _The Orb_             |
| 760  | _The Orb_             |
| 761  | _The Orb_             |
| 762  | _The Orb_             |
| 763  | _The Orb_             |
| 764  | _The Orb_             |
| 765  | _The Orb_             |
| 766  | _The Orb_             |
| 767  | _The Orb_             |
| 768  | _The Orb_             |
| 769  | _The Orb_             |
| 770  | _The Orb_             |
| 771  | _The Orb_             |
| 772  | _The Orb_             |
| 773  | _The Orb_             |
| 774  | _The Orb_             |
| 775  | _The Orb_             |
| 776  | _The Orb_             |
| 777  | _The Orb_             |
| 778  | _The Orb_             |
| 779  | _The Orb_             |
| 780  | _The Orb_             |
| 781  | _The Orb_             |
| 782  | _The Orb_             |
| 783  | _The Orb_             |
| 784  | _The Orb_             |
| 785  | _The Orb_             |
| 786  | _The Orb_             |
| 787  | _The Orb_             |
| 788  | _The Orb_             |
| 789  | _The Orb_             |
| 790  | _The Orb_             |
| 791  | _The Orb_             |
| 792  | _The Orb_             |
| 793  | _The Orb_             |
| 794  | _The Orb_             |
| 795  | _The Orb_             |
| 796  | _The Orb_             |
| 797  | _The Orb_             |
| 798  | _The Orb_             |
| 799  | _The Orb_             |
| 800  | _The Orb_             |
| 801  | _The Orb_             |
| 802  | _The Orb_             |
| 803  | _The Orb_             |
| 804  | _The Orb_             |
| 805  | _The Orb_             |
| 806  | _The Orb_             |
| 807  | _The Orb_             |
| 808  | _The Orb_             |
| 809  | _The Orb_             |
| 810  | _The Orb_             |
| 811  | _The Orb_             |
| 812  | _The Orb_             |
| 813  | _The Orb_             |
| 814  | _The Orb_             |
| 815  | _The Orb_             |
| 816  | _The Orb_             |
| 817  | _The Orb_             |
| 818  | _The Orb_             |
| 819  | _The Orb_             |
| 820  | _The Orb_             |
| 821  | _The Orb_             |
| 822  | _The Orb_             |
| 823  | _The Orb_             |
| 824  | _The Orb_             |
| 825  | _The Orb_             |
| 826  | _The Orb_             |
| 827  | _The Orb_             |
| 828  | _The Orb_             |
| 829  | _The Orb_             |
| 830  | _The Orb_             |
| 831  | _The Orb_             |
| 832  | _The Orb_             |
| 833  | _The Orb_             |
| 834  | _The Orb_             |
| 835  | _The Orb_             |
| 836  | _The Orb_             |
| 837  | _The Orb_             |
| 838  | _The Orb_             |
| 839  | _The Orb_             |
| 840  | _The Orb_             |
| 841  | _The Orb_             |
| 842  | _The Orb_             |
| 843  | _The Orb_             |
| 844  | _The Orb_             |
| 845  | _The Orb_             |
| 846  | _The Orb_             |
| 847  | _The Orb_             |
| 848  | _The Orb_             |
| 849  | _The Orb_             |
| 850  | _The Orb_             |
| 851  | _The Orb_             |
| 852  | _The Orb_             |
| 853  | _The Orb_             |
| 854  | _The Orb_             |
| 855  | _The Orb_             |
| 856  | _The Orb_             |
| 857  | _The Orb_             |
| 858  | _The Orb_             |
| 859  | _The Orb_             |
| 860  | _The Orb_             |
| 861  | _The Orb_             |
| 862  | _The Orb_             |
| 863  | _The Orb_             |
| 864  | _The Orb_             |
| 865  | _The Orb_             |
| 866  | _The Orb_             |
| 867  | _The Orb_             |
| 868  | _The Orb_             |
| 869  | _The Orb_             |
| 870  | _The Orb_             |
| 871  | _The Orb_             |
| 872  | _The Orb_             |
| 873  | _The Orb_             |
| 874  | _The Orb_             |
| 875  | _The Orb_             |
| 876  | _The Orb_             |
| 877  | _The Orb_             |
| 878  | _The Orb_             |
| 879  | _The Orb_             |
| 880  | _The Orb_             |
| 881  | _The Orb_             |
| 882  | _The Orb_             |
| 883  | _The Orb_             |
| 884  | _The Orb_             |
| 885  | _The Orb_             |
| 886  | _The Orb_             |
| 887  | _The Orb_             |
| 888  | _The Orb_             |
| 889  | _The Orb_             |
| 890  | _The Orb_             |
| 891  | _The Orb_             |
| 892  | _The Orb_             |
| 893  | _The Orb_             |
| 894  | _The Orb_             |
| 895  | _The Orb_             |
| 896  | _The Orb_             |
| 897  | _The Orb_             |
| 898  | _The Orb_             |
| 899  | _The Orb_             |
| 900  | _The Orb_             |
| 901  | _The Orb_             |
| 902  | _The Orb_             |
| 903  | _The Orb_             |
| 904  | _The Orb_             |
| 905  | _The Orb_             |
| 906  | _The Orb_             |
| 907  | _The Orb_             |
| 908  | _The Orb_             |
| 909  | _The Orb_             |
| 910  | _The Orb_             |
| 911  | _The Orb_             |
| 912  | _The Orb_             |
| 913  | _The Orb_             |
| 914  | _The Orb_             |
| 915  | _The Orb_             |
| 916  | _The Orb_             |
| 917  | _The Orb_             |
| 918  | _The Orb_             |
| 919  | _The Orb_             |
| 920  | _The Orb_             |
| 921  | _The Orb_             |
| 922  | _The Orb_             |
| 923  | _The Orb_             |
| 924  | _The Orb_             |
| 925  | _The Orb_             |
| 926  | _The Orb_             |
| 927  | _The Orb_             |
| 928  | _The Orb_             |
| 929  | _The Orb_             |
| 930  | _The Orb_             |
| 931  | _The Orb_             |
| 932  | _The Orb_             |
| 933  | _The Orb_             |
| 934  | _The Orb_             |
| 935  | _The Orb_             |
| 936  | _The Orb_             |
| 937  | _The Orb_             |
| 938  | _The Orb_             |
| 939  | _The Orb_             |
| 940  | _The Orb_             |
| 941  | _The Orb_             |
| 942  | _The Orb_             |
| 943  | _The Orb_             |
| 944  | _The Orb_             |
| 945  | _The Orb_             |
| 946  | _The Orb_             |
| 947  | _The Orb_             |
| 948  | _The Orb_             |
| 949  | _The Orb_             |
| 950  | _The Orb_             |
| 951  | _The Orb_             |
| 952  | _The Orb_             |
| 953  | _The Orb_             |
| 954  | _The Orb_             |
| 955  | _The Orb_             |
| 956  | _The Orb_             |
| 957  | _The Orb_             |
| 958  | _The Orb_             |
| 959  | _The Orb_             |
| 960  | _The Orb_             |
| 961  | _The Orb_             |
| 962  | _The Orb_             |
| 963  | _The Orb_             |
| 964  | _The Orb_             |
| 965  | _The Orb_             |
| 966  | _The Orb_             |
| 967  | _The Orb_             |
| 968  | _The Orb_             |
| 969  | _The Orb_             |
| 970  | _The Orb_             |
| 971  | _The Orb_             |
| 972  | _The Orb_             |
| 973  | _The Orb_             |
| 974  | _The Orb_             |
| 975  | _The Orb_             |
| 976  | _The Orb_             |
| 977  | _The Orb_             |
| 978  | _The Orb_             |
| 979  | _The Orb_             |
| 980  | _The Orb_             |
| 981  | _The Orb_             |
| 982  | _The Orb_             |
| 983  | _The Orb_             |
| 984  | _The Orb_             |
| 985  | _The Orb_             |
| 986  | _The Orb_             |
| 987  | _The Orb_             |
| 988  | _The Orb_             |
| 989  | _The Orb_             |
| 990  | _The Orb_             |
| 991  | _The Orb_             |
| 992  | _The Orb_             |
| 993  | _The Orb_             |
| 994  | _The Orb_             |
| 995  | _The Orb_             |
| 996  | _The Orb_             |
| 997  | _The Orb_             |
| 998  | _The Orb_             |
| 999  | _The Orb_             |
| 1000 | _The Orb_             |

#### Biome Entity Type Mapping

This table shows the internal ID for different entity types that can be associated with biomes.

| ID   | Type        |
| :--- | :---------- |
| 0    | _None_      |
| 1    | _Enemy_     |
| 2    | _Item_      |
| 3    | _Prop_      |
| 4    | _Material_  |
| 5    | _Effect_    |
| 6    | _Biome_     |
| 7    | _Spell_     |
| 8    | _Wand_      |
| 9    | _Modifier_  |
| 10   | _Biome_     |
| 11   | _Biome_     |
| 12   | _Biome_     |
| 13   | _Biome_     |
| 14   | _Biome_     |
| 15   | _Biome_     |
| 16   | _Biome_     |
| 17   | _Biome_     |
| 18   | _Biome_     |
| 19   | _Biome_     |
| 20   | _Biome_     |
| 21   | _Biome_     |
| 22   | _Biome_     |
| 23   | _Biome_     |
| 24   | _Biome_     |
| 25   | _Biome_     |
| 26   | _Biome_     |
| 27   | _Biome_     |
| 28   | _Biome_     |
| 29   | _Biome_     |
| 30   | _Biome_     |
| 31   | _Biome_     |
| 32   | _Biome_     |
| 33   | _Biome_     |
| 34   | _Biome_     |
| 35   | _Biome_     |
| 36   | _Biome_     |
| 37   | _Biome_     |
| 38   | _Biome_     |
| 39   | _Biome_     |
| 40   | _Biome_     |
| 41   | _Biome_     |
| 42   | _Biome_     |
| 43   | _Biome_     |
| 44   | _Biome_     |
| 45   | _Biome_     |
| 46   | _Biome_     |
| 47   | _Biome_     |
| 48   | _Biome_     |
| 49   | _Biome_     |
| 50   | _Biome_     |
| 51   | _Biome_     |
| 52   | _Biome_     |
| 53   | _Biome_     |
| 54   | _Biome_     |
| 55   | _Biome_     |
| 56   | _Biome_     |
| 57   | _Biome_     |
| 58   | _Biome_     |
| 59   | _Biome_     |
| 60   | _Biome_     |
| 61   | _Biome_     |
| 62   | _Biome_     |
| 63   | _Biome_     |
| 64   | _Biome_     |
| 65   | _Biome_     |
| 66   | _Biome_     |
| 67   | _Biome_     |
| 68   | _Biome_     |
| 69   | _Biome_     |
| 70   | _Biome_     |
| 71   | _Biome_     |
| 72   | _Biome_     |
| 73   | _Biome_     |
| 74   | _Biome_     |
| 75   | _Biome_     |
| 76   | _Biome_     |
| 77   | _Biome_     |
| 78   | _Biome_     |
| 79   | _Biome_     |
| 80   | _Biome_     |
| 81   | _Biome_     |
| 82   | _Biome_     |
| 83   | _Biome_     |
| 84   | _Biome_     |
| 85   | _Biome_     |
| 86   | _Biome_     |
| 87   | _Biome_     |
| 88   | _Biome_     |
| 89   | _Biome_     |
| 90   | _Biome_     |
| 91   | _Biome_     |
| 92   | _Biome_     |
| 93   | _Biome_     |
| 94   | _Biome_     |
| 95   | _Biome_     |
| 96   | _Biome_     |
| 97   | _Biome_     |
| 98   | _Biome_     |
| 99   | _Biome_     |
| 100  | _Biome_     |
| 101  | _Biome_     |
| 102  | _Biome_     |
| 103  | _Biome_     |
| 104  | _Biome_     |
| 105  | _Biome_     |
| 106  | _Biome_     |
| 107  | _Biome_     |
| 108  | _Biome_     |
| 109  | _Biome_     |
| 110  | _Biome_     |
| 111  | _Biome_     |
| 112  | _Biome_     |
| 113  | _Biome_     |
| 114  | _Biome_     |
| 115  | _Biome_     |
| 116  | _Biome_     |
| 117  | _Biome_     |
| 118  | _Biome_     |
| 119  | _Biome_     |
| 120  | _Biome_     |
| 121  | _Biome_     |
| 122  | _Biome_     |
| 123  | _Biome_     |
| 124  | _Biome_     |
| 125  | _Biome_     |
| 126  | _Biome_     |
| 127  | _Biome_     |
| 128  | _Biome_     |
| 129  | _Biome_     |
| 130  | _Biome_     |
| 131  | _Biome_     |
| 132  | _Biome_     |
| 133  | _Biome_     |
| 134  | _Biome_     |
| 135  | _Biome_     |
| 136  | _Biome_     |
| 137  | _Biome_     |
| 138  | _Biome_     |
| 139  | _Biome_     |
| 140  | _Biome_     |
| 141  | _Biome_     |
| 142  | _Biome_     |
| 143  | _Biome_     |
| 144  | _Biome_     |
| 145  | _Biome_     |
| 146  | _Biome_     |
| 147  | _Biome_     |
| 148  | _Biome_     |
| 149  | _Biome_     |
| 150  | _Biome_     |
| 151  | _Biome_     |
| 152  | _Biome_     |
| 153  | _Biome_     |
| 154  | _Biome_     |
| 155  | _Biome_     |
| 156  | _Biome_     |
| 157  | _Biome_     |
| 158  | _Biome_     |
| 159  | _Biome_     |
| 160  | _Biome_     |
| 161  | _Biome_     |
| 162  | _Biome_     |
| 163  | _Biome_     |
| 164  | _Biome_     |
| 165  | _Biome_     |
| 166  | _Biome_     |
| 167  | _Biome_     |
| 168  | _Biome_     |
| 169  | _Biome_     |
| 170  | _Biome_     |
| 171  | _Biome_     |
| 172  | _Biome_     |
| 173  | _Biome_     |
| 174  | _Biome_     |
| 175  | _Biome_     |
| 176  | _Biome_     |
| 177  | _Biome_     |
| 178  | _Biome_     |
| 179  | _Biome_     |
| 180  | _Biome_     |
| 181  | _Biome_     |
| 182  | _Biome_     |
| 183  | _Biome_     |
| 184  | _Biome_     |
| 185  | _Biome_     |
| 186  | _Biome_     |
| 187  | _Biome_     |
| 188  | _Biome_     |
| 189  | _Biome_     |
| 190  | _Biome_     |
| 191  | _Biome_     |
| 192  | _Biome_     |
| 193  | _Biome_     |
| 194  | _Biome_     |
| 195  | _Biome_     |
| 196  | _Biome_     |
| 197  | _Biome_     |
| 198  | _Biome_     |
| 199  | _Biome_     |
| 200  | _Biome_     |
| 201  | _Biome_     |
| 202  | _Biome_     |
| 203  | _Biome_     |
| 204  | _Biome_     |
| 205  | _Biome_     |
| 206  | _Biome_     |
| 207  | _Biome_     |
| 208  | _Biome_     |
| 209  | _Biome_     |
| 210  | _Biome_     |
| 211  | _Biome_     |
| 212  | _Biome_     |
| 213  | _Biome_     |
| 214  | _Biome_     |
| 215  | _Biome_     |
| 216  | _Biome_     |
| 217  | _Biome_     |
| 218  | _Biome_     |
| 219  | _Biome_     |
| 220  | _Biome_     |
| 221  | _Biome_     |
| 222  | _Biome_     |
| 223  | _Biome_     |
| 224  | _Biome_     |
| 225  | _Biome_     |
| 226  | _Biome_     |
| 227  | _Biome_     |
| 228  | _Biome_     |
| 229  | _Biome_     |
| 230  | _Biome_     |
| 231  | _Biome_     |
| 232  | _Biome_     |
| 233  | _Biome_     |
| 234  | _Biome_     |
| 235  | _Biome_     |
| 236  | _Biome_     |
| 237  | _Biome_     |
| 238  | _Biome_     |
| 239  | _Biome_     |
| 240  | _Biome_     |
| 241  | _Biome_     |
| 242  | _Biome_     |
| 243  | _Biome_     |
| 244  | _Biome_     |
| 245  | _Biome_     |
| 246  | _Biome_     |
| 247  | _Biome_     |
| 248  | _Biome_     |
| 249  | _Biome_     |
| 250  | _Biome_     |
| 251  | _Biome_     |
| 252  | _Biome_     |
| 253  | _Biome_     |
| 254  | _Biome_     |
| 255  | _Biome_     |
| 256  | _Biome_     |
| 257  | _Biome_     |
| 258  | _Biome_     |
| 259  | _Biome_     |
| 260  | _Biome_     |
| 261  | _Biome_     |
| 262  | _Biome_     |
| 263  | _Biome_     |
| 264  | _Biome_     |
| 265  | _Biome_     |
| 266  | _Biome_     |
| 267  | _Biome_     |
| 268  | _Biome_     |
| 269  | _Biome_     |
| 270  | _Biome_     |
| 271  | _Biome_     |
| 272  | _Biome_     |
| 273  | _Biome_     |
| 274  | _Biome_     |
| 275  | _Biome_     |
| 276  | _Biome_     |
| 277  | _Biome_     |
| 278  | _Biome_     |
| 279  | _Biome_     |
| 280  | _Biome_     |
| 281  | _Biome_     |
| 282  | _Biome_     |
| 283  | _Biome_     |
| 284  | _Biome_     |
| 285  | _Biome_     |
| 286  | _Biome_     |
| 287  | _Biome_     |
| 288  | _Biome_     |
| 289  | _Biome_     |
| 290  | _Biome_     |
| 291  | _Biome_     |
| 292  | _Biome_     |
| 293  | _Biome_     |
| 294  | _Biome_     |
| 295  | _Biome_     |
| 296  | _Biome_     |
| 297  | _Biome_     |
| 298  | _Biome_     |
| 299  | _Biome_     |
| 300  | _Biome_     |
| 301  | _Biome_     |
| 302  | _Biome_     |
| 303  | _Biome_     |
| 304  | _Biome_     |
| 305  | _Biome_     |
| 306  | _Biome_     |
| 307  | _Biome_     |
| 308  | _Biome_     |
| 309  | _Biome_     |
| 310  | _Biome_     |
| 311  | _Biome_     |
| 312  | _Biome_     |
| 313  | _Biome_     |
| 314  | _Biome_     |
| 315  | _Biome_     |
| 316  | _Biome_     |
| 317  | _Biome_     |
| 318  | _Biome_     |
| 319  | _Biome_     |
| 320  | _Biome_     |
| 321  | _Biome_     |
| 322  | _Biome_     |
| 323  | _Biome_     |
| 324  | _Biome_     |
| 325  | _Biome_     |
| 326  | _Biome_     |
| 327  | _Biome_     |
| 328  | _Biome_     |
| 329  | _Biome_     |
| 330  | _Biome_     |
| 331  | _Biome_     |
| 332  | _Biome_     |
| 333  | _Biome_     |
| 334  | _Biome_     |
| 335  | _Biome_     |
| 336  | _Biome_     |
| 337  | _Biome_     |
| 338  | _Biome_     |
| 339  | _Biome_     |
| 340  | _Biome_     |
| 341  | _Biome_     |
| 342  | _Biome_     |
| 343  | _Biome_     |
| 344  | _Biome_     |
| 345  | _Biome_     |
| 346  | _Biome_     |
| 347  | _Biome_     |
| 348  | _Biome_     |
| 349  | _Biome_     |
| 350  | _Biome_     |
| 351  | _Biome_     |
| 352  | _Biome_     |
| 353  | _Biome_     |
| 354  | _Biome_     |
| 355  | _Biome_     |
| 356  | _Biome_     |
| 357  | _Biome_     |
| 358  | _Biome_     |
| 359  | _Biome_     |
| 360  | _Biome_     |
| 361  | _Biome_     |
| 362  | _Biome_     |
| 363  | _Biome_     |
| 364  | _Biome_     |
| 365  | _Biome_     |
| 366  | _Biome_     |
| 367  | _Biome_     |
| 368  | _Biome_     |
| 369  | _Biome_     |
| 370  | _Biome_     |
| 371  | _Biome_     |
| 372  | _Biome_     |
| 373  | _Biome_     |
| 374  | _Biome_     |
| 375  | _Biome_     |
| 376  | _Biome_     |
| 377  | _Biome_     |
| 378  | _Biome_     |
| 379  | _Biome_     |
| 380  | _Biome_     |
| 381  | _Biome_     |
| 382  | _Biome_     |
| 383  | _Biome_     |
| 384  | _Biome_     |
| 385  | _Biome_     |
| 386  | _Biome_     |
| 387  | _Biome_     |
| 388  | _Biome_     |
| 389  | _Biome_     |
| 390  | _Biome_     |
| 391  | _Biome_     |
| 392  | _Biome_     |
| 393  | _Biome_     |
| 394  | _Biome_     |
| 395  | _Biome_     |
| 396  | _Biome_     |
| 397  | _Biome_     |
| 398  | _Biome_     |
| 399  | _Biome_     |
| 400  | _Biome_     |
| 401  | _Biome_     |
| 402  | _Biome_     |
| 403  | _Biome_     |
| 404  | _Biome_     |
| 405  | _Biome_     |
| 406  | _Biome_     |
| 407  | _Biome_     |
| 408  | _Biome_     |
| 409  | _Biome_     |
| 410  | _Biome_     |
| 411  | _Biome_     |
| 412  | _Biome_     |
| 413  | _Biome_     |
| 414  | _Biome_     |
| 415  | _Biome_     |
| 416  | _Biome_     |
| 417  | _Biome_     |
| 418  | _Biome_     |
| 419  | _Biome_     |
| 420  | _Biome_     |
| 421  | _Biome_     |
| 422  | _Biome_     |
| 423  | _Biome_     |
| 424  | _Biome_     |
| 425  | _Biome_     |
| 426  | _Biome_     |
| 427  | _Biome_     |
| 428  | _Biome_     |
| 429  | _Biome_     |
| 430  | _Biome_     |
| 431  | _Biome_     |
| 432  | _Biome_     |
| 433  | _Biome_     |
| 434  | _Biome_     |
| 435  | _Biome_     |
| 436  | _Biome_     |
| 437  | _Biome_     |
| 438  | _Biome_     |
| 439  | _Biome_     |
| 440  | _Biome_     |
| 441  | _Biome_     |
| 442  | _Biome_     |
| 443  | _Biome_     |
| 444  | _Biome_     |
| 445  | _Biome_     |
| 446  | _Biome_     |
| 447  | _Biome_     |
| 448  | _Biome_     |
| 449  | _Biome_     |
| 450  | _Biome_     |
| 451  | _Biome_     |
| 452  | _Biome_     |
| 453  | _Biome_     |
| 454  | _Biome_     |
| 455  | _Biome_     |
| 456  | _Biome_     |
| 457  | _Biome_     |
| 458  | _Biome_     |
| 459  | _Biome_     |
| 460  | _Biome_     |
| 461  | _Biome_     |
| 462  | _Biome_     |
| 463  | _Biome_     |
| 464  | _Biome_     |
| 465  | _Biome_     |
| 466  | _Biome_     |
| 467  | _Biome_     |
| 468  | _Biome_     |
| 469  | _Biome_     |
| 470  | _Biome_     |
| 471  | _Biome_     |
| 472  | _Biome_     |
| 473  | _Biome_     |
| 474  | _Biome_     |
| 475  | _Biome_     |
| 476  | _Biome_     |
| 477  | _Biome_     |
| 478  | _Biome_     |
| 479  | _Biome_     |
| 480  | _Biome_     |
| 481  | _Biome_     |
| 482  | _Biome_     |
| 483  | _Biome_     |
| 484  | _Biome_     |
| 485  | _Biome_     |
| 486  | _Biome_     |
| 487  | _Biome_     |
| 488  | _Biome_     |
| 489  | _Biome_     |
| 490  | _Biome_     |
| 491  | _Biome_     |
| 492  | _Biome_     |
| 493  | _Biome_     |
| 494  | _Biome_     |
| 495  | _Biome_     |
| 496  | _Biome_     |
| 497  | _Biome_     |
| 498  | _Biome_     |
| 499  | _Biome_     |
| 500  | _Biome_     |
| 501  | _Biome_     |
| 502  | _Biome_     |
| 503  | _Biome_     |
| 504  | _Biome_     |
| 505  | _Biome_     |
| 506  | _Biome_     |
| 507  | _Biome_     |
| 508  | _Biome_     |
| 509  | _Biome_     |
| 510  | _Biome_     |
| 511  | _Biome_     |
| 512  | _Biome_     |
| 513  | _Biome_     |
| 514  | _Biome_     |
| 515  | _Biome_     |
| 516  | _Biome_     |
| 517  | _Biome_     |
| 518  | _Biome_     |
| 519  | _Biome_     |
| 520  | _Biome_     |
| 521  | _Biome_     |
| 522  | _Biome_     |
| 523  | _Biome_     |
| 524  | _Biome_     |
| 525  | _Biome_     |
| 526  | _Biome_     |
| 527  | _Biome_     |
| 528  | _Biome_     |
| 529  | _Biome_     |
| 530  | _Biome_     |
| 531  | _Biome_     |
| 532  | _Biome_     |
| 533  | _Biome_     |
| 534  | _Biome_     |
| 535  | _Biome_     |
| 536  | _Biome_     |
| 537  | _Biome_     |
| 538  | _Biome_     |
| 539  | _Biome_     |
| 540  | _Biome_     |
| 541  | _Biome_     |
| 542  | _Biome_     |
| 543  | _Biome_     |
| 544  | _Biome_     |
| 545  | _Biome_     |
| 546  | _Biome_     |
| 547  | _Biome_     |
| 548  | _Biome_     |
| 549  | _Biome_     |
| 550  | _Biome_     |
| 551  | _Biome_     |
| 552  | _Biome_     |
| 553  | _Biome_     |
| 554  | _Biome_     |
| 555  | _Biome_     |
| 556  | _Biome_     |
| 557  | _Biome_     |
| 558  | _Biome_     |
| 559  | _Biome_     |
| 560  | _Biome_     |
| 561  | _Biome_     |
| 562  | _Biome_     |
| 563  | _Biome_     |
| 564  | _Biome_     |
| 565  | _Biome_     |
| 566  | _Biome_     |
| 567  | _Biome_     |
| 568  | _Biome_     |
| 569  | _Biome_     |
| 570  | _Biome_     |
| 571  | _Biome_     |
| 572  | _Biome_     |
| 573  | _Biome_     |
| 574  | _Biome_     |
| 575  | _Biome_     |
| 576  | _Biome_     |
| 577  | _Biome_     |
| 578  | _Biome_     |
| 579  | _Biome_     |
| 580  | _Biome_     |
| 581  | _Biome_     |
| 582  | _Biome_     |
| 583  | _Biome_     |
| 584  | _Biome_     |
| 585  | _Biome_     |
| 586  | _Biome_     |
| 587  | _Biome_     |
| 588  | _Biome_     |
| 589  | _Biome_     |
| 590  | _Biome_     |
| 591  | _Biome_     |
| 592  | _Biome_     |
| 593  | _Biome_     |
| 594  | _Biome_     |
| 595  | _Biome_     |
| 596  | _Biome_     |
| 597  | _Biome_     |
| 598  | _Biome_     |
| 599  | _Biome_     |
| 600  | _Biome_     |
| 601  | _Biome_     |
| 602  | _Biome_     |
| 603  | _Biome_     |
| 604  | _Biome_     |
| 605  | _Biome_     |
| 606  | _Biome_     |
| 607  | _Biome_     |
| 608  | _Biome_     |
| 609  | _Biome_     |
| 610  | _Biome_     |
| 611  | _Biome_     |
| 612  | _Biome_     |
| 613  | _Biome_     |
| 614  | _Biome_     |
| 615  | _Biome_     |
| 616  | _Biome_     |
| 617  | _Biome_     |
| 618  | _Biome_     |
| 619  | _Biome_     |
| 620  | _Biome_     |
| 621  | _Biome_     |
| 622  | _Biome_     |
| 623  | _Biome_     |
| 624  | _Biome_     |
| 625  | _Biome_     |
| 626  | _Biome_     |
| 627  | _Biome_     |
| 628  | _Biome_     |
| 629  | _Biome_     |
| 630  | _Biome_     |
| 631  | _Biome_     |
| 632  | _Biome_     |
| 633  | _Biome_     |
| 634  | _Biome_     |
| 635  | _Biome_     |
| 636  | _Biome_     |
| 637  | _Biome_     |
| 638  | _Biome_     |
| 639  | _Biome_     |
| 640  | _Biome_     |
| 641  | _Biome_     |
| 642  | _Biome_     |
| 643  | _Biome_     |
| 644  | _Biome_     |
| 645  | _Biome_     |
| 646  | _Biome_     |
| 647  | _Biome_     |
| 648  | _Biome_     |
| 649  | _Biome_     |
| 650  | _Biome_     |
| 651  | _Biome_     |
| 652  | _Biome_     |
| 653  | _Biome_     |
| 654  | _Biome_     |
| 655  | _Biome_     |
| 656  | _Biome_     |
| 657  | _Biome_     |
| 658  | _Biome_     |
| 659  | _Biome_     |
| 660  | _Biome_     |
| 661  | _Biome_     |
| 662  | _Biome_     |
| 663  | _Biome_     |
| 664  | _Biome_     |
| 665  | _Biome_     |
| 666  | _Biome_     |
| 667  | _Biome_     |
| 668  | _Biome_     |
| 669  | _Biome_     |
| 670  | _Biome_     |
| 671  | _Biome_     |
| 672  | _Biome_     |
| 673  | _Biome_     |
| 674  | _Biome_     |
| 675  | _Biome_     |
| 676  | _Biome_     |
| 677  | _Biome_     |
| 678  | _Biome_     |
| 679  | _Biome_     |
| 680  | _Biome_     |
| 681  | _Biome_     |
| 682  | _Biome_     |
| 683  | _Biome_     |
| 684  | _Biome_     |
| 685  | _Biome_     |
| 686  | _Biome_     |
| 687  | _Biome_     |
| 688  | _Biome_     |
| 689  | _Biome_     |
| 690  | _Biome_     |
| 691  | _Biome_     |
| 692  | _Biome_     |
| 693  | _Biome_     |
| 694  | _Biome_     |
| 695  | _Biome_     |
| 696  | _Biome_     |
| 697  | _Biome_     |
| 698  | _Biome_     |
| 699  | _Biome_     |
| 700  | _Biome_     |
| 701  | _Biome_     |
| 702  | _Biome_     |
| 703  | _Biome_     |
| 704  | _Biome_     |
| 705  | _Biome_     |
| 706  | _Biome_     |
| 707  | _Biome_     |
| 708  | _Biome_     |
| 709  | _Biome_     |
| 710  | _Biome_     |
| 711  | _Biome_     |
| 712  | _Biome_     |
| 713  | _Biome_     |
| 714  | _Biome_     |
| 715  | _Biome_     |
| 716  | _Biome_     |
| 717  | _Biome_     |
| 718  | _Biome_     |
| 719  | _Biome_     |
| 720  | _Biome_     |
| 721  | _Biome_     |
| 722  | _Biome_     |
| 723  | _Biome_     |
| 724  | _Biome_     |
| 725  | _Biome_     |
| 726  | _Biome_     |
| 727  | _Biome_     |
| 728  | _Biome_     |
| 729  | _Biome_     |
| 730  | _Biome_     |
| 731  | _Biome_     |
| 732  | _Biome_     |
| 733  | _Biome_     |
| 734  | _Biome_     |
| 735  | _Biome_     |
| 736  | _Biome_     |
| 737  | _Biome_     |
| 738  | _Biome_     |
| 739  | _Biome_     |
| 740  | _Biome_     |
| 741  | _Biome_     |
| 742  | _Biome_     |
| 743  | _Biome_     |
| 744  | _Biome_     |
| 745  | _Biome_     |
| 746  | _Biome_     |
| 747  | _Biome_     |
| 748  | _Biome_     |
| 749  | _Biome_     |
| 750  | _Biome_     |
| 751  | _Biome_     |
| 752  | _Biome_     |
| 753  | _Biome_     |
| 754  | _Biome_     |
| 755  | _Biome_     |
| 756  | _Biome_     |
| 757  | _Biome_     |
| 758  | _Biome_     |
| 759  | _Biome_     |
| 760  | _Biome_     |
| 761  | _Biome_     |
| 762  | _Biome_     |
| 763  | _Biome_     |
| 764  | _Biome_     |
| 765  | _Biome_     |
| 766  | _Biome_     |
| 767  | _Biome_     |
| 768  | _Biome_     |
| 769  | _Biome_     |
| 770  | _Biome_     |
| 771  | _Biome_     |
| 772  | _Biome_     |
| 773  | _Biome_     |
| 774  | _Biome_     |
| 775  | _Biome_     |
| 776  | _Biome_     |
| 777  | _Biome_     |
| 778  | _Biome_     |
| 779  | _Biome_     |
| 780  | _Biome_     |
| 781  | _Biome_     |
| 782  | _Biome_     |
| 783  | _Biome_     |
| 784  | _Biome_     |
| 785  | _Biome_     |
| 786  | _Biome_     |
| 787  | _Biome_     |
| 788  | _Biome_     |
| 789  | _Biome_     |
| 790  | _Biome_     |
| 791  | _Biome_     |
| 792  | _Biome_     |
| 793  | _Biome_     |
| 794  | _Biome_     |
| 795  | _Biome_     |
| 796  | _Biome_     |
| 797  | _Biome_     |
| 798  | _Biome_     |
| 799  | _Biome_     |
| 800  | _Biome_     |
| 801  | _Biome_     |
| 802  | _Biome_     |
| 803  | _Biome_     |
| 804  | _Biome_     |
| 805  | _Biome_     |
| 806  | _Biome_     |
| 807  | _Biome_     |
| 808  | _Biome_     |
| 809  | _Biome_     |
| 810  | _Biome_     |
| 811  | _Biome_     |
| 812  | _Biome_     |
| 813  | _Biome_     |
| 814  | _Biome_     |
| 815  | _Biome_     |
| 816  | _Biome_     |
| 817  | _Biome_     |
| 818  | _Biome_     |
| 819  | _Biome_     |
| 820  | _Biome_     |
| 821  | _Biome_     |
| 822  | _Biome_     |
| 823  | _Biome_     |
| 824  | _Biome_     |
| 825  | _Biome_     |
| 826  | _Biome_     |
| 827  | _Biome_     |
| 828  | _Biome_     |
| 829  | _Biome_     |
| 830  | _Biome_     |
| 831  | _Biome_     |
| 832  | _Biome_     |
| 833  | _Biome_     |
| 834  | _Biome_     |
| 835  | _Biome_     |
| 836  | _Biome_     |
| 837  | _Biome_     |
| 838  | _Biome_     |
| 839  | _Biome_     |
| 840  | _Biome_     |
| 841  | _Biome_     |
| 842  | _Biome_     |
| 843  | _Biome_     |
| 844  | _Biome_     |
| 845  | _Biome_     |
| 846  | _Biome_     |
| 847  | _Biome_     |
| 848  | _Biome_     |
| 849  | _Biome_     |
| 850  | _Biome_     |
| 851  | _Biome_     |
| 852  | _Biome_     |
| 853  | _Biome_     |
| 854  | _Biome_     |
| 855  | _Biome_     |
| 856  | _Biome_     |
| 857  | _Biome_     |
| 858  | _Biome_     |
| 859  | _Biome_     |
| 860  | _Biome_     |
| 861  | _Biome_     |
| 862  | _Biome_     |
| 863  | _Biome_     |
| 864  | _Biome_     |
| 865  | _Biome_     |
| 866  | _Biome_     |
| 867  | _Biome_     |
| 868  | _Biome_     |
| 869  | _Biome_     |
| 870  | _Biome_     |
| 871  | _Biome_     |
| 872  | _Biome_     |
| 873  | _Biome_     |
| 874  | _Biome_     |
| 875  | _Biome_     |
| 876  | _Biome_     |
| 877  | _Biome_     |
| 878  | _Biome_     |
| 879  | _Biome_     |
| 880  | _Biome_     |
| 881  | _Biome_     |
| 882  | _Biome_     |
| 883  | _Biome_     |
| 884  | _Biome_     |
| 885  | _Biome_     |
| 886  | _Biome_     |
| 887  | _Biome_     |
| 888  | _Biome_     |
| 889  | _Biome_     |
| 890  | _Biome_     |
| 891  | _Biome_     |
| 892  | _Biome_     |
| 893  | _Biome_     |
| 894  | _Biome_     |
| 895  | _Biome_     |
| 896  | _Biome_     |
| 897  | _Biome_     |
| 898  | _Biome_     |
| 899  | _Biome_     |
| 900  | _Biome_     |
| 901  | _Biome_     |
| 902  | _Biome_     |
| 903  | _Biome_     |
| 904  | _Biome_     |
| 905  | _Biome_     |
| 906  | _Biome_     |
| 907  | _Biome_     |
| 908  | _Biome_     |
| 909  | _Biome_     |
| 910  | _Biome_     |
| 911  | _Biome_     |
| 912  | _Biome_     |
| 913  | _Biome_     |
| 914  | _Biome_     |
| 915  | _Biome_     |
| 916  | _Biome_     |
| 917  | _Biome_     |
| 918  | _Biome_     |
| 919  | _Biome_     |
| 920  | _Biome_     |
| 921  | _Biome_     |
| 922  | _Biome_     |
| 923  | _Biome_     |
| 924  | _Biome_     |
| 925  | _Biome_     |
| 926  | _Biome_     |
| 927  | _Biome_     |
| 928  | _Biome_     |
| 929  | _Biome_     |
| 930  | _Biome_     |
| 931  | _Biome_     |
| 932  | _Biome_     |
| 933  | _Biome_     |
| 934  | _Biome_     |
| 935  | _Biome_     |
| 936  | _Biome_     |
| 937  | _Biome_     |
| 938  | _Biome_     |
| 939  | _Biome_     |
| 940  | _Biome_     |
| 941  | _Biome_     |
| 942  | _Biome_     |
| 943  | _Biome_     |
| 944  | _Biome_     |
| 945  | _Biome_     |
| 946  | _Biome_     |
| 947  | _Biome_     |
| 948  | _Biome_     |
| 949  | _Biome_     |
| 950  | _Biome_     |
| 951  | _Biome_     |
| 952  | _Biome_     |
| 953  | _Biome_     |
| 954  | _Biome_     |
| 955  | _Biome_     |
| 956  | _Biome_     |
| 957  | _Biome_     |
| 958  | _Biome_     |
| 959  | _Biome_     |
| 960  | _Biome_     |
| 961  | _Biome_     |
| 962  | _Biome_     |
| 963  | _Biome_     |
| 964  | _Biome_     |
| 965  | _Biome_     |
| 966  | _Biome_     |
| 967  | _Biome_     |
| 968  | _Biome_     |
| 969  | _Biome_     |
| 970  | _Biome_     |
| 971  | _Biome_     |
| 972  | _Biome_     |
| 973  | _Biome_     |
| 974  | _Biome_     |
| 975  | _Biome_     |
| 976  | _Biome_     |
| 977  | _Biome_     |
| 978  | _Biome_     |
| 979  | _Biome_     |
| 980  | _Biome_     |
| 981  | _Biome_     |
| 982  | _Biome_     |
| 983  | _Biome_     |
| 984  | _Biome_     |
| 985  | _Biome_     |
| 986  | _Biome_     |
| 987  | _Biome_     |
| 988  | _Biome_     |
| 989  | _Biome_     |
| 990  | _Biome_     |
| 991  | _Biome_     |
| 992  | _Biome_     |
| 993  | _Biome_     |
| 994  | _Biome_     |
| 995  | _Biome_     |
| 996  | _Biome_     |
| 997  | _Biome_     |
| 998  | _Biome_     |
| 999  | _Biome_     |
| 1000 | _Biome_     |

### Biome XML Structure Example

A typical biome definition file might look like this. This example shows a simplified structure for a custom biome.

```xml
<!-- Example: data/biome/my_custom_biome.xml -->
<Biome name="My Custom Biome" id="1000">
    <Tags>
        <Tag name="underground" />
        <Tag name="dark" />
        <Tag name="cold" />
    </Tags>
    <Materials>
        <Material name="dirt" />
        <Material name="stone" />
    </Materials>
    <Entities>
        <Entity type="enemy" name="goblin" probability="0.5" />
        <Entity type="item" name="potion_health" probability="0.2" />
        <Entity type="prop" name="rock" probability="0.8" />
    </Entities>
    <Visuals>
        <Color r="0.2" g="0.3" b="0.4" />
        <Texture path="textures/my_biome_texture.png" />
    </Visuals>
    <Effects>
        <Effect type="fog" density="0.1" />
    </Effects>
</Biome>
```

## Modding Biomes

Modding biomes involves creating new biome definitions, modifying existing ones, or influencing biome generation.

### Creating New Biomes

To create a new biome, you will typically:

1.  **Create a new XML file** in your mod's `data/biome/` directory.
2.  **Define the biome's properties** within the XML, similar to the example above. This includes its name, ID (ensure it's unique and doesn't conflict with existing biomes), tags, materials, entities, visuals, and effects.
3.  **Ensure your biome is referenced** in the game's biome generation logic if you want it to appear in the world. This might involve modifying `data/biome/biomes.xml` or using Lua scripting to influence generation.

### Modifying Existing Biomes

You can override or extend existing biome definitions by placing an XML file with the same name as the original biome file in your mod's `data/biome/` directory. For example, to modify `data/biome/mines.xml`, you would create `your_mod/data/biome/mines.xml`.

### Biome Generation and Lua Scripting

Biome generation is a complex process that can be influenced through Lua scripting. You can use the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) to:

*   **Register new biomes:** Make your custom biomes known to the game's generation system.
*   **Modify biome spawn probabilities:** Control how often certain biomes appear.
*   **Influence entity spawning:** Dynamically change which entities can spawn in a biome based on game state.
*   **Create biome-specific events or mechanics.**

#### Example Lua Snippet for Biome Modification

This example demonstrates how you might use Lua to add a custom entity to an existing biome.

```lua
-- Example: Modifying the Mines biome to spawn a custom enemy
local function modifyMinesBiome()
    local minesBiome = Game.GetWorld():GetBiomeManager():GetBiome("The Mines") -- Assuming "The Mines" is the correct name or ID

    if minesBiome then
        -- Add a custom enemy with a certain probability
        minesBiome:AddEntity("enemy", "my_custom_enemy", 0.3)
        -- You might need to use specific functions depending on the exact API available
        -- This is a conceptual example. Refer to the Lua API for exact function calls.
    end
end

-- Call this function during game initialization or when biomes are loaded
-- For example, using a modding hook:
RegisterModCallback(function(mod)
    mod:Hook("OnInit", function()
        modifyMinesBiome()
    end)
end)
```

## Important Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity Documentation](https://noita.wiki.gg/wiki/Documentation:Entity) (Understanding entities is crucial for biome modding)
*   [Noita Modding Discord](https://discord.gg/noitamodding) (For community support and further questions)