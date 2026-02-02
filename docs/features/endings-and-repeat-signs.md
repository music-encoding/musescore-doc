---
layout: default
title: Endings and repeat signs
nav_order: 8
parent: "Features"
---

## Endings and repeat signs (jumps such as D.S. or D.C.)

Voltas are encoded with `ending` elements. The text of the volta is encoded in `@label`. Open voltas will have a `@lendsym="none"`. The styling of the line is encoded in `@lform` with `dashed` and `dotted` possible values.

Sound processing parameters of the voltas are encoded with `@type`, with the repeat list encoded with one attribute value for each entry in the list. Namely `mscore-repeat-1 mscore-repeat-3` for a list value `1,3` in MusesScore.

Jump and marker elements are encoded with `repeatMark`. The `@func` stores the type for Marker (`coda`, `segno ` and `fine`) and Jump (`dalsegno` and `dacapo`).

An additional `@type` attribute is used to encoded the specific MuseScore type. For example:

* `repeatMark@type="mscore-marker-varied-coda` for the MuseScore coda variation.
* `repeatMark@type="mscore-jump-dc-al-double-coda` for the MuseScore jump D.C. al Double Coda.

Relevant tests:
{% include test file="ending-01" %}
{% include test file="jump-01" %}
{% include test file="jump-02" %}

Known limitations:

* For Jump, values for jumpTo, playUntil and continueAt are not exported and default values are assume during import. Similarly, the default value for label is used for Marker during import.
* Import uses default values for the text content for both Jump and Marker.
