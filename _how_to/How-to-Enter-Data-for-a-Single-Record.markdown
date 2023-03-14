---
title: How To Enter Data for a Single Record
author: Teresa J. Mayfield-Meyer
date: 2023-03-14
layout: default_toc
---

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)

# How To Enter Data for a Single Record 

## Navigation 

[Manage -> Data Entry -> Data Entry](https://arctos.database.museum/enter_data.cfm)

## Select a Data Entry Form 

### Pick a Profile 

Profiles are customized data entry forms that may carry seed data. You - or any other user - may use any profile to begin data entry with the data and arrangement in the profile.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Caution.jpg) **Caution**

Data values saved in the profile will have a distinct style and should be carefully checked before saving a record.

To set up a data-bearing profile, you may proceed with one of the options below, then

* Arrange your screen however you wish.
* Enter data that you want the profile to carry, clear out anything that you do not want in the profile. (It is not necessary for the seed data to pass any checks; partial values, types without values, etc., are expected.)
* Click save profile and provide a (unique) name when prompted.

### Begin with Previous Records 

You can start with the last record you entered or if you have sufficient access, with any previously entered record.

### Begin with a Blank Slate 

* Select the collection you need under “Begin with a blank slate”.
* This will start with your last data entry customization.

After choosing one of these options, you will be directed to the appropriate data entry form.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Caution.jpg) **Caution**

The background of your new data entry screen should be **green**. If it is not, Arctos will not let you save your data.

## Customization

See [How To Customize the Data Entry Form]()

## Form Details

The following provides some specifics by data entry section.

