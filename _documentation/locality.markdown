---
title: Locality
author: Dusty McDonald, Teresa J. Mayfield-Meyer
date: 2023-01-16
layout: default_toc
---

# Locality


A locality is a specific place associated with one or more [Collecting Events](collecting-event).  Ultimately, each locality should be a unique polygon in geographic space.  Often, the polygon is a circular estimate with the center as a point defined by [latitude and longitude](coordinates), and the radius as a linear estimate of error.  For electronic mapping, we convert such data to decimal degrees with estimates of error in meters.  Interfaces to the data are more flexible. 

A locality includes three types of data

-   [Higher geography](higher-geography) is controlled "authority data" and is included via key relationships.
-   [Georeferencing determinations](coordinates) are spatial data; they define a shape on a map. Localities may include point-radius data and/or
WKT (polygon) data.
-   Descriptive data, most importantly [Specific Locality](specific-locality). Also includes locality attributes such as [Geology](http://handbook.arctosdb.org/documentation/geology.html)

 Some caveats:

-   A locality documents one *or more* collecting events.
-   Separate but similar localities may differ only in the extent of
    their respective errors.  For example, if the specific locality
    "Barrow" is given for a lemming, it would be reasonable to assume
    the animal came from right in Barrow, or from somewhere on the
    limited road system around Barrow. Five kilometers might be
    appropriate.  If Barrow were given for the specific locality of a
    bowhead whale, then an appropriate error might be more like 50
    kilometers because whalers travel several tens of kilometers.  In
    both cases, the latitude, longitude, specific locality, and higher
    geography are potentially identical.
-   There are important differences between a Locality and a [Verbatim
    Locality](collecting-event.html#verbatim_locality), though the verbiage
    may often be the same.


## Locality Name

Locality Name is a globally-unique human-readable "locality ID"
commonly used to unambiguously associate one or more catalog records to a
locality. Named Localities:

 - Will not be auto-deleted when not used
 - Will always be unique, so will not be auto-merged

![](https://raw.Githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) **Pro Tip**

If you have absolutely no locality data, use the Locality Name **NULL Locality Data** and skip entering anything else related to locality.

## Specific Locality

`Locality . Spec_Locality VARCHAR2 (255) null`

Will appear as the column header locality_specific in bulkloading tools.

Specific Locality is a standardization of verbatim_locality.

When writing Specific Localities, the highest priority should be to maximize clarity and minimize confusion for a global audience, and for machine understanding (such as automated georeferencing). Geolocate is sometimes really picky on spelling. For example: a locality of "Lodge Pole Creek" was coming back with basically a random point - near a lodge or something a state away. "Lodgepole Creek" (which is also the label on Google Maps) returned accurate data.
    
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) 
### Pro Tips

#### Tip 1: Leave Out Higher Geography 
Do not include higher geography (continent, ocean, sea, island group, island, country, state, province, county, feature) in the Specific Locality unless it references a place-name in another geopolitical subdivision, in which case include that subdivision in parentheses. The following is located in California, but the distance is given from a location in Arizona.

**Do** | **Don't** 
-- | -- 
10 mi below Ehrenberg (Arizona), Colorado River | 10 mi below Ehrenberg, Arizona, Colorado River 

#### Tip 2: Use 'No specific locality recorded.' 
 There are some situations in which no Specific Locality is given. For example, collecting events on the high seas which are specified by geographic latitude and longitude. There are some situations in which no Specific Locality would be appropriate. For example, a collecting event with a locality that is specified in the Higher Geography with no further details. In these examples, as well as in records for which appropriate data are missing, the correct value for Specific Locality is, "**No specific locality recorded.**" (In contrast to a normal locality, this is a sentence and therefore begins with a capital letter and ends with a period.)

**Do** | **Don't** 
-- | -- 
No specific locality recorded. | North Pacific Ocean, 45 52′ 24″ N, 165 21′ 48″ W 
No specific locality recorded. | USA, Alaska

#### Tip 3: Use Proper Spelling 
 Do not anglicize words in Verbatim Locality or Specific Locality. The database supports Unicode, so the limitation is input devices (your keyboard!).

**Do** | **Don't** 
-- | -- 
Las Montañas del Norte | Mountains of the North 
Las Montañas del Norte | Las Montanas del Norte 

#### Tip 4: Use Current Name Conventions 
 If an obsolete name for a geographic place is given in Verbatim Locality, put the current name in Specific Locality, followed immediately by the obsolete name in parentheses after an "=". In this example, Whistler has historically been known as Alta Lake and Mons

**Do** | **Don't** 
-- | -- 
Whistler (=Alta Lake=Mons), N of Vancouver | Alta Lake, N of Vancouver
Whistler (=Alta Lake=Mons), N of Vancouver | Mons, N of Vancouver 

#### Tip 5: Specific to General 
 Specific Locality should start with the most specific part of the locality and end with the most general.

**Do** | **Don't** 
-- | -- 
0.25 mi S and 1.5 mi W Mt. Edith, Big Belt Mts. | Big Belt Mts., 0.25 mi S and 1.5 mi W Mt. Edith

#### Tip 6: Spell 'and' Out 
 Use ‘and’ rather than ‘&’ when describing multiple directions in localities. Do not omit the ‘and’ in favor of a comma or any other separator.

**Do** | **Don't** 
-- | -- 
Lauterwasser Creek, 1 mi N and 6 mi E Berkeley | Lauterwasser Creek, 1 mi N, 6 mi E Berkeley 
between Davis and Sacramento | between Davis & Sacramento 

#### Tip 7: Spell out Place Name Directions 
 Do not abbreviate directions when they are part of a place name.

**Do** | **Don't** 
-- | -- 
S of West Lansing | S of W Lansing 

#### Tip 8: Use 'of' 
 Use ‘of‘ to clarify the intention of a locality description.

**Do** | **Don't** 
-- | -- 
S of West Lansing | S West Lansing 

#### Tip 9: Use Decimals 
 Enter distances in decimals, not as fractions.

**Do** | **Don't** 
-- | -- 
0.5 | 1/2 
0.25 | 1/4 
0.125 | 1/8 
0.33 | 1/3 
0.67 | 2/3 

#### Tip 10: Use Leading Zeros for Decimal Fractions 
 Put a "0" before the decimal in distances between 0 and 1 units (e.g., 0.5 mi, 0.75 km).

#### Tip 11: Use Periods After Abbreviations 
 Put a period after an abbreviation **unless it is a direction or a unit of measure (e.g., mi, N, yds, etc.)**.

**Do** | **Don't** 
-- | -- 
 1 mi N junction of Hwy. 580 and Hwy. 80 | 1 mi. N. jct. Hwys 580 & 80

#### Tip 12: Do Not End Localities with a Period 
 Do not put a period at the end of the specific locality **except as part of an abbreviation**.

#### Tip 13: Use Parenthesis For Method of Travel 
 Include parentheses when giving a description such as "by road" or "by air," and place the parenthetical between the direction and the named place that it modifies.

**Do** | **Don't** 
-- | -- 
1 mi N Berkeley (by road) | 1 mi by road N Berkeley 

#### Tip 14: Only Capitalize Proper Nouns 
 Capitalize "Junction" only for proper names. When not a proper noun, "junction" should be spelled out and followed by "with" or "of."

**Do** | **Don't** 
-- | -- 
10 km S junction of Hwy. 1 and Hwy. 5 | 10 km S Junction of Hwy. 1 and Hwy. 5 
Strawberry Creek Junction | Strawberry Creek junction 

#### Tip 15: Leave out Data that Belongs Elsewhere 
 Do not include any information which is not locality-related. This includes but is not limited to comments regarding the health of an individual (put them in attributes); past or present weather (Put present weather in collecting event), terrain (put this in catalog record event), or vegetation observations (put in associated species); or local identifiers (add appropriate other identifiers or locality attribute).

**Do** | **Don't** 
-- | -- 
12.6 mi E of Gladstone, on US 56 | 12.6 mi E Gladstone, DOR on US 56 additional data collected April 1988 dead on road 11.5 grams little fat LE 11cm, WS 16cm skull ossified testes N2mm 4mm no molt
Approx 5 mi E of Alamos | Approx 5 mi E Alamos (on steep rocky hillside w/ heavy brush cover) found below lighthouse after foggy E. wind night
Zuni Webs | Zuni Webs Web 2 trap 100 ear tag #8589

#### Tip 16: Use Standard Abbreviations 
 Use only the following abbreviations:

|Word or phrase                       | Abbreviation       | Comment     |
|-------------------------------------|--------------------|-------------|
| yards                               | yds           | If space permits, spell out non-metric units. *E.g.,*"yards" |
| feet                                | ft            | If space permits, spell out non-metric units. *E.g.,*"feet" |
| meters                              | m             | |
| miles                               | mi            | If space permits, spell out non-metric units. *E.g.,*"miles" |
| kilometers                          | km            | |
| east (of)                           | E             | |
| west (of)                           | W             | |
| north (of)                          | N             | |
| south (of)                          | S             | |
| northeast (of)                      | NE            | |
| northwest (of)                      | NW            | |
| southeast (of)                      | SE            | |
| southwest (of)                      | SW            | |
| approximately, about, near, *circa* | ca.           | |
| Highway                             | Hwy.          | Only as part of a proper noun (e.g., "Hwy. 1", but not "on the highway").|
| Route                               | Rte.          | Only as part of a proper noun (e.g., "Rte. 66"). |
| Provincia, Province                 | Prov.         | |
| Departmento                         | Depto.        | |
| Road                                | Rd.           | Only as part of a proper noun (e.g., "Sunset Rd.", but not "on the road" or "by road"). |
| Mount                               | Mt.           | Only as part of proper noun in which it is spelled out (e.g., "Mount Holyoke"). |
| Mountains                           | Mts.          | Only as part of a proper noun (e.g., Rocky Mts., but not "in the mountains N Lake Tahoe"). |
| Number, NÀômero                     | No.           | |
| Avenue                              | Ave.          | |
| Boulevard                           | Blvd.         | |
| United States                       | U.S.          | e.g., U. S. Forest Service |
| University of California            | U.C.          | Should be followed by a modifier, e.g., U.C. Berkeley |
| Doctor                              | Dr.           | e.g., Dr. Pearson’s house. Do not use for "Drive" (e.g., "Sunset Drive"). |


## Elevations

`Locality . Maximum_Elevation NUMBER null Locality . Orig_Elev_Units VARCHAR2 (2) null`

`Locality . Minimum_Elevation NUMBER null Locality . Orig_Elev_Units VARCHAR2 (2) null`

[`ctlength_units`](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctlength_units)


Elevations are a height above mean sea level.  If elevation data are part of the verbatim locality, they should be entered into Minimum Elevation, Maximum Elevation, and Elevation Units (ft, m).  If the Verbatim Locality contains a range for an elevation, e.g., 500-600 ft, these values should be entered into the minimum and maximum elevation fields, respectively.  If a single elevation is given in Verbatim Locality, put that value in both the minimum and maximum elevation fields.


## Depths

`Locality . Max_Depth NUMBER null Locality . Depth_Units VARCHAR2 (2) null`

`Locality . Min_Depth NUMBER null Locality . Depth_Units VARCHAR2 (2) null`

[`ctlength_units`](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctlength_units)

Depths are a distance below the local surface (such as a body of water or soil surface).  The surface may or may not be at sea level, *e.g.,* a mountain lake.  If depth data are part of the verbatim locality, they should be entered as three fields: Minimum Depth, Maximum Depth, and Depth Units (ft, m).  If the verbatim locality contains a depth range, e.g., 500-600 ft, these values should be entered into the minimum and maximum depth fields, respectively.  If a single depth is given in the verbatim locality, put that value in both the minimum and maximum elevation fields.
 [//]: # Github issue:https://github.com/ArctosDB/documentation-wiki/issues/117

## TRS

"Verbatim" Township, Range, and Section (TRS) information should, like all verbatim locality data, be entered in verbatim locality. Non-verbatim legacy TRS data may be entered in locality remarks. A thorough description of TRS data, along with a tool to translate them to latitude and longitude can be found in [How To Convert Township/Range/Section data to Latitude/Longitude Coordinates Using GeoLocate](http://handbook.arctosdb.org/how_to/Convert_TRS_to_Lat-Long_Using_GeoLocate.html).

## UTM

"Verbatim" Universal Transverse Mercator (UTM) information should, like all verbatim locality data, be entered in verbatim locality. Non-verbatim legacy UTM data may be entered (where? what does it do?. See https://github.com/ArctosDB/arctos/issues/6544.


# Coordinates


The assigning of latitudes and longitudes to verbal
[locality](locality) data is called georeferencing. Latitude describes a
position in degrees north or south of the equator. Longitude describes a
position in degrees east or west of the Greenwich meridian. However,
coordinates alone are of limited use without information on uncertainty
and the coordinate frame of reference (datum).

Protocols for georeferencing natural history collections are described
in the [MaNIS Georeferencing
Guidelines](http://manisnet.org/GeorefGuide.html).  Tools that automate
these protocols include the [Georeferencing
Calculator](http://manisnet.org/gc.html),
[BioGeomancer](http://bg.berkeley.edu/latest/), and
[GeoLocate](http://www.museum.tulane.edu/geolocate/ "GeoLocate at Tulane"). 
GeoLocate is called as a web service by applications within Arctos.

Coordinates are stored with collecting events and with locality, both
optional. Collecting event coordinates are "verbatim" and should reflect
some data associated with specimen events. Locality coordinates are part
of georeferences, and may be standardizations or corrections of, or
additions to verbatim coordinates.

Any locality has zero or one coordinate assertions. "Unaccepted
coordinates" are handled by having multiple specimen events referencing
multiple localities.

Data Entry has (for brevity) one place for coordinate information, and
these data are stored as both verbatim and locality coordinates. Events
and localities may be pre-made and selected when these limitations
prevent accurately representing the data.



## Original Units

`collecting_event . Orig_Lat_long_Units VARCHAR(20) null`

[`ctlat_long_units`](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTLAT_LONG_UNITS)

`DarwinCore2=VerbatimCoordinateSystem`

 for geographic coordinates vary with the source of
the data.  Classically, latitude and longitude have been recorded in
degrees, minute and seconds.  Now, modern GIS applications generally use
degrees only, including decimal fractions for all levels of precision. 
In Arctos, coordinates are stored and displayed in their original
format.  Except for UTMs, coordinates are also translated to, and stored
as, decimal degrees for standardization and mapping.  There is not yet
programming to convert UTMs to decimal degrees. Include as many digits
of precision as are provided in the original data.  Forms in Arctos are
customized according to which format is chosen, and the vocabulary and
formats are defined and described by a [code
table](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTLAT_LONG_UNITS).

In all formats, include as many digits of precision as are provided in
the original data.


## (Geodetic) Datum

`Collecting_Event . Datum VARCHAR(40) null`

[`ctdatum`](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctdatum)

`DarwinCore2=GeodeticDatum`


 The geodetic datum to which the latitude and longitude refer.
A geodetic datum describes the size, shape, origin, and orientation of a
coordinate system for mapping the earth. Latitude and longitude data
referenced to the wrong datum can result in positional errors of
hundreds of meters. Therefore, when providing latitude and longitude
data, it is important to know from which datum those data are derived.
Most GPS units allow you to select the geodetic data from which its
coordinates will be determined (default usually set to WGS84, but this
should be checked in the field). Maps and gazetteers generally provide
this information as well.


## Georeference Source



Recorded as a [Locality Attribute](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctlocality_attribute_type#georeference_source), refers to the source(s) of the coordinates and not
to the source of the error. Coordinates may be original data collected
with the cataloged item, or they may be provided by after-the-fact
georeferencing efforts. In the latter situation, data in Source(s)
should be specific enough to allow anyone in the future to use the same
resources to validate the coordinates, or to georeference the same
locality. These data might be a list of maps, gazetteers or other
resources used to georeference the locality. Examples:

-   USGS 1:24000 Florence Montana Quad
-   Dictionary of Alaska Place Names (Orth, 1967)
-   Geographic Names Canada (NRC website)
-   Geographic Names Information System (USGS website)

In cases where the coordinates are original data, a description of the
original source should be provided. Again, these data should make the
coordinates as verifiable as possible by referring to records associated
with the cataloged item. Examples:

-   collector’s notation
-   preparator’s notation
-   cataloged item label
-   accession file
-   global positioning system (download)
-   global positioning system (transcription)



## Georeference Method

`Locality.GEOREFERENCE_PROTOCOL VARCHAR(40) not null`

[`ctGEOREFERENCE_PROTOCOL`](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctGEOREFERENCE_PROTOCOL "GEOREFERENCE_PROTOCOL")


 is the protocol used to obtain the values for
the coordinates and the measure of precision. Different methods and
tools have been produced, and are sometimes revised, and these
differences can produce different results.  The
[vocabulary](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctgeorefmethod "Georeference Method")
for this field is controlled.


## Maximum Uncertainty Distance

`Lat_Long . Max_Error_Distance NUMBER null`

`DarwinCore2=CoordinateUncertaintyInMeters`


`Lat_Long . Max_Error_Units VARCHAR2(2) null`

[`ctlat_long_error_units`](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctlat_long_error_units "Distance Units")


 is the upper limit of the horizontal
(as opposed to elevational) distance from the reported latitude and
longitude. It describes a circle within which the whole of the described
locality lies. Leave the value empty if the uncertainty is unknown,
cannot be estimated, or is not applicable (because there are no
coordinates). Zero is not a valid value. Maximum Uncertainty is the sum
of GPSAccuracy, Extent, and all other sources of error or imprecision.

This is a simple concept, but there are several sources of error which,
when correctly combined, often demonstrate a value larger than intuition
might suggest. These sources of error are enumerated in the MaNIS
Guidelines, and are combined into estimates of total error by the
Georeferencing Calculator.

In some circumstances the greatest source of error is the behavior of
the collector and/or any intermediary sources of the data. For example,
if a locality names a village, the collector may have obtained cataloged items
from a resident who forages over a large area near the village. The
collector may even have provided coordinates for the village, often from
some standard source, implying specificity equal to the extent of the
village. Estimating error can therefore be subjective, and conservative
interpretation demands large values for Maximum Uncertainty. To avoid
ambiguous or misleading locality descriptions, see [MVZ’s
guidelines](http://mvz.berkeley.edu/Locality_Field_Recording.html).

Note that there is no error inherent to coordinates.
{Dec_Lat=12,Dec_Long=34} is precisely the same point as
{Dec_Lat=12.000000000000000000000000000000,Dec_Long=34.000000000000000000000000000000}.
Make no assumptions of coordinate error or "size" (all coordinates
describe a point) based on anything other than asserted maximum error.

For most usage, including exportation to federated portals, the value
for Maximum Uncertainty is converted from the original units (recorded
here) to the value in meters.



## Remarks

`Lat_Long . Lat_Long_Remarks VARCHAR2(4000) null`

`DarwinCore2=GeoreferenceRemarks`


 about the spatial description determination, explaining
assumptions made in addition or opposition to the those formalized in
the method referred to in [Georeference Method](#georefmethod).



## Primary Spatial Data

All spatially-aware localities have both point-radius and polygon data available. primary_spatial_data indicates wheich is provided; the other is generated. 


## Place Terms

Place Terms is a search-optimized cache of locality-adjacent data, primarily supporting localities which are referenced from filtered_flat. (That is: used, primary, and unencumbered) These data are deeply cached and may be weeks out of date, but still generally serve as the most effective way of locating records by place. (Curatorial data are notoriously inconsistent.) As of this writing, place_terms contains the following data.

| Source | Explanation |
|---|---|
| geography | Term from geography chosen/asserted by the collection. |
| locality | Term from locality chosen/asserted by the collection. |
| locality attribute |  Term from "locality-adjacent" attribute chosen/asserted by the collection. |
| geography metadata | Term from metadata ("search terms") of geography chosen/asserted by the collection. |
| spatial intersection |  Term from spatial data which intersects the coordinates or polygon provided (as Locality) by the collection. |
| GeoLocate |  Term from spatial data which intersects the coordinates returned by the GeoLocate API. |


### More about GeoLocate

[GeoLocate](https://www.geo-locate.org/) coordinates are derived from asserted geography, locality, and event data, arranged and filtered using a relatively complicated algorithm in an attempt to provide data in a way that GeoLocate can best interpret. Wildly incorrect results are almost always related to not following the guidance for specific locality (above), or rarely through incorrect (often outdated) geography choices. Any errors which cannot be atributd to these sources should be reported to the GeoLocate developers. Despite these few generally-obvious errors (which provide a mechanism to locate improvable data), GeoLocate provides the single most consistent method of locating records by place names. GeoLocate data are also used when a collection activates the georeference [bot](https://handbook.arctosdb.org/documentation/bot.html). Note that this is not related to [using GeoLocate to assist in curatorial assertions](https://handbook.arctosdb.org/documentation/geolocate.html).


# Edit Locality Form

Localities used by "verified by…." verificationstatus values may not be
edited. If you don’t understand the giant bright red box, please use a
contact link.

Many things are paired or dependant. Min, max, and units must be given
together for elevation and depth. Coordinates must have datum, source,
and protocol. Error cannot exist without coordinates. Fieldset labels on
the form will change as form values change to help inform you of these
associations.

All coordinates are stored as DD.ddd format. (Verbatim Coordinates are
an attribute of Collecting Events.) The form will make conversions.

The webservice data pane has documentation inline. Read it.

# Maintenance

Duplicate localities are automatically merged, and unused localities are automatically deleted. A Locality Name will prevent both of these actions and should be used in pre-created localities. Please remove Name from any localities which you no longer intend to use.

## How To

Instructions for doing specifc tasks related to Localities in Arctos (please note that "under construction" icons on pages indicate that the documentation may be incomplete or out-of-date):

- [How To Assign a New Locality to a Catalog Record](https://handbook.arctosdb.org/how_to/How-to-Reassign-Specimens-to-Another-Locality.html)
- [How To Change Locality and Collecting Event](https://handbook.arctosdb.org/how_to/How-to-Change-Locality-Single-Specimen.html)
- [How To Convert Township/Range/Section data to Latitude/Longitude Coordinates Using GeoLocate](https://handbook.arctosdb.org/how_to/Convert_TRS_to_Lat-Long_Using_GeoLocate.html)
- [How To Create a Locality](https://handbook.arctosdb.org/how_to/How-to-Create-a-Locality.html)
- [How To Create a New Collecting Event for a Locality](https://handbook.arctosdb.org/how_to/How-to-Create-a-New-Collecting-Event-for-a-Locality.html)
- [How To Create a New Specific Locality](https://handbook.arctosdb.org/how_to/How-to-Create-a-New-Specific-Locality.html)
- [How To Edit a Specific Locality](https://handbook.arctosdb.org/how_to/How-to-Edit-a-Specific-Locality.html)
- [How To Edit Coordinates and Max Error of a Locality](https://handbook.arctosdb.org/how_to/How-to-Edit-Coordinates-and-Max-Error-of-a-Locality.html)
- [How To Edit Coordinates for One Cataloged Item](https://handbook.arctosdb.org/how_to/How-to-Edit-Coordinates-for-One-Specimen.html)
- [How To Merge Duplicate Localities](https://handbook.arctosdb.org/how_to/How-to-Merge-Duplicate-Localities.html)
- [How To Understand Locality Media](https://handbook.arctosdb.org/how_to/How-to-understand-locality-media.html)
- [How To Understand the Arctos Locality Model](https://handbook.arctosdb.org/how_to/How-to-understand-the-Arctos-Locality-Model.html)
  
## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/locality.markdown" target="_blank">here</a>.
