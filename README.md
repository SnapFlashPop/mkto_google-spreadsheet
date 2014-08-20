mkto_google-spreadsheet
=======================

![Marketo Lists in your Google Spreadsheet]
(http://f.cl.ly/items/3N0K442b433F0L1B163O/lists_in_spreadsheet.png)

Import Marketo lists to Google Spreadsheet - and maybe one day, keep them up-to-date - 
using the [REST API](http://developers.marketo.com/documentation/rest/) and 
[Google Apps Script](https://developers.google.com/apps-script/).

**NOTE: DO NOT POST YOUR API CREDENTIALS PUBLICALLY!**  
**You alone are responsible for the security of your API credentials.**

This project is a work-in-progress. It is only minimally functional.
Please salt heavily, and see the Caveats / Todo section at the bottom of this README.

Author information
------------------
Kyle Halstvedt  
[Elixiter, Inc.](http://www.elixiter.com)  
kyle@elixiter.com

Setup (*IMPORTANT*)
-------------------
1. From within a new Google Spreadsheet file,
   open Tools -> Script editor...
2. File -> New -> Project, and select
   "Spreadsheet" under "Create a script".
3. Paste the code from
   [mkto_spreadsheet-lists.js]
   (https://raw.githubusercontent.com/khalstvedt/mkto_google-spreadsheet/master/mkto_spreadsheet-lists.js)
   into the editor.
4. Configure the script by replacing the
   "REPLACE_ME" strings in the configuration
   section at the top with URL's/keys that
   are specific to your Marketo instance.
   If you have trouble with this, see
   [Marketo's documentation](http://developers.marketo.com/documentation/rest/),
   specifically the sections on [authentication]
   (http://developers.marketo.com/documentation/rest/authentication/)
   and [the custom service]
   (http://developers.marketo.com/documentation/rest/custom-service/).

Usage
-----
1. From a Spreadsheet file with the script
   included, click the custom "Marketo Import"
   menu item, and click "Initialize sidebar...". If there
   is no menu item titled "Marketo Import", please make sure
   you have followed all of the steps in Setup (and that
   the script is present in the script editor for the
   current document).
2. A right-hand sidebar should appear with the names
   and IDs of the lists fetched from Marketo.
3. Each list has an "Insert" button. Click it to insert
   the members of the list.

Caveats / Todo
--------------
1. The REST API is paginated, and this script does not even bother to walk through
   the pages; it currently only retrieves the first page from a list
   (first 100 results). This feature is upcoming.
2. The script does not attempt to "update" or "synchronize" the lists,
   it currently only appends to the bottom of your sheet. This feature is
   planned.
3. Any user with enough priveleges to run the script
   is able to *read* the script, which contains
   your REST API credentials (ID and secret key) in-the-clear.  
   **DO NOT POST YOUR API CREDENTIALS PUBLICALLY!**
