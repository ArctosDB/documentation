---
title: Higher Geography
layout: default_toc
author: Dusty McDonald
date: 2024-12-15
---


![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)


# Geography

Geography has been defined (https://github.com/ArctosDB/internal/issues/366) in Arctos to reflect the administrative nature of asserted geography data. For example, many marine-focused collections wish to assert both marine (where the event took place) and terrestrial (eg perhaps the adjacent land from which permits are issued) geography for various reasons, while there is little or no overlap in spatial definitions of these places.

## Structure

### geog_auth_rec_id

Primary key, internal, not stable.

### continent

A continent is the largest, terrestrial, contiguous geographic region or area as defined by accepted sources and that meet the needs of Arctos users. First level division. We currently recognize seven continents: Africa, Antarctica, Asia, Europe, North America, Oceania, South America.

Source: Wikipedia and GBIF.
Contents: Links: https://en.wikipedia.org/wiki/Continent#Number_of_continents; https://gbif.github.io/gbif-api/apidocs/org/gbif/api/vocabulary/Continent.html

### ocean

An ocean is a conventional division of the global body of salt water into a basin as enumerated by accepted sources that meet the needs of Arctos users. First level division. We currently recognize five: Arctic Ocean, Atlantic Ocean, Indian Ocean, Pacific Ocean, Southern Ocean

Sources: Wikipedia and IHO.

Links: https://en.wikipedia.org/wiki/Ocean; https://www.vliz.be/en/imis?module=ref&refid=78851; https://marineregions.org/gazetteer.php?p=browser 


### sea

Definition: A sea is a subdivision of an ocean. Seas are usually larger than lakes, and usually smaller than an ocean and frequently surrounded by more landmass. Second level division.
Most seas will be associated with a first level division ocean, but unlike administrative regions, an ocean is not an absolute requirement for the Sea to be used as the highest level in Higher Geography. For example: Gulf of Oman, Mediterranean Sea, Bass Strait may not have an associated Ocean.

Sources: Wikipedia, Marine Regions, IHO.

Links: https://en.wikipedia.org/wiki/List_of_seas_on_Earth; https://www.vliz.be/en/imis?module=ref&refid=78851; https://marineregions.org/gazetteer.php?p=browser 

Contents: The initial list will contain the 105 IHO Sea Areas from Marine Regions. This list can be seen here: https://arctos.database.museum/place.cfm?sch=geog&sea=_.

Waterbodies that are considered “marginal seas” can be considered as Seas for purposes of higher geography concatenation ( source: https://en.wikipedia.org/wiki/List_of_seas_on_Earth#Largest_seas_by_area )

### waterbody

(Awaiting definition by the Arctos Geography Committee)


### country

 A sovereign state, nation or other first-level political entity as listed with an listed by ISO country code. Acceptable values are available in referenceable gazetteers and compendia; Arctos currently has adopted the Database of Global Administrative Areas (GADM) for its internal administrative boundaries (i.e., Admin0).

Source: GADM and identified backup (Wikipedia) for missing or erroneous data 

Link: (https://gadm.org/index.html) and identified backup (Wikipedia) for missing or erroneous data
Contents: see GADM (Admin0 0)




### state_prov


The primary administrative subdivision of a country as listed by the Arctos country authority (i.e., GADM Level 1 or State/Province).
Source: GADM and identified backup (Wikipedia) for missing or erroneous data 

Links: (https://gadm.org/index.html) and identified backup (Wikipedia) for missing or erroneous data

Contents: see GADM (admn 1)


### county


Definition:  The secondary administrative subdivision of a Level 1 State/Province as listed by the Arctos country authority (i.e., GADM Level 2 or US county). Level 2 divisions will be created by Community approval only when there is a special need and a significant history of stability. The following are the only entities approved for this treatment:
United States 

United Kingdom (source: geography cleanup: United Kingdom arctos#5178)


Source: GADM and identified backup (Wikipedia) for missing or erroneous data 





### quad

(Awaiting definition by the Arctos Geography Committee)


### feature

References [ctfeature](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctfeature)

(Awaiting definition by the Arctos Geography Committee)


### island_group

References [ctisland_group](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctisland_group)

(Awaiting definition by the Arctos Geography Committee)


### island

(Awaiting definition by the Arctos Geography Committee)


### source_authority

GADM for administrative terrestrial terms, IHO for marine/aquatic terms. Wikipedia for terms where GADM and IHO authorities are lacking. 

### geog_remark

Information in this field is intended to provide guidance and clarification in future geography creation or merge events, and is not searchable nor intended for public display.

Use remarks to describe remarkable things about the geography itself, such as when the named place existed or how it differs from potentially-confusing other places. Do not use remarks for procedural information or information concerning other data (such as specimens or localities).




### higher_geog

Generated concatenation of comma-sepated terms (in the order above, as of this writing). Serves as a (unique) 'handle' for the data object; what's entered during data entry.





## Creation Guidelines

When the authorities that Arctos uses for Higher Geography are found to be out of date, missing data, or containing errors, the Geography Committee will use Wikipedia as a backup to create terms when requested by Arctos users. 

To request the addition of a higher geography term, aquatic or terrestrial, submit a code table request in the main Arctos repository (https://github.com/ArctosDB/arctos/issues/new/choose). Issues will be discussed and approved by the Geography Committee, and implemented by users with role manage_geography (Dusty, Michelle). Please include relevant links to sources for the most exclusive terrestrial unit for the requested geographies. For example, include a Wikipedia link to the relevant Admin level 0, 1, or 2 terrestrial unit, whatever is most specific to the request.
Geography Request Requirements:
* Requested geography term must be present in GADM, IHO, or Wikipedia (when GADM or IHO are lacking). 
* Ideally, GADM or IHO term is linked to a shape file, ensuring that the geographic term is grounded in reality. When the term is from Wikipedia, the Geography Committee will evaluate the request based on consistency, reasonableness, and benefit to the requesting collection and the organization overall.
* GADM administrative terms that are a subdivision of a higher level administrative division must include the higher level term(s). For example, a GADM Level 1 division (state or province) must be preceded by the Level 0 entity (the country the state is in). 
* Arctos will handle in higher geography up to admin level 2 for US (other countries to be discussed and handled later, as requested by members of the community)



# Spatial

Spatial data are maintained separately from geography, and may be used to failitate search or suggest spatial affiliation.



## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/higher-geography.markdown" target="_blank">here</a>.
