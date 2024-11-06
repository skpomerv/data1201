# Week 11:
## OpenRefine II Part 1: Worksheet
To start, create a new lab11 folder. You will **not need to place any files in it to start**.
Instead, we will insert our screenshots, as well as create another `questions.md` file.

Remember to go to the openrefine installation, and run ./refine to start it up!

You can run openrefine in the background using `./refine &` if you would like!

###	Filtering and Sorting with OpenRefine
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



## OpenRefine Part 2: Weekly Assignment

