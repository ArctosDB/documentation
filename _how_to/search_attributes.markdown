---
title: How To Search Attributes
layout: default_toc
---

# Search Attributes

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)


This is a stash for information which was in /documentation/attributes - it may not be relevant, and should be updated.



## Searching with Attributes

You may search for only [Attribute Name](#name) (leave Value and Units
blank) to return specimens that match your other criteria and possess
data for the specified Attribute. Exercising this option unwisely (For
example, searching for all specimens with Attribute ‘sex’ and no other
qualifiers) can time-out your request.

You can search for Attributes by only value or by only units. For
example:

-   Attribute: Numeric Age
-   Units = "years" (Returns all specimens with a numeric age recorded
    in years.)


-   Attribute: Numeric Age
-   Value = "5" (Returns all specimens with a numeric age of 6 years, 6
    days, etc.

You may set the search operator for Attributes to:

-   `equals`
-   `contains`
-   `greater than`
-   `less than`

`Equals` will find only exact matches. `Contains` will find substring
matches. For example, sex `equals` ‘male’ will find only *male*
specimens; sex `contains` ‘male’ will find both *male* and *fe**male***.

## Searching by Attribute Type

In addition to the above, the interactive Specimen Results Widget will
accept any attribute, with spaces and dashes replaced by underscore, as
a variable. For example, "age class" becomes "age_class."

All attributes (and most other variables) will accept underbar (\_) to
mean "require the field; match any value." For example, "age_class=\_"
will return specimens for which the attribute "age class" exists.

String attributes – those consisting of uncontrolled text and those
consisting of code-table controlled vocabularies – will accept two
prefixes: = (meaning "is exactly") and ! (meaning "is not"). Unprefixed
attributes are case-insensitive substring matches, and so "male" will
match "male" and "fe**male**."

Numeric attributes – those with code-table controlled units – will
accept prefixes = (exactly), ! (is not), &lt; (less than), &gt; (greater
than), and appropriate units as suffix. Arctos will guess at unit
suffix, so an exact code-table match is not usually necessary. Units of
both data and criteria are converted (to meters, days, and grams), and
so exact matches may be difficult to obtain. Therefore, numeric
attributes will also accept a range of values in conjunction with units
(format {low value}{dash}{high_value} {units}).

The following examples are illustrative.

  |SearchTerm              |Result|
  |------------------------|-------|
  |age_class=adult         |adult, subadult, ….|
  |age_class==adult        |adult|
  |age_class=!adult        |juvenile, subadult, ….|
  |numeric_age=3           |3 years, 3 seconds, 3 days, …..|
  |numeric_age=!3          |1 years, 5 years, 1 hour, 5 days, …|
  |numeric_ag=3 years      |{value converted to} 1095.726 days|
  |numeric_age=3-5 years   |{value converted to days} BETWEEN 1095.726 and 1826.21 days|

Arctos can convert the following units to meters:

-   in
-   M
-   METERS
-   METER
-   FT
-   FEET
-   FOOT
-   KM
-   KILOMETER
-   KILOMETERS
-   MM
-   MILLIMETER
-   MILLIMETERS
-   CM
-   CENTIMETER
-   CENTIMETERS
-   MI
-   MILE
-   MILES
-   YD
-   YARD
-   YARDS
-   FM
-   FATHOM
-   FATHOMS

Arctos can convert the following units to grams:

-   G
-   GRAMS
-   GRAM
-   KG
-   KILOGRAM
-   KILOGRAMS
-   LB
-   POUND
-   POUNDS
-   OZ
-   OUNCE
-   OUNCES

Arctos can convert the following units to days:

-   D
-   DAY
-   DAYS
-   H
-   HOUR
-   HOURS
-   M
-   MONTH
-   MONTHS
-   WEEK
-   WEEKS
-   YR
-   Y
-   YEAR
-   YEARS

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/search_attributes.markdown" target="_blank">here</a>.
