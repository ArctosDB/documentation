---
title: Character Encoding
author: DLM
layout: default_toc
---

# Character Encoding

Arctos is UTF encoded.

## Conversion

Many products are encoded in different character sets by default. It is possible that "special" characters which cannot be translated to Unicode by the tool will be converted to a placeholder character, such as � or . (The actual character depends on the tool being used. Many source characters may be converted to the same placeholder.)


## HTML

Some data are encoded with HTML escape characters rather than Unicode. These will appear visually identical in Arctos (which in general renders HTML), but are not searchable. For example, ``&aacute;`` and ``á`` will appear identical in many forms. A search for "á" will find only the latter.

## Non-printing characters

Arctos disallows characters not in POSIX character class PRINT for most fields, but things like doubled or trailing spaces can still appear in data and will make searching difficult.

## Similar Characters

Many characters, or combinations of characters, are visually similar. For example, see the [Wikipedia entry on the degree symbol](https://en.wikipedia.org/wiki/Degree_symbol).

## Special Caution

If any encoding erors are encountered, the entire dataset should be considered suspect. Consider running CSV through Google Sheets (or any equally competent converter) and explicitly saving as UTF. This step will not remove errors, but it may make them easier to discover. (ref: <https://github.com/ArctosDB/dev/issues/177>)

# Field Length

Some programs or editors silently truncate text. Arctos never will; some text length limitations exist, and violating them will always result in an error, never string manipulation.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/encoding.markdown" target="_blank">here</a>.
