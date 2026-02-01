---
layout: default
title: Other features
nav_order: 15
parent: "Features"
---

## Other features

### Ottava lines

Relevant tests:
{% include test file="octave-01" %}

### Hairpins

Relevant tests:
{% include test file="hairpin-01" %}

### Lyrics

Relevant tests:
{% include test file="lyric-01" %}
{% include test file="lyric-02" %}
{% include test file="lyric-03" %}

Known limitations:

* Any SMuFL character within a lyric is considered to be an elision character
* Elision character is always SMuFL character `lyricsElision` (U+E551)

### Figured bass

Relevant tests:
{% include test file="fig-bass-01" %}

### Note articulation (stacc.)

Relevant tests:
{% include test file="artic-01" %}

Known limitations:

* Chord lines (i.e., `doit`, `scoop`, `plop`, etc.) are not supported

### Ornaments such as mordents and turns

Relevant tests:
{% include test file="ornam-01" %}
{% include test file="mordent-01" %}

### Arpeggios

Relevant tests:
{% include test file="arpeg-01" %}

### Piano pedal marks

Relevant tests:
{% include test file="pedal-01" %}

### Rehearsal marks

Relevant tests:

% include test file="reh-01" %}

### Bow tremolo

Relevant tests:
{% include test file="btrem-01" %}

### Measure Repeat

Relevant tests:
{% include test file="measure-repeat-01" %}

### Colors

Relevant tests:
{% include test file="color-01" %}
