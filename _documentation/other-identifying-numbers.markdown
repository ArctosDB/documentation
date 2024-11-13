---
title: Other Identifying Numbers (Other IDs) and Relationships
layout: default_toc
---

# Other Identifying Numbers (Other IDs) and Relationships

**Other IDs** (identifiers) are any identifiers applied to specimens. These
identifiers may allow tracking records (as in the case of collector
numbers), reference other resources (*e.g.*, GenBank numbers), or form
relationships among specimens (such as hosts of parasites).

## Other Identifier Type

`Coll_Obj_Other_ID_Num . Other_ID_Type VARCHAR2(75) not null`

This field describes the kind of identifier 
using a [controlled vocabulary](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type).

### Cleanup In Progress

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)

Note that many types are legacy and should not be used. Cleanup is in progress. ``identifier`` is the correct type for most situations.




## ID Issued By

ID Issued By is the Agent issuing the identifier. "Issuing" may involve any process of creating the identifier, such as a collector writing something in a notebook or on a tag, or a subdivision of NCBI creating a URL representing a genetic sequence. Note that this allows very fine-scaled "typing" of identifiers; a subdivision of a department within an institution is easily achievable and wholly unambiguous, for example. Much of this functionality has traditionally - and very roughly - been embedded into type, or as part of the identifier itself (such as a collector's initals prefixing their collector number).

## ID Assigned By

ID Assigned By is the Agent assigning the identifier to a catalog record. Note that some identifiers may be assigned by bot agents, and these should receive extra scrutiny. This information is generally extracted from the user's environment rather than being asserted.

## assigned_date

Date on which identifier was assigned.

## ID References

ID References is a [controlled vocabulary](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctid_references)
defining the item to which the other ID was originally applied. "Self"
is the value used when an ID was applied to the current item; all other
values create a (sometimes-resolvable) relationship to another item.
Note that the "other half" of an ID-created relationship does not
necessarily resolve to a cataloged item (though it should), and is not
limited to other records in Arctos (relationships can be formed to any
online resource).

A special type ("[Arctos record GUID](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type)") is available for linking records within Arctos. This type ensures that identifiers and issued by agent are properly formed.

Various tools are available for detecting and creating reciprocal relationships, or a [bot](https://handbook.arctosdb.org/documentation/bot.html) may be enabled to fully automate this process.

## remarks

A remarks field is available for any clarifying information.

## General Guidelines

Be as specific and complete as possible in choosing both an Other ID
Type and assigning an Other ID Number. Everything that follows is an
elaboration of this simple concept.

Other ID numbers are in a zero-or-one-or-many:1 relationship with
Cataloged Items. There is no limit to the number of Other IDs that may
be assigned to a catalog item, and there is no implication that IDs must
be unique, particularly identifying, or even useful. Capture every
identifier associated with a specimen – someone at some time considered
the identifier useful, and may wish to locate the specimen using it.

Loaned specimens occasionally return with de-facto other IDs (in the
form of attached barcodes, GenBank numbers, "personal numbers," etc.).
Record all these as Other IDs.

## Choosing Type

Identifiers are in a state of limbo as of this writing, and type is not generally understood. Failure to comply with the following will result in lower-quality data, will prevent discovery of the record and related data, and will prevent full integration in the [Extended Specimen Network](https://doi.org/10.1093/biosci/biz140).

### Local Identifiers

If the identifier applies to something like the organization of your local freezer and is generally not intended to be a useful component of the Extended Specimen Network, then a local identifier type (such as [AF](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#af) or [NK](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#nk) is appropriate. These generally have locally-meaningful rules and do not need (and are not allowed) an issued agent.

### Arctos References

To reference another record in Arctos, use [Arctos record GUID](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#arctos_record_guid). This type requires metadata, but will generally be able to automate the addition of such from partial information (such as the triplet).

### Personal Catalogs

To reference a person's personal catalog, [collector number](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#collector_number) or [preparator number](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#preparator_number) should be used.

### Lot-at-location

[field number](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#field_number) is appropriate for cataloging e.g., lots of fish. (This is not a recommendation for such traditional practices!)

### Organism

[Organism ID](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#organism_id) is appropriate for referencing a parent Organism. These are often (but not necessarily) cataloged in the [Arctos:Entity](https://arctos.database.museum/collection/Arctos:Entity) collection, and many tools for assembling Organisms exist. Only one Organism ID is allowed.

### separated data

[UUID](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#uuid) (expected, but not required, to be of the form described [here](https://en.wikipedia.org/wiki/Universally_unique_identifier)) is useful for linking data together in the absence of better identifiers.

### all other identifiers

All other identifiers are properly entered as type [identifier](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type#identifier). This type should always have metadata, and some data require precise handling.

* GenBank may only issue identifiers of the pattern ``http[s]://[www].ncbi.nlm.nih.gov/nuccore/{code}``, and must be issued by [https://arctos.database.museum/agent/21349032](https://arctos.database.museum/agent/21349032)
* NCBI BioProject may only issue identifiers of the pattern ``http[s]://[www].ncbi.nlm.nih.gov/bioproject/{code}``, and must be issued by [https://arctos.database.museum/agent/21349072](https://arctos.database.museum/agent/21349072)
* NCBI SRA may only issue identifiers of the patterns ``http[s]://[www].ncbi.nlm.nih.gov/sra/{code}`` or ``http[s]://[www].ncbi.nlm.nih.gov/Traces/sra/sra.cgi\?run={code}``, and must be issued by [https://arctos.database.museum/agent/21349034](https://arctos.database.museum/agent/21349034)
* NCBI BioSample may only issue identifiers of the pattern ``http[s]://[www].ncbi.nlm.nih.gov/biosample/{code}``, and must be issued by [https://arctos.database.museum/agent/21348953](https://arctos.database.museum/agent/21348953)
*BOLD may only issue identifiers of the patterns ``http[s]://[www].boldsystems.org/index.php/Public_RecordView?processid={code}`` or ``http[s]://[www].boldsystems.org/connectivity/specimenlookup.php?processid={code}``, and must be issued by [https://arctos.database.museum/agent/21348931](https://arctos.database.museum/agent/21348931)
* MCZ:Mala may only issue identifiers of the pattern ``http[s]://mczbase.mcz.harvard.edu/guid/MCZ:Mala:{code}``, and must be issued by [https://arctos.database.museum/agent/21347821](https://arctos.database.museum/agent/21347821)
* MCZ:Mamm may only issue identifiers of the pattern ``http[s]://mczbase.mcz.harvard.edu/guid/MCZ:Mamm:{code}``, and must be issued by [https://arctos.database.museum/agent/21355896](https://arctos.database.museum/agent/21355896)
* MCZ:Orn may only issue identifiers of the pattern ``http[s]://mczbase.mcz.harvard.edu/guid/MCZ:Orn:{code}``, and must be issued by [https://arctos.database.museum/agent/21355897](https://arctos.database.museum/agent/21355897)






## How To

Instructions for doing specifc tasks related to identifiers in Arctos

 - [How to Record Prior Inclusion in Another Collection](https://handbook.arctosdb.org/how_to/How_To_Add_Object_Provenance.html)
 - [Searching Arctos](/how_to/How-to-Search-for-Specimens)
 - [How to Identify National Park Specimens](https://handbook.arctosdb.org/how_to/National-Park-Specimens.html)

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/other-identifying-numbers.markdown" target="_blank">here</a>.
