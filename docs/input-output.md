---
layout: default
title: Input and output
nav_order: 2
---

Import and export in integrated in MuseScore (as of version 4.2). File opening and file saving follows the same workflow as for other external file formats (e.g., MusicXML).

## File opening

MEI files can be imported from the `Open...` menu with a selection of `*.mei` files:

<img width="639" alt="image" src="https://github.com/rism-digital/MuseScore/assets/689412/397c3e8c-ce50-4c63-a4f6-bd369851c092">

Previously opened MEI files appear in the file list with a dedicated `<xml> 🎵 MEI` file icon:

<img width="443" alt="image" src="https://github.com/rism-digital/MuseScore/assets/689412/69df21e0-d449-476c-b8e1-b2c1f5ccd60e">

The `Preferences` dialog includes a MEI checkbox option `Import MEI layout` in the `Import` section:

<img width="881" alt="image" src="https://github.com/rism-digital/MuseScore/assets/689412/bd71e7cf-f148-4b03-9f8c-10c021cbb58c">

## File saving

MEI files can be saved through the `Export...` menu that includes an MEI section. The MEI section includes an option `Include page and system breaks` as well as the standard part extraction option:

<img width="804" alt="image" src="https://github.com/rism-digital/MuseScore/assets/689412/cc2bf69b-baa9-4316-a237-b70b6b533767">

## User feedback

When possible, some feedback is provided when features cannot be imported. The feedback is shown in dialog that allows for the process to be continued if desirable:

<img width="514" alt="image" src="https://github.com/rism-digital/MuseScore/assets/689412/cb26cec3-5d9c-45e7-987f-209e6c58f10d">

Additional lower-level feedback might be provided in the logs

## Metadata

The following metadata tags from the [Project properties](https://musescore.org/en/handbook/4/project-properties) are exported to the MEI header:

* Work title
* Subtitle
* Arranger
* Composer
* Copyright
* Lyricist
* Translator

```xml
<meiHead>
    <fileDesc>
        <titleStmt>
            <title type="main">Work title</title>
            <title type="subordinate">Subtitle</title>
            <respStmt>
                <persName role="arranger">Arranger is me</persName>
                <persName role="composer">Composer is me</persName>
                <persName role="lyricist">Another lyricist</persName>
                <persName role="translator">Deepl</persName>
            </respStmt>
        </titleStmt>
        <pubStmt>
            <date isodate="2023-05-09-14:34:46" />
        </pubStmt>
    </fileDesc>
</meiHead>
```

{: .warning }
The tags `Creation date`, `Platform` and `Source` are currently **not imported** since no appropriate place in MEI-Basic has been found

When importing an MEI file, the values in the MEI header (if found) are set back as score properties. The entire MEI header is also preserved. When exporting again to MEI, the original header is re-exported as such, and the score properties are ignored. However, the original MEI header can be deleted from the score properties dialog.

## Command-line

The conversion from and to MEI through MuseScore is possible with standard MuseScore command-line options.

For example, converting a MuseScore file to MEI:

```shell
mscore file.mscz -o file.mei
```

Converting an MEI file to MuseScore:

```shell
mscore file.mei -o file.mscz
```

The option `-f` can also be added to by-pass score corruption warnings.
