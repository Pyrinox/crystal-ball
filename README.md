# Crystal-Ball Documentation

This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.


## Methods
###  cb.contains(keywords, all_colnames) -> list
*Purpose:*
- Determine whether a keyword (substring) exists in a given list of column names (strings). 
- Note: This search is case sensitive!

*Parameters:*
- keywords: list of strings
  - A key word
- all_colnames: list of strings
  - List of column names of a table, or for many tables. 
  - If no argument is provided, this function will use the column names generated when the run method was called.
