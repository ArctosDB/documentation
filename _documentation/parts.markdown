---
title: Parts
author: unknown, Teresa J Mayfield-Meyer, Dusty McDonald
date: unknown, 2021-07-15, 2022-08-30
layout: default_toc
---

[Add to current update request](https://github.com/ArctosDB/documentation-wiki/issues/271)

# Parts 

Parts are physical entities, in contrast to [Cataloged Items](/documentation/catalog) (an abstract entity) or binary objects
(such as Images). One or many parts may comprise a Cataloged Item, and parts may be defined as the minimal units for which [storage location](/documentation/container), usage, and condition are tracked. (*"Parts are things to which you can stick barcodes."*) Parts are generally the equivalent of [dwc:MaterialSample](https://dwc.tdwg.org/terms/#materialsample)

## Part Names

`specimen_part . part_name VARCHAR(255) not null`

 - [Value Code Table](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctspecimen_part_name)

Part names provide information about the physical objects associated with the catalog record. They can be subsampled, loaned, and have one or more attributes associated with them.

Part names should refer to specific anatomical parts or recognized groups of parts (*e.g.*, "postcranial skeleton"). With rare exception, part names are the singular form of a noun. There is no requirement to include a part in a catalog record.

A part name should be entered for each distinct physical object associated with the catalog record *e.g*., ***skull*** and ***postcranial skeleton***. Parts already contained in the ***postcranial skeleton*** may be entered on separate lines for clarity when necessary. An acceptable list of part names in a catalog record might be:

* skull
* postcranial skeleton
* right humerus

Such an entry would designate a postcranial skeleton that has a disarticulated right humerus. Situations like this are 
typically created when a subsample is removed for a loan. The addition of appropriate part condition, disposition, remark, and/or attribute are used to clarify.

## Disposition


Disposition describes the curatorial status of parts. Values are controlled by a [code table](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctdisposition). [Github discussion](https://github.com/ArctosDB/arctos/issues/7605#issuecomment-2091521078) [Code Table Committee discussion](https://docs.google.com/document/d/1eZ_S8VTp-m5Wrbb6cAK96ODPZpt2-Hvnvt6yfU9qVwg)

## Condition

`Coll_Object . Condition VARCHAR(255) not null`

Condition is free-text generalized with very limited metadata. It may be used used for entries such as "broken" or "dissected." 

The community recommends following condition ratings be used specifically to parts with the "is_tissue" flag see [Tissue](##Tissue):

-   5 – The best tissues. These have gone from a freshly killed animal
    directly into liquid nitrogen. The animal should not have been dead
    for more than thirty minutes.
-   4 – These are tissues taken from animals only a few hours post
    mortem at cool temperatures. Such tissues should not have been
    previously frozen and thawed.
-   3 – These are tissues taken from an animal that has been dead less
    than sixteen hours at cool temperatures, or tissues taken from an
    animal that was hard frozen soon after death and then thawed
    for preparation. Fur is not slipping.
-   2 – These tissues may be beginning to show signs of decomposition.
-   1 – These tissues are flaccid and thoroughly autolyzed. They
    probably stink.

Note that there are many part attributes that may confirm or conflict with the information in condition. These include, but are not limited to:

1. [condition report](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#condition_report) is basically condition, but without the structural limitations (eg you can fully expose how things change over time) and with full metadata
2. [preservation](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#preservation)
3. [preservation need](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#preservation_need)
4. [remaining volume](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#remaining_volume)
5. [storage temperature](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#storage_temperature)
6. [tissue quality](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type#tissue_quality) 

## Lot Count

`Coll_Object . Lot_Count NUMBER(22) not null`

A **Lot Count** is an integer that enumerates how many similar items
comprise a part. The value is frequently one (1), but collections of
fish and invertebrates usually assign a single catalog number to all of
the individual organisms of one species from one collecting event.
Thus, 86 minnows of one species from one place, collected at the same
time, and stored together in one jar of alcohol would be a cataloged
item with one part, and that part would have a lot count of 86 whole
animals.

Lot counts are not static; lots may be split into smaller lots by
creating a separate part. If one of those 86 minnows was prepared for
skeletal study by clearing and staining, it would be necessary to create
a second "part" within the catalogued item, *e.g.:*

| Catalog \#         | Part Name          | Pres Method        | Lot Cnt            |
|--------------------|--------------------|--------------------|--------------------|
| 123456             | whole animal       | alcohol            | 85                 |
| 123456             | skeleton           | cleared and stained| 1                  |

A cryotube of embryos or a box of ribs should have a lot count. In
contrast, three tubes of muscle from an individual will be tracked
separately; these should be entered as three collection objects, each
with a lot count of one.

There must be a value of at least one (1) for each part, and the maximum
is 99999. Lot counts are sometimes approximate. For example, a
three-liter jar of small minnows in alcohol might be given a lot count
of 400, at least until such time as someone counts the minnows.

Examples of lot count usage:

| Material                             | Entry                                |
|--------------------------------------|--------------------------------------|
| Two embryos stored in the same crytube      | embryo (lot count = 2)               |
| Two liver samples stored in individual tubes         | liver (lot count = 1)               |
| Three tubes each containing five nematodes     | nematode (lot count = 5) <br/> nematode (lot count = 5) <br/> nematode (lot count = 5)             |
| Ten vertebrae in a box               | vertebra (lot count = 10)            |
| A jar of five salamanders of the same species from the same collecting event.                    | whole animal (lot count = 5)     |

## Sampled From

`Specimen_Part . Sampled_From_Obj_ID NUMBER(22) not null`

Sampled From designates a part derived from another part. This functionality may be used to 
create tissue subsamples for destructive analysis, split particularly valuable samples into multiple freezers to
eliminate single-point failure risk, to better track a specific bone (_e.g._, for loan), or for any other situation
which results in one part being split into multiple parts or altered into a new type of part.

## Remarks

`Coll_Object_Remark . Coll_Object_Remarks VARCHAR2(4000) null`

Use remarks to document non-standard information pertaining to the specimen part. 
Do not use remarks for any information which could be recorded with more structure elsewhere, 
including [Part Attributes](/documentation/attributes).

## Preservation

<div style="margin:1em;padding:1em;border:2px solid red; background-color:rgb(249, 242, 244);">
NOTE: The definition of Tissue above is being deprecated, and embedded preservation information is being removed from part names. The following will become definitive as the migration is completed.
</div>

Part Preservation is controlled by a [code table](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTPART_PRESERVATION). Any part may have any number of preservation events, and like all Part Attributes they may include date and determiner information. "Tissueness" is an attribute of preservation.

* A part with no preservation attributes is not a tissue
* A part with one or more preservation attributes having a NULL preservation flag is not a tissue
* A part with one or more preservation attributes having a TRUE preservation flag may be a tissue, except
* A part with one or more preservation attributes having a FALSE preservation flag cannot be a tissue

For example, a part preserved in "90% ethanol" would be a tissue, unless it also has an additional (probably earlier) "formalin" attribute.

# Record Search Results

Record Search Results column "partdetail" contains "core" part information formatted as [JSON (JavaScript Object Notation)](https://en.wikipedia.org/wiki/JSON). JSON is a 
lightweight data exchange format capable of representing complex data (_e.g._, multiple parts each with multiple child attributes)
as simple text strings. Most browsers will "pretty print" 
JSON data, making these data very human-readable.

The most simple data will be one part and it's direct metadata:

```
[
  {
    "part_name": "skull",
    "lot_count": "1",
    "disposition": "in collection",
    "condition": "unchecked",
    "barcode": "",
    "container_path": "",
    "remark": "",
    "attributes": []
  } 
]
```

Many specimens will contain data for multiple parts:
```
[
  {
    "part_name": "skull",
    "lot_count": "1",
    "disposition": "in collection",
    "condition": "unchecked",
    "barcode": "",
    "container_path": "",
    "remark": "",
    "attributes": []
  },
  {
    "part_name": "study skin",
    "lot_count": "1",
    "disposition": "in collection",
    "condition": "unchecked",
    "barcode": "",
    "container_path": "",
    "remark": "",
    "attributes": []
  }
]
```
And some specimens will also contain part attribute data for one or more of the parts:
```
[
  {
    "part_name": "study skin",
    "lot_count": "1",
    "disposition": "in collection",
    "condition": "unchecked",
    "barcode": "",
    "container_path": "",
    "remark": "",
    "attributes": [
      {
        "attribute_type": "location",
        "attribute_value": "Cabinet 12; Drawer 5",
        "attribute_units": "",
        "determined_date": "",
        "determiner": "",
        "attribute_remark": ""
      }
    ]
  }
]
```

## How To

Instructions for doing specifc tasks related to Parts in Arctos

 - [How To Create and Edit Parts](https://handbook.arctosdb.org/how_to/How-to-Create-and-Edit-Parts.html)
 - [How To Bulkload Parts](https://handbook.arctosdb.org/how_to/How-to-Bulkload-Parts.html)
 - [How To Create Part Attributes from Containers](https://handbook.arctosdb.org/how_to/How-To-Create-Part-Attributes-from-Containers.html)

   
## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/parts.markdown" target="_blank">here</a>.

# Community Discussion

[Github Issue #271](https://github.com/ArctosDB/documentation-wiki/issues/271)
