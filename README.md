# acs-table-hierarchy

Machine readable table hierarchy for US Census Bureau's American Community Survey.

The American Community Survey from the US Census Bureau contains a wealth of information organized in what is essentially a gigantic spreadsheet with thousands of columns and tens of thousands of rows. The Census Bureau releases the important metdata about this data in several different files with different data formats (XLS, CSV, TSV, etc.) and to get a complete set of metadata a consumer is required to know how to merge all those pieces in just the right way.

One of the pieces that is the trickiest to pull apart is the column hierarchy. Each column obviously has a name, but in some cases that column "belongs" to a "parent column". For example, in this screenshot from the Census FactFinder tool, you can see that there are several "subjects" (columns) whose name are simply age ranges.

![](http://factfinder.census.gov/help/en/image/ebx_1928454782.gif)

To get the full context about what that column is about, you also need to know that the column belongs to "SEX AND AGE" column, which belongs to the "Foreign-born population" column.

This hierarchy information is only exposed as formatting information on Microsoft Excel "Table Shell" files that Census releases alongside each year of the survey. The code in this repo is designed to download the Table Shell files and extract the formatting information to generate a machine readable (JSON) representation of the column hierarchy that can be used in other applications.
