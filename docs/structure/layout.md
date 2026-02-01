---
layout: default
title: Layout options
nav_order: 3
parent: "General structure"
---

## Layout options

The layout option in the export dialog and the import preferences (see above) triggers writing and reading `pb` and `sb` elements.

When writing, all page and line (system) breaks are encoded into the MEI. The ones manually entered in MuseScore have a `@type="mscore-manual"`.

When reading the MEI, only `pb` and `sb` with `@type="mscore-manual"` are set as page and line breaks and all the others are ignored.

Relevant tests:
{% include test file="breaks-01" %}
