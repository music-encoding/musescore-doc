---
layout: default
title: Chord labels and roman numerals
nav_order: 12
parent: "Features"
---

## Chord labels and roman numerals

Chord labels and roman numerals in MuseScore are encoded with `harm`. In the export, the plain text (as entered by the user) is encoded as text content of the `harm`, with no formatting. When importing, the text is re-processed by MuseScore.

For distinguishing between chord labels and roman numerals, a `harm@type` attribute is used with `mscore-roman` for roman numerals.

Relevant tests:
{% include test file="chord-label-01" %}
{% include test file="roman-numeral-01" %}

Known limitations:

* Chord labels or roman numerals attached to a voice for which there is no note or rest are ignored.
