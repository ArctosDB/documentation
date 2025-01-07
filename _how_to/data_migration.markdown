---
title: How To Migrate Data Into Arctos 
layout: default_toc
author: Teresa J. Mayfield-Meyer
date: 2024-07-01
---

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)

# How To Migrate Data Into Arctos

This How To walks through the steps of data migration. These steps are more completely outlined in the numbered issue templates in the [Arctos Data Migration Github repository](https://github.com/ArctosDB/data-migration).

## Manage Collection(s)

Before any data is entered, it is important that the collection metadata is complete.


* Github Issue Template: [3. Manage Collection](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=3--manage-collection.md&title=Acronym+Collection+-+3.+Manage+Collection)

## Create Your Arctos Team

At least one person at any institution will have an operator account created as part of creation of the collection(s). Anyone else who will assist with data migration or data entry will need to follow the same steps to become an Arctos operator.

* Documentation: [Agents](http://handbook.arctosdb.org/documentation/agent.html) 
* Handbook instructions: [How To Create and Manage Your Arctos Team (Users and Operators)](https://handbook.arctosdb.org/how_to/How-to-Create-your-Arctos-Team-Users-and-Operators.html)
* Github Issue Template: [4. Create an Arctos Team](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=4--create-an-arctos-team.md&title=Acronym+Collection+-+4.+Create+an+Arctos+Team)

## Agents

People and organizations are associated with almost all types of data available in Arctos so it is important to map the names in use in your current data to names available in Arctos. Ensure that all People (collectors, preparators, makers, identifiers, event assignors, donors) in your data file are included as Agents in Arctos and that there are no duplications (same person with name spelled different ways). If you are entering records one at a time, you will probably return to this step every time you enter something.

* Documentation: [Agents](http://handbook.arctosdb.org/documentation/agent.html) 
* Handbook instructions: [How To Create Agents](https://handbook.arctosdb.org/how_to/How-to-Create-Agents.html)
* Github Issue Template: [5. Agents](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=5--agents.md&title=Acronym+Collection+-+5.+Agents) 

### Permissions
Agents are a shared resource in Arctos and care should always be given to editing existing agents and efforts made to not create duplicate agents. At least one person at every institution should have permission to [manage agents](https://arctos.database.museum/Admin/user_roles.cfm#manage_agents). This person should read the documentation about Agents above and respond in the appropriate Github issue that they understand that Agents are a shared resource in Arctos and they understand how to manage them. Once this is complete, they will be given permission to [manage agents](https://arctos.database.museum/Admin/user_roles.cfm#manage_agents).

## Accessions

ALL Arctos records require an associated accession. If your institution does not currently use accessions, at least one "legacy accession" will need to be created to facilitate entry of catalog records into Arctos.

* Documentation: [Accessions](https://handbook.arctosdb.org/documentation/accession.html) 
* Handbook instructions: [How To Create an Accession](http://handbook.arctosdb.org/how_to/How-to-Create-an-Accession.html)
* Github Issue Template: [6. Accessions](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=6--accessions.md&title=Acronym+Collection+-+6.+Accessions) 

### Permissions

At least one person at every institution should have manage transactions access, this person should read the documentation above and and respond in the appropriate Github issue that they understand that Transactions are an important and useful tool for demonstrating collection building and use. Once this is complete, they will be given permission to [manage transactions](https://arctos.database.museum/Admin/user_roles.cfm#manage_transactions).

## Identifications (Taxon Names)

Identifications must match at least one Arctos Taxon Name exactly for every object record. Please note that taxon names are managed separately from classifications associated with those names. At this stage, the only concern is the name used in the identification of a catalog record.

* Documentation: [Identifications](http://handbook.arctosdb.org/documentation/identification.html) 
* Handbook instructions: [How to Create Taxa](http://handbook.arctosdb.org/how_to/How-to-Create-Taxa.html) and [How to Edit Taxa](http://handbook.arctosdb.org/how_to/How_to_Edit_Taxa.html).
* Github Issue Template: [7. Identifications (Taxon Names)](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=7--identifications--taxon-names-.md&title=Acronym+Collection+-+7.+Identifications+%28Taxon+Names%29) 

### Permissions

At least one person at every institution should have manage taxonomy access, this person should read the documentation above and and respond in the appropriate Github issue that they understand that Taxonomy is a community resource and managing it means a commitment to the community that they will do their best to reduce the possibility of misspelled taxon names and to only edit classifications with information that they are certain make the classification more accurate. Once this is complete, they will be given permission to [manage taxonomy](https://arctos.database.museum/Admin/user_roles.cfm#manage_taxonomy).

## Higher Geography

Higher Geography values (Country, State, County) in your data file must exist in Arctos before data can be bulkloaded.

* Documentation: [Higher Geography](https://handbook.arctosdb.org/documentation/higher-geography.html)
* Github Issue Template: [8. Higher Geography](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=8--higher-geography.md&title=Acronym+Collection+-+8.+Higher+Geography) 

## Locality

Every object record may be assigned a locality (e.g. place of collection). Localities include coordinates used for mapping.

* Documentation: [Localities](http://handbook.arctosdb.org/documentation/locality.html) 
* Handbook instructions: [How To Create a Locality](http://handbook.arctosdb.org/how_to/How-to-Create-a-New-Specific-Locality.html)
* Github Issue Template: [9. Locality](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=9--locality.md&title=Acronym+Collection+-+9.+Locality) 

Localities may be treated in several different ways.

* If you have many specimens from a single specific locality, you may want to create that locality, name it, and use the locality name in your bulkload file. 
* You can also bulkload your data with the localities you have entered

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Caution.jpg) **Caution**  

Localities that are exactly alike should load as a single locality shared by many specimens, but just one little difference (a capital letter or period, for example) will create two localities when you think there is only one.  These can be merged later, if you find them.

### Permission

At least one person at every institution should have manage locality access, this person should read the documentation above and and respond in the appropriate Github issue that they understand that localities are a community resource and managing them means a commitment to the community that they will do their best to reduce the possibility of misspelled place names and to only edit localities with information that they are certain make the location more accurate. Once this is complete, they will be given permission to [manage locality](https://arctos.database.museum/Admin/user_roles.cfm#manage_locality).

![](https://raw.Githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) **Pro Tip**

At this point, records can be loaded to Arctos and the remaining data can be added to them using component loader tools. This can simplify the process of data migration and allow for more detailed review of components such as attributes, parts, collectors, preparators, and identifiers.

* Github Issue Template: [11. Bulkload Legacy Data](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=11--bulkload-legacy-data.md&title=Acronym+Collection+-+11.+Bulkload+Legacy+Data) 

## Catalog Record Agent Roles

People who participate in the [Collection Object: Agent Roles](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctcollector_role) related to a catalog record must be Agents. If a person in a catalog record agent role is not well-known enough to create an agent, their role can be recorded using the [verbatim agent](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type#verbatim_agent) atttribute with the role listed in the attribute method.

* Documentation: [Attributes](https://handbook.arctosdb.org/documentation/other-identifying-numbers.html)
* Handbook instructions: [How to Create and Edit Catalog Record Attributes](https://handbook.arctosdb.org/how_to/How-to-Create-and-Edit-Attributes.html)

If not loaded with the rest of the catalog record, agent roles may be loaded with the [Agent Role: Bulkload](https://arctos.database.museum/loaders/BulkloadCollector.cfm) tool.

## Parts

Part names (object descriptions) must match to the available [Part: Names](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctspecimen_part_name) in Arctos. Part names must be selected for use by each individual collection. For instructions on how to select the parts you want to use - see [How To Video](https://drive.google.com/file/d/1nmCFYhNaX5z3VM8_8UZXZ_MszdsQskJy/view?usp=drive_link). If you need to add a part name that is not included in the code table, you will need to request it and provide a definition for the part.

* Documentation: [Parts](https://handbook.arctosdb.org/documentation/parts.html)
* Handbook instructions: [How To Create and Edit Parts](https://handbook.arctosdb.org/how_to/How-to-Create-and-Edit-Parts.html)
* Github Issue Template: [10. Parts](https://github.com/ArctosDB/data-migration/issues/new?assignees=&labels=&projects=&template=10--parts.md&title=Acronym+Collection+-+10.+Parts) 

### Part Attributes

Parts may be associated with many part attributes and the attribute type must match a term in [Part: Attribute Types](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpart_attribute_type) in Arctos. It is preferable to use part attributes rather than placing this information in part remark so that the data is more discoverable.

If not loaded with the rest of the catalog record, parts may be loaded with the [Part+Attribute Bulkload](https://arctos.database.museum/loaders/BulkloadParts.cfm) tool.

## Attributes

Attributes must match to the available [Collection Object Attribute: Types](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type) in Arctos. Attributes must be selected for use by each individual collection. For instructions on how to select the attributes you want to use - see [How To Video](https://drive.google.com/file/d/1nmCFYhNaX5z3VM8_8UZXZ_MszdsQskJy/view?usp=drive_link). If you need to add an attribute, you will need to request it and possibly provide a controlled vocabulary for the attribute value (for example, sex is the attribute, with possible values of male, female, etc.).

* Documentation: [Attributes](https://handbook.arctosdb.org/documentation/attributes.html)
* Handbook instructions: [How to Create and Edit Catalog Record Attributes](https://handbook.arctosdb.org/how_to/How-to-Create-and-Edit-Attributes.html)

If not loaded with the rest of the catalog record, attributes may be loaded with the [Attribute: Bulkload](https://arctos.database.museum/loaders/BulkloadAttributes.cfm) tool.

## Identifiers

Every catalog record in Arctos has a catalog number, but often objects have been shared, transferred, or given identifiers by individuals other than the institution that holds them now. Every catalog record in Arctos can have multiple identifiers other than the Arctos catalog number. In addition to identifiers assigned to the cataloged item(s), identifiers may be used to document relationships to other catalog records or data.

* Documentation: [Other Identifying Numbers (Other IDs) and Relationships](https://handbook.arctosdb.org/documentation/other-identifying-numbers.html)
* Handbook instructions: [How To Record Prior Inclusion in Another Collection](https://handbook.arctosdb.org/how_to/How_To_Add_Object_Provenance.html)

If not loaded with the rest of the catalog record, identifiers may be loaded with the [Identifier: Bulkload](https://arctos.database.museum/loaders/BulkloadOtherId.cfm) tool.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/data_migration.markdown" target="_blank">here</a>.
