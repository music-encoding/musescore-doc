---
layout: default
title: Notes and rests
nav_order: 5
parent: "Features"
---

## Notes and rests

Supported chord, note and rest durations range from long to 512th. Chords with different note durations are not supported.

Stem direction are encoded in `@stem.dir`. When the stem direction is set for notes within a beam, then all notes have a `@stem.dir`. (This could eventually be changed to `beam@place` if it is added to MEI-Basic.)

Stemless notes are encoded with `@stem.len="0"`. (This could eventually be changed to `@stem.visible` if it is added to MEI-Basic.)

Cross-staff notation is encoded with `@staff` and the appropriate staff number value. It is supported for `chord`, `note` and `rest`. The staff displacement is constrained to one staff above or below since it seems there is not reason to allow for more than that.

Relevant tests:
{% include test file="accid-01" %}
{% include test file="accid-02" %}
{% include test file="stem-01" %}
{% include test file="cross-staff-01" %}

Known limitations:

* Enclosing accidentals are not supported (not available in MEI-Basic).
* Triple flats / sharp are not preserved in the import.
* Cross-staff for chords with only some one or some of the notes on the staff above or the staff below is not supported since this can only be achieved with a workaround in MuseScore .
