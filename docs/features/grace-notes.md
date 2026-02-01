---
layout: default
title: Grace notes
nav_order: 6
parent: "Features"
---

## Grace notes

Grace notes are encoded as `graceGrp` with the appropriate `@attach` and `@grace`. Preceding grace notes are encoded with `@attach="pre"`, and ending (i.e., following) grace notes with `@attach="post"`. For preceding grace notes, the acciaccature will have a `@grace="unacc"` and appogiature `@grace="acc"`. For ending grace notes, the value is `@grace="unknown"`. The grace groups will contain `chord`, `note` and `beam`. Note duration are encoded as standard MEI duration in `@dur`.

For wider compatibility, MEI import also supports grace notes encoded without being wrapped within a `graceGrp`. One limitation of this approach is that ending grace notes are not supported. The grace notes will always be attached to the following `chord` or `note`, or ignored if appearing at the end of a measure.

Relevant tests:
{% include test file="gracenote-01" %}
{% include test file="gracenote-02" %}
