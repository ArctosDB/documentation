---
title: Record Data Entry
layout: default_toc
author: DLM
date: 2024-10-28
---

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)

# Data Entry: The Big Picture


All record entry goes through a table named ``bulkloader``. There are several ways to write to this table, and any number of others are possible. The loader scripts may be set to load the record, or to load the record and trigger any UUID-linked records in 'component loaders' to also load.


## Current

### Arctos Entry Form

There is a generic record entry form provided as part of the Arctos UI.

### Record Bulkloader

## Documentation

Documentation is provided as a Google Sheet: [https://docs.google.com/spreadsheets/d/1VbNC3k17WAHMum_qD5UYoXxUUWwXXh5gZSM5vfGvRzU](https://docs.google.com/spreadsheets/d/1VbNC3k17WAHMum_qD5UYoXxUUWwXXh5gZSM5vfGvRzU)

## Possibilities

Various points of expansion have been discussed, or are available but not used.

### API

The loader has been implemented as an API (albeit one primarily intended for local consumption, an easy state to change) for well over a decade; authorities are available from the API. Developing a local tool that directly interacts with Arctos should be straightforward.

### Multiple Entry Forms

[issue](https://github.com/orgs/ArctosDB/discussions/8052) - there's been inconclusive discussion about having more than one entry form, possibly it/they could have baked-in rules that differ from the global form

### Collection-specific rules


[issue](https://github.com/orgs/ArctosDB/discussions/4384)  - there have been also-inconclusive discussions about adding 'when collection then....' types of rules to the bulk checker.

### Fancy-up the one shared form


[issue](https://github.com/orgs/ArctosDB/discussions/7560) - Dynamically Highlight Required Data Entry Fields is a request for UI rules in the shared form.


### Implement warnings

(no issue) - the checks currently return text, and anything other than NULL is considered a fail. PostgreSQL elegantly supports JSON, and adding warnings to the check ("Most collections of this type don't do that....") would be relatively trivial. Implementing this in a primarily-bulk ecosystem would require planning.

### Mix-n-Match

Following multiple options - e.q., lots of forms all with increased complexity - would probaly require additional resources.




## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly [here](https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/data_entry.markdown).