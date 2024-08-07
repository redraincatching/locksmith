# Nintendo DS Overlays
----

## What is an overlay?
----
idk yet look at [this](https://en.wikipedia.org/wiki/Overlay_(programming))

## Overlay Format
----
sample layout of an overlay file
```txt
OVERLAY# RAM_ADDR RAM_SIZE BSS_SIZE STAT_BEG STAT_END FILE_ID# RESERVED
00000000 80C32202 40000000 00000500 A4C32202 ACC32202 00000000 00000000
```

## *Lock's Quest* Overlays
----
There are 13 overlays for this game, and I don't know what any of them do yet. I will eventually have a full YAML file for each, something like this
```yaml
overlay14:
    versions:
        - EU
        - NA
        - JP
    address:
        EU: 0x238AC80
        NA: 0x238A140
        JP: 0x238B6A0
    length:
        EU: 0xC60
        NA: 0xC60
        JP: 0xC60
    description: Gives Lock a duel disk.
    functions: []
    data: []
```
(stolen from the [pokemon mystery dungeon debug repo](https://github.com/UsernameFodder/pmdsky-debug/tree/master))

For now though, I'll just make a list of their addresses and lengths in the one version I have

- overlay 00
    - 0x0207E380
    - 0x0243E0
    - open while building
- overlay 01
    - 0x0207E380
    - 0x3CC0
- overlay 02
    - 0x0207E380
    - 0x20
    - literally just 32 bytes of 00
- overlay 03
    - 0x0207E380
    - 0x0260
- overlay 04
    - 0x0207E380
    - 0x8DA0
    - loaded on start screen!
- overlay 05
    - 0x0207E380
    - 0x0240C0
- overlay 06
    - 0x0207E380
    - 0x3440
- overlay 07
    - 0x0207E380
    - 0xBFC0
- overlay 08
    - 0x0207E380
    - 0xF160
- overlay 09
    - 0x0207E380
    - 0x014320
- overlay 10
    - 0x020A2780
    - 0x019B60
    - loaded on start screen, and while building
- overlay 11
    - 0x020A2780
    - 0x20
    - also 32 bytes of 00
- overlay 12
    - 0x020A2780
    - 0x7F20

so we have 13 overlays, two of which are empty, and a maximum of two can be loaded in at once.
the two locations are `0x0207E380` for 00-09 and `0x020A2780` for 10-12
