---
layout: default
title: Fermata and breath
nav_order: 11
parent: "Features"
---

## Fermata and breath

Fermata are encoded with `fermata` control events within the corresponding `measure`. They are attached to a `note`, `chord` or `rest` with `@startid`. Fermata attached to the end bar line of a measure are a special case and are encoded with the appropriate `@staff` and `@tstamp` and not with `@startid`.

Import of fermata encoded with `@tstamp` attribute is also supported, even though these will not be preserved. Only dynamics for which a `chord`, `note`, or `rest` corresponding to the `@tstamp` can be found will be imported. There is one exception for `fermata` with a `@tstamp` pointing to the end of the measure. These will be imported as a fermata attached to the end bar line.

For fermata with a custom shape, the MEI `@shape` attribute is used, i.e., for `angular` and `square` fermatas. Otherwise, `@glpyh.auth` and `@glyph.name` is used.

Breath are also encoded with a control event within the corresponding measure. However, the MEI element is `breath` or `caesura`, as appropriate. 
The `@glyph.auth` and `glyph.name` is encoded when the breath or caesura is not the common one.

Import with `@tstamp` encoded breath and caesura works as long as as corresponding element can be found.

Import of fermata, breath and caesura with `glyph.num` is also supported.

Relevant tests:
{% include test file="fermata-01" %}
{% include test file="breath-01" %}

Known limitations:

* The vertical position of a breath and caesura is different (lower) after import.
