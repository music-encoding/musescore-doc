---
layout: default
title:  Time signatures
nav_order: 2
parent: "Features"
---

## Time signatures

Time signature changes occurring at all staves are encoded in a `scoreDef` change. When the time signature change is not the same on all staves, or is occurring only on some staves, a `scoreDef` with appropriate `staffDef` descendants is generated.

Relevant tests:
{% include test file="time-signature-01" %}
{% include test file="time-signature-02" %}
