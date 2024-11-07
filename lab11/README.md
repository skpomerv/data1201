# Week 11:
## OpenRefine II Part 1: Worksheet
To start, create a new lab11 folder. You will **not need to place any files in it to start**.
Instead, we will insert our screenshots, as well as create another `questions.md` file.

Remember to go to the openrefine installation, and run ./refine to start it up!

You can run openrefine in the background using `./refine &` if you would like!

###	Filtering with OpenRefine
Sometimes you want to view and work only with a subset of data or apply an operation only to a subset. You can do this by applying various filters to your data.

One way to filter down our data is to use the `include` or `exclude` buttons on the entries in a text facet. If you still have your text facet for `scientificName`, you can use it. 
If you’ve closed that facet, recreate it by selecting `Facet > Text facet` on the `scientificName` column.

1. In the text facet, hover over one of the names, e.g. *Baiomys taylori*. Notice that when you hover over it, there are buttons to the right for `edit` and `include`.
2. Whilst hovering over *Baiomys taylori*, move to the right and click the `include` option. This will include this species, as signified by the name of the species changing from blue to orange, and new options of edit and exclude will be presented. Note that in the top of the page, “33 matching rows” is now displayed instead of “790 rows”.
3. You can include other species in your current filter - e.g. click on *Chaetodipus baileyi* in the same way to include it in the filter.
4. Alternatively, you can click the name of the species to include it in the filter instead of clicking the include/exclude buttons. This will include the selected species and exclude all others options in a single step, which can be useful.
5. Take a screenshot of your page with only entries of *Baiomys taylori* and *Chaetodipus baileyi* visible. **Name the screenshot "filter1.png" or "filter1.jpg."**

Another way to filter data is to create a text filter on a column. Close all facets you may have created previously and reinstate the text facet on the `scientificName` column.
1. Click the down arrow next to `scientificName > Text filter`. A `scientificName` filter will appear on the left margin below the text facet.
2. Type in `bai` into the text box and press return.
3. Near the top of the screen, change `Show:` to 50. This way, you will see all the matching rows in a single page.
4. Take a screenshot of the page to show the 35 rows that matched. **Name the screenshot "filter2.png" or "filter2.jpg."**

### Sorting with OpenRefine

We can also sort! Sorting data is a useful practice for detecting outliers in data - potential errors and blanks will sort to the top or the bottom of your data.

You can sort the data in a column by using the drop-down menu available in that column. There you can sort by text, numbers, dates or booleans (TRUE or FALSE values). You can also specify what order to put Blanks and Errors in the sorted results.

If this is your first time sorting this table, then the drop-down menu for the selected column shows Sort.... Select what you would like to sort by (such as numbers). Additional options will then appear for you to fine-tune your sorting.

If you try to re-sort a column that you have already used, the drop-down menu changes slightly, to > Sort without the ..., to remind you that you have already used this column. It will give you additional options:
- `Sort > Sort...` - This option enables you to modify your original sort.
- `Sort > Reverse` - This option allows you to reverse the order of the sort.
- `Sort > Remove sort` - This option allows you to undo your sort.

You can sort by multiple columns by performing sort on additional columns. The sort will depend on the order in which you select columns to sort. To restart the sorting process with a particular column, check the `sort by this column alone` box in the Sort pop-up menu.


1. In **questions.md**, create a header for the following question called **question 1**, then below the header, answer it.

You might like to look for trends in your data by month of collection across years.

Part 1. How do you sort your data by month? 

Part 2. How would you do this differently if you were instead trying to see all of your entries in chronological order?