### Catalog Record Data
* Accession is is the Acquisition number that is given to a set of specimens, e.g., 01.2014 and is **REQUIRED** and can be selcted using the "pick" button. The accession **does not** need to be associated with the same collection as the item being entered.
* Catalog Number can be left blank if you wish Arctos to assign the next available number (only for collections using integer catalog numbers).
* Catalog Item Type can be left blank if you wish to use the default type selected in collection metadata (See [How To Manage a Collection](https://handbook.arctosdb.org/how_to/How-to-Manage-a-Collection-in-Arctos.html#default-cataloged-item-type)
* GUID Prefix will be completed based upon the collection selectd above or what has been added to a customized data entry form.
* Entered By should have your Arctos username already filled in.
* Status will always be “waiting approval.”

### Identification 

Use this block when you are entering a single identification with a single Identifying Agent. If you want to enter more than one identification for a single catalog record or a single identification with multiple Identifying Agents, use ["Extras Identification"](#"Extras"_Identification).

* Scientific Name is the identification to be applied to the cataloged item. Type in all or part of the cataloged item’s identification and use the Tab key to select a taxon name, or use the "build" button to create a complex identification.
* Identifying Agent is the Arctos Agent that determined the identification. Type in all or part of the Agent’s name and use the Tab key to select an Agent.
* Nature of ID is selected from a [code table](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctnature_of_id).
* ID Date is the date the Agent assigned the identification. If this is not known, leave it blank.
* ID Remark can be used to add information about the identification, including a verbatim determiner if the Identifying Agent is not found in Arctos Agents.

### "Extras" Identification

This section allows you to add up to 3 identifications to a catalog record at once and to include up to 6 Identifying Agents for each Identification. The fields are the same as those discussed in ["Extras Identification"](#Identification).




**Agents**
* “Collector” should be the agent’s name. Fill in the name, hit Tab and you will see a popup; you may have to select the collector if there’s more than one choice.
* **Neat Tip:** Click “Copy2All” next to the field you entered the collector’s name into and Arctos will automatically assign that name to all the required fields on the current data sheet.

**Other IDs**
* The only time you need to enter anything in this section is when you have preserved embryos taken from a specimen.
* If that is the case the PARENT’S information goes here.

**Identification**
* “Scientific Name” allows you to type in all or part of the specimen’s scientific name. Then press the Tab button and a small window will pop up with a list of all scientific names relating to what you typed in.
* This helps to avoid spelling errors.
* “Nature” is a drop down menu. Most often you will choose “field” if the specimen was caught in the field.
* “Date” here is referring to the date the specimen was caught. Also known as ‘date of death’.

**Attributes**
* “Attributes” is a section where you enter the specimen’s sex, measurements and weight
* “Det.Date” is the date the specimen was prepared, ‘prep date’.
* “Determiner” is the same as the collector’s name.
* “Attribute” is where you will enter any endoparasites and/or ectoparasites found or not found with the specimen.
* **Note:** You will want to select endos and ectos then under “Values” selecting yes or no to show if they were detected or not.
* “Date” is the same as the “Det.Date” or ‘prep date’ since that is when it was discovered that the specimen did or did not have any parasites.

**Random Junk**
* Type in all remarks made on the data sheet here.

**Specimen/Event**
* “Event Determiner” will be the same as the collector.
* “Detr. Date” is the current date.
* “Specimen/Event Type” will always be “accepted place of collection”.
* “Coll. Src.” Is a drop down menu. Select “wild caught” unless indicated otherwise.
* “Verification Status” is another drop down menu where “unverified” will already be selected.

**Collecting Event**
* “Verbatim Locality” is the specific locality but even more specific. Just add the state and country it was caught to the end of the specific locality.
* “Verbatim Date” is the date of death.
* “Begin” is the date of death, “End” is the prep date. These two can be the same if it was prepped in the field.

**Locality**
* “Higher Geog” is the county the specimen was collected from.
* “Spec Locality” if not given, is usually the verbatim locality with town and county.

**Coordinates (event and locality)**
* “Original lat/long Units” is a drop down menu where you will select “decimal degrees”.
* “Max Error” is usually guestimated to be around 10m unless indicated otherwise.
* “Datum” will be “World Geodetic System 1984” down near the bottom.
* “Georeference Source” is a section where you can start typing in “global positioning” and a dropdown menu will automatically pop up. From that select “Global Positioning System (Transcription)”
* “Georeference Protocol” is a dropdown menu where you will select “not recorded”.
* “Dec Lat” is the latitude value in decimal degrees found on the data sheet.
* “Dec Long” is the longitude value in decimal degrees found on the data sheet.
* **Note:** If the verbatim locality is vague, you may need to go digging for lat / long coordinates and district.
* To do this, try your best to find the location given in google maps. It should give you a lat/long if you click on the map.
* To find district, use this website: http://www.michigan.gov/dnr/1,1607,7-153-10371_14793-30743--,00.html
* Type in the lat/long in this section and click [geolocate] in blue, located at the top of this section right next to where you choose your Original lat/long units.
* This will give you a map of the general location of your lat/long units.
* You can move the green dot marker anywhere you want for a more precise location and can also edit your max error here.
* To edit max error, click on the green dot marker and a box will pop up where you can choose “edit uncertainty”

**Parts**

* List all the parts collected from the specimen.
* Again, you can press the Tab key and a small window will pop up with a list to select from. Choose the most appropriate one, ie; h,k,lu,spl (frozen) instead of just h,k,lu,spl
* “Condition” correlates to the circled number on the data sheet for “Tissue Condition”.
* “Disposition” is another drop down menu from which you will always select “in collection” unless indicated otherwise.
* “#” is the number of samples kept of the part. This will almost always be a 1 unless of course indicated otherwise.


# Extras

Occasionally data which has no place in the default screen will be available. This may be handled in two ways.

### Option One: Flags

A flag may be added to the record during entry ...

<img width="320" alt="Screen Shot 2021-07-15 at 6 50 22 AM" src="https://user-images.githubusercontent.com/5720791/125799282-cb6916d8-ee48-4840-8ab3-c3754e1e93ad.png">

... and then, after the record has been loaded, it may be located by searching flags ...

<img width="581" alt="Screen Shot 2021-07-15 at 6 50 59 AM" src="https://user-images.githubusercontent.com/5720791/125799492-1871e7a9-42c0-4d67-a51b-443b198111e5.png">


... and resolving any issues. This approach requires reliable procedures.


### Option Two: Extras

The most common "extras" are available from the bottom of the data entry screen....


These options allow, for example, adding parts with multiple attributes. Simply select the appropriate type ...

<img width="599" alt="Screen Shot 2021-07-15 at 6 48 03 AM" src="https://user-images.githubusercontent.com/5720791/125799814-ee689b91-361f-4da7-8014-4fdff05bc7fd.png">

... provide whatever's requested by the form, and save.

<img width="981" alt="Screen Shot 2021-07-15 at 6 56 37 AM" src="https://user-images.githubusercontent.com/5720791/125800281-d5c768cc-b8c8-4a7f-a974-28ab8b813a75.png">

These data are written to the Component Loader system, which generates a weekly report.


**All finished!**
* Now you will want to click on “Save This As A New Record” in the bottom left hand side of the page in the blue box.
* Your data sheet will then be put into the bulkloader and await approval.
* To approve the records for upload to Arctos see [How to approve records entered with Data Entry form](https://github.com/ArctosDB/documentation-wiki/wiki/How-to-approve-records-entered-with-Data-Entry-form)

## Stuff from old document
* If there is a collector or preparator number, use the “CustomID Type” drop down menu. Scroll all the way to the bottom and select “collector number” or “preparator number.”
* Custom ID” is the specimen’s collector or preparator number, if it has one.

### Data Entry Tutorial Video ###
[![Data Entry Example](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Arctos_Data_Entry_Example.jpg)](https://youtu.be/IOJP1M_Lu_E)

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/How-to-Enter-Data-for-a-Single-Record.markdown" target="_blank">here</a>.
