---
title: Higher Geography
layout: default_toc
author: Dusty McDonald, Teresa J. Mayfield-Meyer
date: 2023-01-15
---

# Geography

Geography has been defined (https://github.com/ArctosDB/internal/issues/366) in Arctos to reflect the administrative nature of asserted geography data. For example, many marine-focused collections wish to assert both marine (where the event took place) and terrestrial (eg perhaps the adjacent land from which permits are issued) geography for various reasons, while there is little or no overlap in spatial definitions of these places.

## Creation Guidelines

(Geography should not be created or modified until the Arctos Geography Committee has established guidelines and updated this document.)

# Spatial

Spatial data are maintained separately from geography, and may be used to failitate search or suggest spatial affiliation.


![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)


# ---------------------------------------------------------
# ----------------------------------------------------------
# Important: Everything below this line is outdated and wrong

I'm temporarily leaving this here because it might be a handy reference for building the new


# Important: Everything below this line is outdated and wrong
# ---------------------------------------------------------
# ----------------------------------------------------------


# Higher Geography

Higher Geography is "assertable" spatial geography and will be limited to:

## [GADM](https://gadm.org/maps.html)

As of October 12, 2022, only those GADM Levels 0, 1 or 2 that were in use were added to Arctos. Note that they will contain "spatial data source GADM" in remarks.<a href="https://github.com/ArctosDB/arctos/issues/5155#issuecomment-1276792090" target="_blank">GitHub</a> 

To request addition of new GADM Level 0, 1 or 2 geography, please <a href="https://github.com/ArctosDB/arctos/issues/new?assignees=&labels=&template=geography-request.md&title=%5B+geography+request+%5D" target="_blank">file an issue</a>.

### Level 0 or Country
 
GADM Level 0 or Country is the familiar concept of first-level political entity and will exist in Arctos globally.

### Level 1 or State / Province

GADM Level 1 or State/Province is a primary subdivision of a country, be it state, province, department, or okrug and will exist in Arctos globally.

### Level 2 or County

GADM Level 2 is a second-level political subdivision of a country, regardless of local labels. level 2 divisions will be created by Community approval only when there is a special need and a significant history of stability. The following are the only entities approved for this treatment:

* United States (source: it is known)
* United Kingdom (source: https://github.com/ArctosDB/arctos/issues/5178)
 
## [IHO World Seas](https://iho.int/)

As of October 12, 2022, all IHO Seas should now be in Arctos and have spatial data. Note that they will contain "spatial data source iho_world_seas" in remarks. <a href="https://github.com/ArctosDB/arctos/issues/5155#issuecomment-1276792090" target="_blank">GitHub</a>
 
## Other Options

There will also be options when geography should or cannot be asserted:
* we don't know - <a href="https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=69" target="_blank">no higher geography recorded</a>
* we refuse to say - <a href="https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=10016350" target="_blank">no specific higher geography</a>

# Unassertable Higher Geography

Anything will be eligible to be "unassertable" geography or spatially aware features, including but in no way limited to

* [continents](https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=4962)
* [parks](https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=10004785)
* [islands](https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=1005324)

Search will use intersections of geography and locality in addition to asserted geography. That is, a record which maps to Yosemite will be findable by:

* Park
* County/counties
* State
* Country
* Continent

Making the record also discoverable by region ("The West") or ecoregion (Sierras) or WHATEVER will involve only creating a spatially-aware feature.

Note that no search functionality hinges on what's asserted. Asserting Mariposa County and "we refuse to say" are functionally equivalent when the locality maps to the bits of Mariposa County that are within Yosemite.

<img src="https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20FAQ.jpg" width="50"> 

# FAQ
## How do I record the locality "Africa"?
Continents are not assertable geography. If the only locality information available is a continent, use the following:
* higher geography = <a href="https://arctos.database.museum/place.cfm?action=detail&geog_auth_rec_id=10016350" target="_blank">no specific higher geography</a>  
* specific locality = Africa

# Community Discussion
* [GitHub Issue #275](https://github.com/ArctosDB/documentation-wiki/issues/275)


**Suggest removing everything below except guideline stuff and some might be useful for eventual locality attributes**

is a combination of terms delineating geopolitical
units and it includes many imprecise regions. These terms are
descriptively applied to [Localities](locality). In so far as counties
occur within states, states within countries, and countries within
continents, these data are approximately hierarchical, but only
approximately. For example, a state park or national forest may be
comprised of segments from two or more counties. Columns in the Higher
Geography table are concatenated into the column [`higher geography`](#higher_geog)
which is uniquely indexed. The concatenated
string "higher geography" is the only column displayed and used in data
entry. Unfortunately, you cannot assume that any locality or area is
listed under only one higher geography. The [guidelines](#guidelines)
below are intended to prevent (and even remedy) such inconsistencies.



## Continent / Ocean

`Geo_Auth_Rec . Continent_Ocean VARCHAR(50) not null`

All records in Higher Geography have a value in
this field. A record with the value "no higher geography recorded" is applied to
specimens with no geographic data. Western Russia is in Europe, eastern
Russia is in Asia. Both are sometimes in Eurasia.


| [Terrestrial](#terrestrial_marine)   | [Marine](#terrestrial_marine)        |
|--------------------------------------|--------------------------------------|
| North America                        | North Pacific Ocean ([Area D](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans"))       |
| Central America                      | South Pacific Ocean ([Area E](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans"))       |
| South America                        | Arctic Ocean ([Area A](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans"))       |
| Europe                               | South Atlantic Ocean ([Area C](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans"))       |
| Asia                                 | North Atlantic Ocean ([Area B](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans"))      |
| Africa                               | Indian Ocean ([Area F](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans")) |
| Australia                            |                                      |
| Antarctica                           | missing data: "no higher geography recorded"  |



## Map Name (Quad)

`Geo_Auth_Rec . Quad VARCHAR(30) null`


 The name of the U. S. Geological Survey topographic map quadrangle. The name of the quad should include the map scale. Ex. 'Ambler River 1:250,000'. The 1:250,000 series has been used because Alaska lacks anything as inclusive counties; “quads” have been used extensively in organizing collections and interrogating data (Although note that a combination of Borough and Census Area is all-inclusive and mutually exclusive and therefore serves as a suitable if large-scale “county substitute.”). Finer scale quads are used by other collections as sub-county level geography.


## Geographic Feature

`Geo_Auth_Rec . Feature VARCHAR(50) null`


 Features include named entities such as parks,
preserves, refuges, and other delineated geo-political features. Feature
may also be used to describe recognized [sub-groups of
islands](#island_group). Many administrative units included in Feature
have ephemeral boundaries, if not an ephemeral existence. Their past and
future use may be inconsistent. Therefore, avoid using Feature if the
locality is well georeferenced and/or unequivocal in the absence of
Feature.


## Island Group

`Geo_Auth_Rec . Island_Group VARCHAR(50) null`


 is defined as the largest island group or Archipelago
to which an island belongs. Island groups within island groups should be
indicated in [Geographic Feature](#feature).


| Sea                | Island Group       | Feature            | Island             |
|--------------------|--------------------|--------------------|--------------------|
| Bering Sea         | Aleutian Islands   | Andreaonof Islands | Adak Island        |


## Island

`Geo_Auth_Rec . Island VARCHAR(50) null`


 When a locality includes an island name, and the locality is
on or near an island, then the name of the island should be included in
this field. An island is included in this field if a locality has the
word "island" in its proper name even though (depending on the tides) it
may be a peninsula. (Rhode Island is nevertheless a state.) An offshore
locality that is associated with, and near, an island should include the
island. For example, if the Verbatim Locality is "100 yds off of the
beach, Bay Farm Island, Alameda Co., California", then the Higher
Geography record should include:


| Country        | State          | County         | Island         | Specific Locality       |
|----------------|----------------|----------------|----------------|----------------|
| United States  | California     | Alameda County | Bay Farm Island| 100 yds off of the beach, Bay Farm Island    |

On the other hand, a locality description may include an island only as
a point of reference, *e.g.,*"456 nautical miles SSE of Midway Island."
In this case, inclusion of data in the island field is inappropriate.
The island name should be included in the island field even though it
may be the same as the specific locality, *e.g.,*

| Country        | State          | County         | Island         | Specific Locality       |
|----------------|----------------|----------------|----------------|----------------|
| United States  | California     | Alameda County | Pin Head Island| Pin Head Island|



Names should be spelled out, including the word "island" when it is part
of the name. Some valid island names:

-   Saint Lawrence Island
-   Spitzbergen
-   Dangerous Reef

## Source

Source is limited to the URL of a page on Wikipedia. English is strongly preferred; Spanish is acceptable. (Contact us 
with other needs.) If such a
page does not exist, it should usually be created. However, in some
instances such a page would be overly redundant or conflict with
Wikipedia guidelines, in which case the next-most-specific entry is
appropriate. Examples follow.

  | Geography  | Source   | Explanation |
  |------------|----------|-------------|
  | North America, United States, Alaska | http://en.wikipedia.org/wiki/Alaska | Well-defined unambiguous entity – yay us! |
  | North America, United States, Alaska, Ambler River Quad | http://en.wikipedia.org/wiki/Alaska | There is no Wiki page for USGS quad maps. The data are unambiguous (there is or is not an appropriate USGS quad map) and mostly internal, so a general citation is tolerable, if not entirely appropriate. |
  | North America, Beaufort Sea, United States, Alaska | http://en.wikipedia.org/wiki/Beaufort_Sea | This is "Arctos shorthand" for "Beaufort, probably West of the Canandian border." The relevant Wikipedia article is the Sea. Note also that a geospatial search on this general area finds 7 geography entries; georeferencing is critical when geographic data is ambiguous. Best practice would be to avoid this sort of undefinable geography altogether.|
  | North America, United States, Alaska, Mt. McKinley Quad, Denali National Park and Preserve | http://en.wikipedia.org/wiki/Denali_National_Park_and_Preserve | There is no Wikipedia entry for the area of Alaska that’s within both DNP and a USGS quad, so pick the most specific available. |


## Start Date and Stop Date

Start Date and Stop Date must be given as an ordered pair or not at all. These are parenthetically included in the higher_geography concatenation.

### For Geography Admins

Dates are often not known to even year precision. Elaborate on any assumptions or guesses in remarks. Delete any unused geography records with dates as you encounter them.

### For Catalog Records

Dates signify less-than-ideal geography, often without spatial data. Do not use these data if it is possible to avoid them, and "upgrade" any catalog records to avoid these data as resources permit.

## Higher Geography

`Geo_Auth_Rec . Higher_Geog VARCHAR(255) not null`


 (as a specific data field) is a the actual concatenation of the subdivisions described above. This is the value that is displayed in most applications.



## Field Summary

| Category                            | Examples                | Short Definition |
|-------------------------------------|-------------------------|------------------|
| [Continent/Ocean](#continent_ocean) | North America, Arctic Ocean |  An all-inclusive set of divisions of the globe. |
| [Country](#country)                 | United States, Iraq, Tibet | **The primary political entity.** |
| [State/Province](#state_province)   | Florida, Magadanskaya oblast | Primary subdivision of a country, whatever its formal rank. |
| [Sea](#sea)                         | Bering Sea, Gulf of Mexico  | A subdivision of an ocean. (See [chart](http://memory.loc.gov/cgi-bin/image-services/jp2.py?data-/home/www/data/gmd/gmd9/g9096/g9096a/ct003193.jp2&res-2 "Chart of the Limits of Seas and Oceans").) |
| [County](#county)                   | Lincoln County, Cajun Parish | County, parish, or equivalent subdivision of a state or province. |
| [Map Name (Quad)](#map_name)        | Fairbanks, Beaver | Names of quadrangles delineated by USGS 1:250,00 map series. |
| [Feature](#feature)                 | Kenai National Wildlife Refuge, Anza Borrego State Park |  Miscellaneous named and delineated entities below the level of state. |
| [Island Group](#island_group)       | Alexander Archipelago, Franz Joseph Land | **A named (but sometimes poorly defined) group of islands. These data are often replicated in Feature.** |
| [Island](#island)                   | Kodiak Island, Svalbard | A single island. |



Additional Data

In addition to the "formal" fields, the Edit Geography form provides for
any number of UTF-encoded additional identifiers. These should not be
considered "formal"

terms, but as search aids. The "any geography" specimen search field
will consider these data, and they will be displayed on Specimen Detail.

Usage Example:

-   **Asia, Russia, Kamchatka Oblast** (Formal term)**

    **
    -   Камча́тская о́бласть (Native character encoding)
    -   Kamchatskaya oblast (Common variant or transliteration)

## Remarks

A remarks field is also provided. Information in this field is intended
to provide guidance and clarification in future geography creation or
merge events, and is not searchable nor intended for public display.


## Guidelines for Geographic terms in Arctos


Geographic terms are difficult to standardize because:

-   They originate in many different languages, and alphabets.
-   They are correctly but variously presented using different
    translation and transliteration protocols.
-   They are frequently changed by political processes.

Scrupulous consistency is essential. With inconsistent data, users will
not find what they’re looking for, and operators will not be able to use
import tools. The primary function of these guidelines is to promote
consistent, predictable data across Arctos; while proper data in a
single record is important, more important is being consistent at scale
(across states, islands or island groups, countries, and ultimately all
of Arctos). These guidelines have been developed to facilitate consistency,
and to allow tools which facilitate consistency to exist. Do not deviate from
the Guidelines without contacting the AWG.


-   Contact us if you encounter any difficulty in following these Guidelines. 
-   **Be consistent**. At the largest practical scale (usually \~country),
    do the same thing for all records. For island nations, ensure that
    the island data are consistent. Ensure all county-level records
    include qualifiers (County, Parish, etc.) or that none do.
-   **Be certain that the term you intend to create does not
    already exist**. Alternative spellings, transliterations, or
    abbreviations are probable. If you are creating a new state or
    province, first look carefully at all the unique values for
    State/Province from the relevant country. These values can be
    especially confusing if the term refers to an area where the Roman
    alphabet is not used.
-   **Use current definitions, where possible.** For example: Yugoslavia no longer exists, so use
    Slovenia, Croatia, or whichever country the locality is *now* in, especially if cataloging current material. If
    Yugoslavia was used in the original data, it now belongs in verbatim
    locality, *not* in Higher Geography. If you are editing specimen
    records, append the old higher geography to verbatim locality in the
    following order: verbatim_locality, state, country. We will support Higher Geography of deprecated countries, state/provinces for     legacy materials but STRONGLY urge curators to view this as a short-term solution and re-assign as appropriate. Any Geography term can have synonyms and alternate names to maximize discoverability. We will support WKT footprints for modern geography only.
-   **Try not to mix older terms; use modern geography**. We have no idea
    how to do that when, *e.g.*, one Province of Kenya becomes
    6 Counties. Especially in the case where the "new" shares
    namestrings with the old, confusion is almost certain. (Alternative
    interpretation: Geography is names, not shapes, and it doesn’t
    matter if "Naples" can refer to a dozen THINGS in Italy.)
-   **Use the spelling of geographic term that is in the title of the
    English version of Wikipedia’s entry for that term (but see below)**.
    Wikipedia describes most (possibly all) of the world’s current
    politically-delineated geographic units. Do not use something
    transcribed from a label or fieldnotes for a new value in
    Higher Geography. Look it up in Wikipedia. If it doesn’t exist, and
    you are sure it’s valid, create the article in Wikipedia.
-   **Enter the full (English strongly preferred; Spanish acceptable) Wikipedia URL under
    "Authority" of the geography entry**; it will be automatically
    converted to HTML. The Wikipedia link must directly describe the
    Arctos record.
    - DO Link to the Wikipedia page which directly describes the resource.
    - DO NOT link to anchors in general articles, lists, maps,
    images, vaguely-related entities, "parent" entities (except in cases described under [source documentation](#source)) or anything 
    other than the specific relevant article
    in Wikipedia. 
-   **No accents, umlauts, Cyrillic, Chinese, etc. Do use ASCII-128.**
    Arctos has bitwise indexes and the specimens from non-US/ASCII
    geography will be invisible in geographic searches. This may require
    that you modify the Wikipedia spelling; for example, Huánuco must
    become Huanuco.
-   **Avoid punctuation. Spell it out.** Avoid terms like "Turks & Caicos" - "Turks and Caicos" is much less likely to cause confusion or become part of a duplicate situation. 
-   The overriding goal is to have exactly one set of terms describing
    the most precise (NOT necessarily the smallest) formally named and
    delineated geographic term that is applicable to localities. There
    can be ten terms referring to things that overlap or are contained
    within "Inyo County," but there should be exactly one thing that
    *is* Inyo County.
-   Google is your friend. "{local word for county} County" is no
    longer amusing. New York City isn’t in Inyo County, Texas, no matter
    what it says on the label. (Label data should be transcribed
    to verbatim_locality.)
-   **Do not introduce unnecessary descriptors or ranks, but also do not
    exclude parts of proper names**. "Santiago Metropolitan Region" in
    state_prov is correct; Maule Region in state_prov is redundant
    and confusing. Use the construction used by Wikipedia.
-   **Do not partially translate**. "Región de la Araucanía" (disallowed
    under rules "use English Wikipedia" and "use ASCII128") should be
    entered as "Araucania", not "Region de Araucania" or "Region
    Araucania."
-   **Do not "promote" entities**. Cities, vaguely-described districts,
    4th-level administrative entities, and things the collector made up
    are verbatim_locality and should not be stuffed into geography.
    Chilean Communes, for example, are "real" political entities, but as
    sub-county-level divisions are not formal geography.
-   **Do "standardize" spelling**. Sometimes you’ll have to do something
    arbitrary, and that’s OK as long as you do the same arbitrary thing
    for all versions of the entity. Provincia de Aysén, región Aysén del
    General Carlos Ibáñez del Campo is entered as "South America, Chile,
    Aisen, Aisen," for example, because "Aisen" is a somewhat-common
    transliteration, not because it’s any particular form of "correct."
    **Do not use Arctos fields for data which are not categorically appropriate. Do not use island for an island group, for example.
-   **Use only "official" abbreviations**. "Wrangell–**St.** Elias National
    Park and Preserve" is correct. "Something **Prov.**" is
    never acceptable.
-   No parentheticals, cryptic square brackets, inline
    translations, etc.
-   ~~No unnecessary punctuation or separators. *Kenya, North Eastern
    Province*, never *Kenya, North-Eastern Province.*~~
-   **DO include any equivalent data excluded by these "rules" in "search
    terms."** These are becoming increasingly valuable in automated
    mapping to Arctos (and reducing duplicates); please MINIMALLY copy
    all of the "alternate names" (such as Spanish place names containing
    diacritics or "local" names given in Arabic or Thai characters) from
    Wikipedia into individual search terms fields.
-   **Do NOT include descriptive text (such as the language in which a
    term is given) in search terms.** Along with facilitating access to
    data, search terms are also used by data cleanup tools, and things
    which are not search terms in the search terms field will prevent
    those tools from working properly. Do not confound search terms
    with remarks.
-   **Do NOT include non-equivalent information, such as island
    "subgroups" or alternate spellings of "parent" geography (country,
    state, etc.) data in search terms.**
-   **Use remarks to describe remarkable things about the geography
    itself, such as when the named place existed or how it differs from
    potentially-confusing other places.** Do **not** use remarks for
    procedural information or information concerning other data (such as
    specimens or localities).
-   See
    [Iran](http://arctos.database.museum/geography.cfm?geog_auth_rec_id=10000319)
    for an "complete" example.
-   Contact us if you encounter any difficulty in following these Guidelines. 

## Guidelines for assigning geography to specimens.


A primary purpose of Higher Geography is to facilitate finding
specimens, and so a primary curatorial goal should be to facilitate that
usage. Arbitrarily or improperly linking geography to specimens WILL
result in users not finding what they’re looking for. For example, if
point *X, Y* is described by both Geography *A* and *B*, queries for
either "*A*" or "*B*" will find some unknowable subset of the intended
specimens, and provide no clue to the user that there are additional
suitable specimens assigned to another geography entry, thereby failing
to provide the user with an accurate answer and decreasing the overall
value of the specimens and their associated data.

Specimens should be linked to their geographical origin. Do NOT use geography as a reference. A specimen with specific locality "20 miles west of Monterey, CA" should
be linked to Pacific Ocean, not California.

1.  Geography is not a replacement for Agents. Use accession roles,
    projects, etc., to *e.g.*, recognize contributions from the National
    Park Service.
2.  Whenever possible, georeference localities, even crudely. Geographic
    terms in Arctos are a mess, but georeferenced specimens can pull
    geographic data from webservices or GIS at will.
3.  A huge number of specimens say "Bla County" but have a geospatial
    error that extends well beyond Bla County. Consider error when
    determining geography from coordinates and when determining
    coordinates from geography.
4.  The Edit Locality form will detect variation of geography used in
    nearby georeferences and in identical specific locality strings.
    Unify these data when possible.
5.  Localities should link to the most specific Higher Geography possible.


## Special Use Cases
There are two special use cases where assigning a single administrative geography to a record is not possible. For example, legacy records may not have complete or have missing locality information, in which case the locality is simply "no specific locality". For those records, **"no higher geography recorded"** is appropriate.  The second example is for records which do have locality information but are not limited to a single site and single administrative geography. For example, an archival or cultural record may be an item with entries or components spanning several locations on more than one continent, in which case, using **"no specific higher geography"** is appropriate. (We do assume it's from planet Earth.)


## Searching Guidelines

Higher Geography should be viewed as "semi-arbitrary
curatorially-assigned string" rather than "singular definitive
placename." A specimen with a very precise and accurate georeference
might be assigned to a state, state+USGS map quadrangle, state+county,
state+feature (*e.g.*, military reservation), or any combination of
these and more. These assignments depend on collection-specific
curatorial practices, the information available when a specimen was
cataloged, and various other factors. Especially for cross-collection
queries, it is often advisable to search "Any Geographic Element" (which
considers [webservice-derived data](#service)) or to search using the
"Select on Google Map" option. Both of these methods work best with
georeferenced specimens; additional or exploratory queries may be
necessary to find all relevant specimens. Use the contact link at the
bottom of any Arctos page for assistance.



## Terrestrial versus marine descriptors

Coastal localities should be described with terrestrial descriptors. For
offshore localities, the Higher Geography should include at least the
ocean in [Continent/Ocean](#continent_ocean) and, if applicable, it
should also include [Sea](#sea). (Therefore, "coastal" specimens are
often impossible to location by descriptive geography queries.)



## Webservice Data

In addition to curatorially-asserted data, Arctos also uses data from
various web services to:

-   automatically suggest geographic coordinates
-   reverse-georeference – i.e., derive descriptive geographic terms
    from asserted coordinates

This often adds searchable standardized data, but sometimes results in
erroneous results. Service-derived data are viewable under Edit
Locality, and searchable through "Any Geographic Element." Use more
precise terms (Continent, Feature, etc.) to avoid the inclusion of these
secondary data. See also [Additional Data](#additionaldata).

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/higher-geography.markdown" target="_blank">here</a>.
