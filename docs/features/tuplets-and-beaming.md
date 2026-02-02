---
layout: default
title: Tuplets and beamings
nav_order: 7
parent: "Features"
---

## Tuplets and beaming

Tuplets are encoding with `tuplet` elements with corresponding `@num` and `@numbase`. Bracket and number styles and tuplet placement are encoded in `@num.place`, `@num.visible`, `@num.format`, `@bracket.place`, `@bracket.visible`.

Beams automatically calculated in MuseScore are exported as `beam` elements. However, these are not reimported as such. During the import, `beam` are ignored and beaming is performed by the MuseScore beaming algorithm.

Beam modes in MuseScore (e.g., forcing the start of a new beam, or joining beams) are exported as `@type` attributes as follow:

* Beam start as `beam@type="mscore-begin"`
* Beam middle (joining of a beams) as `note|rest|chord@type="mscore-beam-mid"`
* No beam as `note|rest|chord@type="mscore-beam-none"`
* 16th sub beam as `note|rest|chord@type="mscore-beam-begin16"`
* 32nd sub beam as `note|rest|chord@type="mscore-beam-begin32"`

Relevant tests:
{% include test file="beam-01" %}
{% include test file="beam-02" %}
{% include test file="beam-03" %}
{% include test file="tuplet-01" %}
{% include test file="tuplet-02" %}
{% include test file="tuplet-03" %}

Known limitations:

* Nested tuplets (tuplet within tuplet) are not supported.
* Feathered beams are not available in MEI Basic.
