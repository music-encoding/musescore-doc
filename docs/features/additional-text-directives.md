---
layout: default
title: Additional text directives
nav_order: 13
parent: "Features"
---

## Additional text directives

MuseScore has different types of text directives, which are encoded with `dir` using `@startid`. The following MuseScore types of directives are exported as `dir`:

* Expression
* Playtech annotation
* Staff text
* System text

The distinction of the type of directive is encoded in the `dir@type` attribute. The default is given to expressions, and others have the following values:

* `mscore-playtech-annotation`
* `mscore-staff-text`
* `mscore-system-text`

The style (normal or italic) and the position (above or below) is inferred from the type. A custom position in MuseScore is encoded in `@place`.

Relevant tests:
{% include test file="dir-01" %}

Known limitations:

* Text formatting within directives is ignored.
