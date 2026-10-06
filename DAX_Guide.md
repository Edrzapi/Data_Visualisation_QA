# DAX guide (Lab 11 and beyond)

DAX is the formula language in Power BI. You use it to add **calculated columns** and **measures**.

## Column or measure?

| | Calculated column | Measure |
|---|---|---|
| Works out | one value **per row** | one answer for **whatever the visual shows**, after filters |
| Stored | in the table | nowhere: worked out when shown |
| Use for | labels, groups, slicers | totals, averages, percentages, year on year |
| Lab 11 example | `FullName`, `Reseller Group` | `Web Sales Amount`, `Web Sales Amount SPLY` |

Rule of thumb: if you would put it on a slicer or an axis, make a column. If it is a number you would add up, make a measure.

**How:** select the table in the Data pane, then **New column** or **New measure** on the ribbon. Type the formula and press Enter.

## Functions in the labs

| Function | Does |
|---|---|
| `SUM ( column )` | adds up a column |
| `DIVIDE ( a, b )` | a / b, but blank instead of an error when b is 0 |
| `IF`, `ISBLANK` | conditions, and checking for empty values |
| `SWITCH ( TRUE (), test, result, ... )` | several conditions: the first true test wins, so order matters |
| `RELATED ( column )` | in a column: fetch a value from the related table |
| `SUMX ( RELATEDTABLE ( table ), column )` | in a column: add up the matching rows in a related table |
| `CALCULATE ( measure, filter )` | the measure with the filters changed |
| `TOTALYTD`, `SAMEPERIODLASTYEAR`, `PARALLELPERIOD` | time intelligence: needs a table marked as a date table |

Every Lab 11 formula is in `lab11/Code.txt`. Copy from there, not from the PDF.

## When DAX goes wrong

| You see | Usually |
|---|---|
| `The syntax for ',' is incorrect` | a missing bracket, or curly quotes pasted from a PDF: retype the quotes |
| "...cannot be found..." | a wrong column, measure or table name: start typing and pick from the list |
| The same number on every row | it is a column that should be a measure, or there is no relationship |
| Time intelligence is blank | the date table is not marked: Table tools -> Mark as date table |
| A total looks wrong | check the relationships in Model view |

**Tip:** type `[` to pick a column or measure, or `'` to pick a table, from a list. It removes most typos.
