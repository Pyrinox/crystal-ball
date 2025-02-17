# Crystal-Ball Documentation

If you have hundreds of csvs you need to quickly digest and understand, you can use crystal-ball to help with the onboarding and data exploration phase of your project. You will be able to immediately dive into an expansive data set without getting lost.

## Crystal-Ball Features:
- find specific columns and tables you may be interested in, but may have otherwise not known where to look.
- walk through connections between different csvs, 
- compare and establish foreign key and primary key relationships by using simple boxplots
- dynamically create a master table of useful information while simultaneously recording your step-by-step process for future reference.

## Methods

###  cb.contains(keywords, all_colnames) -> list

**_Purpose:_**
- Determine whether a keyword (substring) exists in a given list of column names (strings). 
- Note: This search is case sensitive!

**_Parameters:_**
- **keywords** (list of strings)
  - A key word
- **all_colnames** (list of strings)
  - List of column names of a table, or for many tables. 
  - If no argument is provided, this function will use the column names generated when the run method was called.
  
**_Returns:_**
- **list** (a list of bools): 
  - For each index corresponding to a keyword, True if substring exists in list of strings, otherwise False.

**_Examples:_**
```python
colnames = ['id', 'name', 'title']
cb.contains(['name'], colnames) # returns [True]
cb.contains(['Name'], colnames) # returns [False]
cb.contains(['name', 'Name'], colnames) # returns [True, False]
```

###  cb.featureSearch(keywords, all_colnames) -> list

**_Purpose:_**
- Find features (column names) that contain the substrings specified in keywords. 
- Note: This search is case sensitive!

**_Parameters:_**
- **keywords** (list of strings)
    - List of key words that the user is interested in
- **colnames** (list of strings)
    - List of column names of a table, or for many tables. 
    - If no argument is provided, this function will use the column names generated when the run method was called.

**_Returns:_**
- **list** (list of features): 
    - List will contain all features (column names) that contains one/all substrings found in keywords.
    - List will be sorted in alphabetical order.

**_Examples:_**
```python
colnames = ['id', 'name', 'nameType', 'subSpeciesName', 'title']
cb.featureSearch(['name'], colnames) # returns ['name', 'nameType']
cb.featureSearch(['Name'], colnames) # returns ['subSpeciesName']
cb.featureSearch(['name', 'Name'], colnames) # returns ['name', 'nameType', 'subSpeciesName']
```
