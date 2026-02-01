---
layout: default
title:  Measure numbering
nav_order: 1
parent: "Features"
---

## Measure numbering

Measure numbers in MuseScore are integers automatically incremented. They are encoded in `measure@n`. When a measure is excluded from the measure count in MuseScore, no `@n` is provided.

Irregular (e.g., a pickup measure) will have a `measure@metcon="false"`.

MuseScore also has the option of adding a number to the measure count. The value is taken into account when writing and reading `measure@n`.

For end bar lines with a repetition, the number of sounding repetitions given in MuseScore is encoded as `@type="mscore-repeat-n` where `n` is the value of the repeat parameter in MuseScore.

Relevant tests:
{% include test file="measure-01" %}
{% include test file="measure-02" %}

Known limitations: 
* The MuseScore barline type `Reverse final` does not exist in MEI, it is exported as double `dbl` barline.
* Measure numbers with text (e.g., `3a`) are represented by text elements in MuseScore and are currently not exported.