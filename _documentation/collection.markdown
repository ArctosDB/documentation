---
title: Collection
layout: default_toc
author: DLM
date: 2024-07-18
---

# Collection

An Arctos collection is a group of co-managed records. Most collections are "traditional," (eg MVZ Mammal Collection, [https://arctos.database.museum/collection/MVZ:Mamm](https://arctos.database.museum/collection/MVZ:Mamm)) but there are few  technical constraints. User access roles (VPD partitions) are collection-based.

## Creating

To create a collection, see [https://handbook.arctosdb.org/how_to/new-collection.html](https://handbook.arctosdb.org/how_to/new-collection.html).

"Core tables" are as follows.

----------------

## Collection

### collection_id

Internal primary key (integer), not to be exposed in public UI nor confused with collectionID (generated from guid_prefix).

### guid_prefix

The "functional primary key" which most usefully defines a collection in Arctos. Used as part of the catalog record identifier which each record in Arctos recieves. Forms collectionID (a GUID) when prefixed by ``https://arctos.database.museum/collection/``. Note that this is a concept with no dependencies; it is completely unrelated to ``institution_acronym``, ``collection_cde``, all other fields in all other tables, and all other data. Must never be allowed to change; please see <a href="https://en.wikipedia.org/wiki/Replication_crisis" target="-blank">Replication Crisis</a> for more information.

* <a href="https://handbook.arctosdb.org/best_practices/GUID.html" target="_blank">Best Practices: Create a meaningful GUID Prefix</a>


### citation

Recommended text for citing the collection. Cataloged items within a collection should be cited by record GUID (or as directed by the collection). This text applies only to the collection, not to any items linked to or managed by the collection.

### catalog_number_format

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcatalog_number_format](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcatalog_number_format). We encourage the use of the integer format for catalog numbers. This makes sorting, review for number gaps, and determining the last catalog number used an easy task. The other options do not allow for predictive, series- or range-based tools.

### genbank_collection

Collection identifier as registered with NCBI. Used to automatcally find records in GenBank. 

* [Management Information](https://handbook.arctosdb.org/documentation/genbank.html)

### web_link and web_link_text

Used to make links to the collection's web page from the Arctos UI.

* web_link is a public URL
* web_link_text is the "clickable text"

### collection

Free text short description of the collection, possibly useful for sorting.

### institution_acronym

Used to group collections in UI, and serves as a VPD partition for managing containers.


### institution

Free-text.

### collection_cde

Legacy column, can be useful for selecting 'suggested' authority items.


### loan_policy_url

A loan policy is required by Arctos, but the contents of the policy are at the discretion of the collection. The loan policy should provide a path through which qualified users can request material, access, etc. The policy might also outline who is eligible to access materials or collection, expectations for citations, etc. A loan policy should not be confused with a loan or material transfer agreement, which is the document shared between collections and borrowers when and if a loan is finalized. The value of this field is a document posted at a regular public URL which can be updated by the collection.


### internal_license_id

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctdata_license](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctdata_license).

An internal license is a legally-binding document which applies to data downloaded from Arctos.


### external_license_id

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctdata_license](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctdata_license). 

An external license is a legally-binding document which applies to data shared outside or Arctos, for example through DarwinCore. Data which has been through this process are less-complete and less-connected than data from Arctos, and a less-stringent license may be appropriate. Re-using the internal license here is also fully acceptable. Note that some "portals" have license requirements, and may refuse to publish date which does not meet those requirements. Example: [GBIF Terms of Use](https://www.gbif.org/terms)


### collection_terms_id

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcollection_terms](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcollection_terms).


Terms are a well-considered code of conduct intended to supplement and clarify licenses that anyone who uses data downloaded from a collection is expected to uphold. These terms should model a set of ethical behaviors and help us to build a vibrant community intended to support efforts to make collection data as complete, discoverable, and accessible as possible. Collections wishing to provide their own terms must also provide a URL for the document; an Arctos-wide approach is encouraged where possible.  Terms should not be confused or counfounded with data licenses, loan policies, or loan agreements.



* Discussion: [https://github.com/ArctosDB/arctos/issues/7861](https://github.com/ArctosDB/arctos/issues/7861)


### default_cat_item_type

Allows a collection to specify a default value for [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcataloged_item_type](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcataloged_item_type) in records. The record bulkloader will translate NULL to this value, and values provided in the record bulkloader will override this value.


### preferred_identifiers 

Prioritize certain identifiers in UI using [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_other_id_type). Useful for "local identifiers" only.

### preferred_identifier_issuers 

Prioritize certain identifiers in UI using Issued By Agent. Useful for linking identifiers, eg highlighting participation in the Extended Specimen Network.

### collection_agent_id

Foreign key to Agents. All collections have a coresponding Agent, which provides data structure for additional information.


------------------


## collection_attributes

Collection_Attributes provides a very flexible structure for storing collection-related data, such as that used to build .eml files for sharing with DWC portals.


### attribute_type

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcollection_attribute_type](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcollection_attribute_type)

### attribute_value

### attribute_remark

### created_date and created_agent_id

Environment-derived metadata.


-----------------------


## collection_templates

Collection_Templates provides a mechanism to store information for one-click filling certain forms, such as loans and shipments.

### template_type

Controls access

### template_name 

User-supplied identifier

### template_data

Data (generally serialized JSON)

### created_date and created_agent_id

Environment-derived metadata.


-------------------------


## collection_contacts

Collection_Contacts links agents to collections in roles. These are used to direct error logs, messages, and provide metadata in .eml files.

### contact_role

Foreign key to [https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_contact_role](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcoll_contact_role)

### contact_agent_id

Foreign key to Agent.

--------------------

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly [here](https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/collection.markdown)
