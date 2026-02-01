---
layout: default
title: Dynamics
nav_order: 10
parent: "Features"
---

## Dynamics (ff, s.p, sfz etc.)

Dynamics are encoded with `dynam` control events within the corresponding `measure`. Coded dynamics in MuseScore are encoded as text, such as `pp`. Dynamics with mixed text and coded dynamics, such as `sempre pp` or `molto ff`, are also supported.

In addition to the text, the dynamic code is encoded in `@label`. Multi-line dynamics is also supported.

Import of dynamic encoded with `@tstamp` attribute is also supported, even though these will not be preserved. Only dynamics for which a `chord`, `note`, or `rest` corresponding to the `@tstamp` can be found will be imported.

Relevant tests:
{% include test file="dynamic-01" %}

Known limitations:

* Text formatting (i.e., italic, bold, etc.) within a text element is currently not preserved.