### Reconciliation of Values
Reconciliation services allow you to lookup terms from your data in OpenRefine against external services, and use values from the external services in your data. The [OpenRefine manual provides more information about the reconciliation feature.](https://openrefine.org/docs/manual/reconciling)

Reconciliation services can be more sophisticated and often quicker than using the method described above to retrieve data from a URL. However, to use the Reconciliation function in OpenRefine requires the external resource to support the necessary service for OpenRefine to work with, which means unless the service you wish to use supports such a service you cannot use the Reconciliation approach.

There are a few services where you can find an OpenRefine Reconciliation option available. For example Wikidata has a reconciliation service at [https://wikidata.reconci.link/](https://wikidata.reconci.link/).

In this lab, we can find the taxonomic matches to the names in this dataset using the [Encyclopedia of Life](https://eol.org/) reconciliation service.

1. In the `scientificName` column use the dropdown menu to choose `Reconcile > Start Reconciling`

2. If it's the first time using a service, we will need to add it by clicking 'Add Standard Service...' Enter the following url below:
	* `https://eol.org/api/reconciliation`

![The Add Reconciliation Menu](/lab11/images/add-reconciliation.png "An example of adding the eol reconciliation api.")

3. You should now see a heading in the list on the left hand side of the Reconciliation dialogue called "Encyclopedia of Life" Click on it to seect that service.

4. In the middle box in the reconciliation dialogue you may get asked what type of ‘entity’ you want to reconcile to - that is, what type of thing are you looking for. The list will vary depending on what reconciliation service you are using. In this case, the only option is "Taxon".

5. In the box on the righthand side of the reconciliation dialogue you can choose if other columns are used to help the reconciliation service make a match - however it is sometimes hard to tell what use (if any) the reconciliation service makes of these additional columns.

6. At the bottom of the reconciliation dialogue there is the option to "Auto-match candidates with high confidence". This can be a time saver, but in this case you are going to uncheck it, so you can see the results before a match is made.

7. Finally, click "Start Reconciling"
	* This operation can take a bit of time if you have a lot of stuff to look up.
	* Once done, we should have two Facets that are created automatically.
		* scientificName: Judgement
		* scientificName: best candidate’s score

8. These are two of several specific reconciliation facets and actions that you can get from the ‘Reconcile’ menu (from the column drop down menu).
Close the ‘scientificName: best candidate’s score’ facet, but leave the ‘scientificName: Judgement’ facet open.

9. If you look at the scientificName column, you should see some cells have found one or more matches - the potential matches are shown in a list in each cell. Next to each potential match there is a ‘tick’ and a ‘double tick’. To accept a reconciliation match you can use the ‘tick’ options in cells. The ‘tick’ accepts the match for the single cell, the ‘double tick’ accepts the match for all identical cells.

    1. Create a text facet on the scientificName column
    2. Choose Ammospermophilus harrisii
    3. In the scientificName column you should be able to see the various potential matches. Clicking on a match will take you to the EOL page for that entity

	4. **Take a screenshot of the page as "match.png" or "match.jpg"**

	5. Click a ‘double tick’ in one of the scientificName column cells for the option "Ammospermophilus harrisii (Audubon & Bachman 1854)". This will accept this as a match for all cells with this value - you should see the other options disappear

There are two things that reconciliation can do for you. Firstly it gets a standard form of the name or label for the entity. Secondly it gets an ID for the entity - in this case a page and numeric id for the scientific name in EOL. This is hidden in the default view, but can be extracted:

	1. In the scientificName column use the dropdown menu to choose `Reconcile > Add entity identifiers column...`
	2. Give the column the name "EOL-ID"
	3. **Take a screenshot of the page called "eol-id.png" or "eol-id.jpg"**

1. In **questions.md**, create a header for the following question called **question 2**, then below the header, answer it.

What is the major benefit of reconciliation? What did reconciliation *do*?

**At this point, you have completed the worksheet! Save questions.md. Add all files in the lab11 directory you created. Finally, commit the changes and push them to your data1201 repository.**
	
## OpenRefine Part 2: Weekly Assignment


### Looking up Data from a URL
OpenRefine can retrieve data from URLs. This can be used in various ways, including looking up additional information from a remote service, based on information in your OpenRefine data. As an example, you can look up the scientific names in a dataset against the taxonomy of the Global Biodiversity Information Facility (GBIF), and retrieve additional information such as higher taxonomy and identifiers.

Typically this is a two step process, firstly a step to retrieve data from a remote service, and secondly to extract the relevant information from the data you have retrieved.

1. To retrieve data from an external source, use the drop down menu at any column heading and select `Edit column > Add column by fetching URLs...`

This will prompt you for a GREL expression to create a URL. This URL will use existing values in your data to build a query. When the query runs OpenRefine will request each URL (for each line) and retrieve whatever data is returned (this may often be structured data, but could be HTML). The data retrieved will be stored in a cell in the new column that has been added to the project. You can then use OpenRefine transformations to extract relevant information from the data that has been retrieved. Two specific OpenRefine functions used for this are:
	* `parseHTML()` - This works on HTML *and* XML
	* `parseJson()` - This primarily works on JSON returns

For now, let's use the [GBIF API](https://www.gbif.org/developer/summary). Note that API providers may impose rate limits or have other requirements for using their data, so it’s important to check the site’s documentation. To reduce the impact on the service, we will use a value of `500` in the `Throttle Delay` setting to specify the number of milliseconds between requests.

2. The syntax for requesting species information from GBIF is `http://api.gbif.org/v1/species/match?name={name}` where {name} is replaced with the scientific name in the dataset. This is retrieved by looking through the GBIF documentation.
	* Using the dropdown menu of `scientificName`, select `Edit column > Add column by fetching URLs...`
	* In the `New Column` field, enter "gbif\_JSON"
	* In the expression box type the GREL `"http://api.gbif.org/v1/species/match?name="+escape(value,'url')`
	* At this point, your screen should be similar to this:
![The Data from URL](/lab11/images/data-from-url.png "An example of adding a url for data.")
	* Click "OK"

3. You should see a message at the top on the OpenRefine screen indicating it is fetching some data, with progress showing the percentage of the proportion of rows of data successfully being fetched. Wait for this to complete. After, you should have a new column containing a long text string in a format called ‘JSON’ (this stands for JavaScript Object Notation, although very rarely spelled out in full). 

4. **Take a screenshot of the JSON column, and save it as "url_json.png" or "url_json.jpg"**

5. OpenRefine has a function for extracting data from JSON (sometimes referred to as ‘parsing’ the JSON). 
The parseJson() function is explained in more detail [here](https://docs.openrefine.org/manual/grelfunctions/#format-based-functions-json-html-xml).

    * In the new column you’ve just added use the dropdown menu to access `Edit column > Add column based on this column...`
    * Add the new column name: "gbif\_family"
	* In the Expression box type the GREL value.parseJson().get("family")
	* You should see a preview of what will be extracted on the right.
	* **Take a screenshot of the page, and call it "parse_json.png" or "parse_json.jpg"**

The reason for using Add column based on this column is that this allows you to retain the full JSON and extract further data from it if you need to. If you only wanted the taxonomic family and did not need any other information from the JSON you could use Edit cells > Transform... with the same GREL expression.

6. Hit "OK"

### Exporting Data Cleaning Steps
As you conduct your data cleaning and preliminary analysis, OpenRefine saves every change you make to the dataset. These changes are saved in a format known as JSON (JavaScript Object Notation). You can export this JSON script and apply it to other data files. If you had 20 files to clean, and they all had the same type of errors (e.g. species name misspellings, leading white spaces), and all files had the same column names, you could save the JSON script, open a new file to clean in OpenRefine, paste in the script and run it. This gives you a quick way to clean all of your related data.

1. In the Undo / Redo section, click Extract..., and select the steps that you want to apply to other datasets by clicking the check boxes.
2. Copy the code from the right hand panel and paste it into a text editor (you can use Nano, Vim, or gedit).
3. Finally, **save that code in lab 11 as "cleanup_script.txt"**
4. Make a new openrefine instance by clicking the "Open..." button on the top-right.
5. Create a new project using the `Portal\_rodents\_19772002\_simplified.csv` file from the last lab. Name it a new name.
6. Click the `Undo / Redo tab > Apply` and paste in the contents of txt file with the JSON code from step 2.
7. Click `Perform operations`.  The dataset should now be the same as your other cleaned dataset!

For convenience, we used the same dataset, but in real life, we can instead use that process to clean related sets of data.

### Exporting Cleaned Data
You're all familiar with my love for .csv files, and OpenRefine delivers on the promise you'll be able to spit out a beautifully shiny and clean .csv!

Inside of either of your cleaned projects, click "Export" on the top right, and select the .csv file type. 
**Save a version of your cleaned CSV called "cleaned.csv". Make sure there are some changes from the lab reflected in the new CSV!**

### Exporting Project Files
If we need to share out OpenRefine project with someone else, we can also export the entire project!
This is helpful, for instance, if you wanted to send your raw data and cleaning steps to a collaborator, or share this information as a supplement to a publication.

1. Click the Export button in the top right and select OpenRefine project archive to file.
2. A tar.gz file will download to your default Download directory. The tar.gz extension tells you that this is a compressed file, which means that this file contains multiple files.
3. If you open the compressed file (if on Windows, you will need a tool like 7-Zip), you should see:
	* A history folder which contains several zip files. Each of these files itself contains a change.txt file.
		* These change.txt files are the records of each individual transformation that you did to your data.
	* A data.zip file. When expanded, this zip file includes a file called data.txt which is a copy of your raw data.
    * You may also see other files.

**Save this tar.gz in the lab11 folder 	as "backup.tar.gz"**

You can also import into OpenRefine by clicking `Open...` on the top right, and clicking `Import Project` on the left side menu Click `Choose File` and select the tar.gz file you created.
This will include all the raw data and steps you took in the project!

**At this point, you have completed the post-lab assignment! Add all files in the lab11 directory you created. Finally, commit the changes and push them to your data1201 repository.**
	
