---
layout: default
title: Title frame
nav_order: 4
parent: "General structure"
---

## Title frame (page head)

The top (first) text frame in MuseScore is encoded as `pgHead`. Text elements are placed and size according to their type:

* Title: top-center, size `x-large`
* Subtitle: top-center, size `large`
* Composer: bottom-right, size `normal`
* Poet (lyricist): bottom-left, size `normal`
* Instrument excerpt: top-left, size `normal`

The `pgHead` is organized in `<rend>` elements (up to 9) representing positions aligned with `@halign` and `@valign`. Each text element is encoded in its own `<rend>` with the desired `@fontsize`. The type of the text element is encoded in `@type`. For example:

```xml
<pgHead>
   <rend halign="center" valign="top">
      <rend type="title" fontsize="x-large">Ach Gott und Herr</rend>
   </rend>
</pgHead>
```

Text element on multiple lines is supported will be encoded as mixed content and `lb`.

Relevant tests:
{% include test file="page-head-01" %}
{% include test file="page-head-02" %}

Known limitations:

* Text formatting (i.e., italic, bold, etc.) within a text element is currently not preserved.
