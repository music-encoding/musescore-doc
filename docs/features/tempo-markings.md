---
layout: default
title: Tempo markings
nav_order: 9
parent: "Features"
---

## Tempo markings

Tempo indications are encoded with `tempo` control events within the corresponding measure. They are attached to a `note`, `chord` or `rest`.

The text of the tempo indication is encoded as text withing the `tempo` element. This can be mixed content (text mixed with additional elements) with `rend` or `lb` elements for representing SMuFL characters, or line breaks, respectively. For the SMuFL characters, the `@glyph.auth="smufl"` is set on the `rend` that wraps them.

The tempo value is encoded as `@midi.bpm`. And additional `@type="mscore-infer-from-text"` is added for indication for which MuseScore is expected to infer the tempo value from the text.

Relevant tests:
{% include test file="tempo-01" %}

Known limitations:

* Spanning tempo indications (e.g., ritardando) are currently not supported.
