If you have hundreds of csvs you need to quickly digest and understand,
you can use crystal-ball to help with the onboarding and data
exploration phase of your project. You will be able to immediately dive
into an expansive data set without getting lost.

CrystalBall Features
====================

-   find specific columns and tables you may be interested in, but may
    have otherwise not known where to look.

-   walk through connections between different csvs,

-   compare and establish foreign key and primary key relationships by
    using simple boxplots

-   dynamically create a master table of useful information while
    simultaneously recording your step-by-step process for future
    reference.

Installation and Usage
======================

pip install crystal-ball&lt;/programlisting&gt;
You can start using CrystalBall right away by importing it and
initializing it with a relative directory containing the CSVs.

    import crystalball as cb

    ball = cb.run("insert relative directory here")

Methods
=======

Note that all methods that involve searching via keynames are case
sensitive.

cb.contains(keywords: list, all\_colnames: list=None) → list
------------------------------------------------------------

Check if keywords exist in all\_colnames.

cb.featureSearch(keywords: list, all\_colnames: list=None) → list
-----------------------------------------------------------------

Find the columns that contain the keywords.

cb.tableSearch(keywords: list, csvname\_to\_colnames\_list=None, mode: str=*UNION*) → list
------------------------------------------------------------------------------------------

Find the tables that contain the keywords.

cb.openTable(rel\_dir: str, indices: list=\[0\]) → DataFrame
------------------------------------------------------------

Open the csv that is referenced by the given relative directory.

cb.subTable(supertable: DataFrame, chosen\_index: list, chosen\_columns: list) → DataFrame
------------------------------------------------------------------------------------------

Create a subtable from a supertable.

cb.mergeTables(tables: list) → DataFrame
----------------------------------------

Sequentially merge a list of tables that all share a common index.

cb.analyzeRelationships(to\_analyze: list, visualize: bool=True) → DataFrame
----------------------------------------------------------------------------

Analyze basic stats of one or more different Series.

compareRelationship(to\_analyze1: Series, to\_analyze2: Series, visualize: bool=False) → DataFrame
--------------------------------------------------------------------------------------------------

Compare and contrast the difference between two Series.

cb.export(df\_to\_export: DataFrame, write\_to: str, export\_type: str=*CSV*) → None
------------------------------------------------------------------------------------

Exports contents of dataframe to relative location specified by
write\_to arg.
