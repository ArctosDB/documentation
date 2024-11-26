---
title: How To Bulkload Catalog Records
layout: default_toc
author: Michelle Koo
date: 2024-11-25
---
Relevant Documentation:
[Bulkloader Documentation](https://handbook.arctosdb.org/documentation/bulkloader.html) | 
[Catalog Record/Data Entry Documentation](https://handbook.arctosdb.org/documentation/catalog.html)

# How to Bulkload Catalog Records

What you need to know: Bulkloading records into Arctos is an efficient way to organize and create multiple records in batches. The key to successful bulkloading  is properly preparing your CSV file (see *Bulkload Builder* below). Once your CSV file is ready, then there are two database steps. First step is loading your prepared file into the Staging Table. This is a shared resource currently, so if a user has data in the table it is unavailable until it has been pushed to the second step (see Bulkloading Table). This step is meant to be a temporary holding stage for primary data validation. If there are no errors, then the Second step is to push the data to  the Staging Table. 



# Bulkload Builder - Pre-uploading stage

#### Navigation: [Tools Directory > Enter Data > Bulkload Builder](https://arctos.database.museum/Bulkloader/bulkloaderBuilder.cfm)

If you do not have a Bulkload Catalog Record Data sheet, begin with the [Bulkload Builder](https://arctos.database.museum/Bulkloader/bulkloaderBuilder.cfm).

The first section includes groups of fields available to use. Select which ones you want to save time on selecting individual fields in the larger table below.

In the next section, you will see the fields that were selected as part of the groups selected above. 

If there are fields that will never be used by your collection and therefore do not need to be in your file. **Unselect** them.  

Now click on “Get CSV” located above the small table and below the large table. Your file will automatically download.

## Helpful Hints:

* Any header can be deleted, added, or rearranged in the excel sheet manually. 

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Caution.jpg) **Caution**

Be sure edited cells do not have an invisible lead or end, otherwise Arctos will reject it. 

* The bulkload template has a large number of fields for parts, attributes, collector, etc. These are there only if you need them; these fields can be blank or omitted from the bulkload template. 

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) **Pro Tips**

* The bulkloader only allows loading four part attributes per part. If you need to add more attributes, consider bulkloading the records without parts and then bulkloading parts with the Part Bulkload Tool. 

* **IT IS VERY HELPFUL TO HAVE THE SINGLE DATA ENTRY PAGE OPEN WHILE ENTERING DATA INTO THE BULKLOAD DATA SHEET.** 
Much of the bulkloader works off of the single data sheet and many things are “text sensitive”, meaning Arctos will not accept your file if something does not already exist within Arctos (ie; agents, parts, attributes, etc) OR if something is spelled incorrectly. 

* Agents can be entered as “unknown”, but blanks are also an acceptable value. 

* If no Catalog Number has been previously assigned you can leave the CAT_NUM blank if you want Arctos to automatically assign the next available catalog number.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Caution.jpg) **Caution** 

When trying to fill a gap in the available catalog numbers, it is wise to view what is available and enter them manually. Only allow Arctos to assign numbers if you have no gaps in your assigned catalog numbers and are using an integer catalog number format.

## Excel Helpful Hints:

* Excel generally defaults dates to the (mm-dd-yyyy) format, whereas Arctos likes them to be in (yyyy-mm-dd) format. Excel will also re-format the date back to how it likes if you close and re-open a CSV file. To change the date format at any point, do the following:
 * In the Home tab of excel in the “Number” section there will be a drop menu. With the cell(s) you need selected, click the drop menu and scroll to the bottom and select Text. This tells excel to stop assuming it knows what to do with the date and keep it the way you want it.
 * Another way to do this, which is especially helpful with a re-opened file, is to again, select the cell(s) you want and click the drop down menu in the “Number” section of the Home tab.
* Select “more number formats” at the very bottom.
* If “date” is not already selected, do so and it will bring up all the different formats for dates.
* In the “Locale (location)” drop down menu, select “English (South Africa)”
* South Africa is your new best friend because they have the date format that you need. Select “yyyy-mm-dd” format and click ok.
* Your highlighted cell(s) should automatically change to Arctos date format. **Woot!**

For information about required data and individual fields, see [How To Enter Data for a Single Record: Data Entry Details](https://handbook.arctosdb.org/how_to/How-to-Enter-Data-for-a-Single-Record.html#data-entry-form-details)

# Uploading Your Data

#### Navigation: [Tools Directory > Enter Data > Bulkload Catalog Records](https://arctos.database.museum/Bulkloader/BulkloadSpecimens.cfm)

## Step 1: Staging Table    

On the bulkloading page, read through the steps and etiquette, and scroll to the bottom of the page. You will either see a table with user information indicating that the staging table is in use or you will see the message "Upload a comma-delimited text file (csv)" with the Browse and Upload buttons.
* The Staging Table is a shared resource that can only be accessed by one user at a time. If the Staging Table is in use, then the Browse and Upload buttons will **not** be available.
* Instead the name and contact information of the user will be shown and will remain there until it is free and available. If you forget to delete your data from the staging table, you may end up getting some emails from other institutions asking when you will be done.

Please read the *Staging Table etiquette* on the upload form. 


### Ready to Bulkload    

* Browse to your file and click “Upload this file”. 
* You will be brought to a page that says “There are (#) records in the staging table. They have not been checked or processed yet”. (#- the number of records you are trying to upload).
* From here you will choose from the following choices; Check and load these records, just load these records, or cleanup.
  * **“Check and load these records”** - By-passes the need for the records to go into the bulkloader where they would normally be looked over by an administrator.
  * **“Just load these records”** - Moves the records to the “personal” bulkloader where your administrator can approve them like any other single data entry.
  * **“Cleanup”** – If you have last minute data that needs to be added or changed. Once you do that, go back and choose one of the two other choices. For practical purposes, choose “Just load these records”.
* You will be brought to a new page that says, “Your records have been checked and are now in the table bulkloader and flagged as loaded=’BULKOADED RECORD’. A data administrator can un-flag and load them.” After that it will say in blue “please delete from the staging table”, click that then click “yep, delete away” and you are all set.
* Your data is now in the Bulkloading Table awaiting approval in Step 2.

 ***IMPORTANT: DELETE YOUR DATA FROM THE STAGING TABLE***
 
## Step 2: Bulkloading Table
 
 Once you have successfully pushed your data to the Bulkloading Table, proceed to [Browse and Edit page](https://arctos.database.museum/Bulkloader/browseBulk.cfm) where you can filter for your latest uploaded records. The status column will tell you if further edits are required before loading, or if blank, you can set to ```autoload``` for record creation. If there are errors, you can correct records in this Bulkloading Table prior to autoloading. 
 
 Note: Permission to access this table is different than Step 1.
 
 
<!--
## How to Bulkload Data Tutorial Video

[![YouTube: How to Bulkload Data](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/How_to_Bulkload_Data_thumb.jpg)](https://youtu.be/2ehyZqS_C3Q)
-->

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/How-to-Bulkload-Catalog-Records.markdown" target="_blank">here</a>.
