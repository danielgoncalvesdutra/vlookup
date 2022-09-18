# vlookup-hlookup

When do you need to use VLOOKUP? 

Two common reasons to use VLOOKUP are:

    -Populating data in a spreadsheet 

    -Merging data from one spreadsheet with data in another

VLOOKUP syntax in excel and spreadsheets:

    VLOOKUP(search_key, range, index, [is_sorted])

        search_key

            -The value to search for. 

            -For example, 42, "Cats", or I24.

        range 

            -The range to consider for the search. 

            -The first column in the range is searched to locate data matching the value specified by search_key.

        index

            -The column index of the value to be returned, where the first column in range is numbered 1. 

            -If index is not between 1 and the number of columns in range, #VALUE! is returned.

        is_sorted 

            -Indicates whether the column to be searched (the first column of the specified range) is sorted. TRUE by default.

            -It’s recommended to set is_sorted to FALSE. If set to FALSE, an exact match is returned. If there are multiple matching values, the content of the cell corresponding to the first value found is returned, and #N/A is returned if no such value is found.

            -If is_sorted is TRUE or omitted, the nearest match (less than or equal to the search key) is returned. If all values in the search column are greater than the search key, #N/A is returned.

What if you get #N/A?

    -As you have just read, #N/A indicates that a matching value can't be returned as a result of the VLOOKUP. The error doesn’t mean that anything is actually wrong with the data, but people might have questions if they see the error in a report. You can use the IFNA function to replace the #N/A error with something more descriptive, like “Does not exist.”

    -IFNA syntax:

        IFNA(value, value_if_na)

        value
            -This is a required value.

            -The function checks if the cell value matches the value; such as #N/A.

        value_if_na
            -This is a required value.

            -The function returns this value if the cell value matches the value in the first argument; it returns this value when the cell value is #N/A.

Helpful VLOOKUP reminders
    -TRUE means an approximate match, FALSE means an exact match on the search key. If the data used for the search key is sorted, TRUE can be used.

    -You want the column that matches the search key in a VLOOKUP formula to be on the left side of the data. VLOOKUP only looks at data to the right after a match is found. In other words, the index for VLOOKUP indicates columns to the right only. This may require you to move columns around before you use VLOOKUP.

    -After you have populated data with the VLOOKUP formula, you may copy and paste the data as values only to remove the formulas so you can manipulate the data again. 