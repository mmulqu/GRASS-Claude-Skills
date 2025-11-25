# v.db.select

**Category**: vector

## Description

Prints vector map attributes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_select(map,layer="1",columns=None,where=None,group=None,format="plain",separator=None,vertical_separator=None,null_value=None,file=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`columns : str | list[str], optional`**
   - Name of attribute column(s)
   - Used as: input, dbcolumn, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`group : str, optional`**
   - GROUP BY conditions of SQL statement without 'group by' keyword

6. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json, vertical
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html#__tabbed_2_3) for all details)*

7. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`vertical_separator : str, optional`**
   - Output vertical record separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

9. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string

10. **`file : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

11. **`flags : str, optional`**
   - Allowed values: r, c, e, f
   - r
   - Print minimal region extent of selected vector features instead of attributes
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.db.select prints attributes of a vector map from one or several user
selected attribute table columns.

Four different formats can be used depending on the circumstances using
the format option: plain text, CSV, JSON, and vertical plain text.

The plain text is the default output which is most suitable for reading
by humans, e.g., when working in the command line or obtaining specific
values from the attribute table using the v.db.select GUI dialog.

The individual fields (attribute values) are separated by a pipe ( | )
which can be customized using the separator option. The records
(rows) are separated by newlines.

Example with a pipe as a separator (the default):

When escaping is enabled, the following characters in the fields are
escaped: backslash ( \\ ), carriage return ( \r ), line feed ( \n ),
tabulator ( \t ), form feed ( \f ), and backslash ( \b ).

No quoting or escaping is performed by default, so if these characters
are in the output, they look just like the separators. This is usually
not a problem for humans looking at the output to get a general idea
about query result or attribute table content.

Consequently, this format is not recommended for computers, e.g., for
reading attribute data in Python scripts. It works for further parsing
in limited cases when the values don't contain separators or when the
separators are set to one of the escaped characters.

CSV (comma-separated values) has many variations. This module by default
produces CSV with comma ( , ) as the field separator (delimiter). All
text fields (based on the type) are quoted with double quotes. Double
quotes in fields are represented as two double quotes. Newline
characters in the fields are present as-is in the output. Header is
included by default containing column names.

All full CSV parsers such as the ones in LibreOffice or Python are able
to parse this format when configured to the above specification.

Example with default settings:

If desired, the separator can be customized and escaping can be enabled
with the same characters being escaped as for the plain text. Notably,
newlines and tabs are escaped, double quotes are not, and the separator
is not escaped either (unless it is a tab). However, the format is
guaranteed only for the commonly used separators such as comma,
semicolon, pipe, and tab.

Note that using multi-character separator is allowed, but not
recommended as it is not generally supported by CSV readers.

CSV is the recommended format for further use in another analytical
applications, especially for use with spreadsheet applications. For
scripting, it is advantageous when tabular data is needed (rather than
key-value pairs).

JSON (JavaScript Object Notation) format is produced according to the
specification so it is readily readable by JSON parsers. The standard
JSON escapes are performed (backslash, carriage return, line feed,
tabulator, form feed, backslash, and double quote) for string values.
Numbers in the database such as integers and doubles are represented as
numbers, while texts (TEXT, VARCHAR, etc.) and dates in the database are
represented as strings in JSON. NULL values in database are represented
as JSON null . Indentation and newlines in the output are minimal and
not guaranteed.

Records which are the result of the query are stored under key records as an array (list) of objects (collections of key-value pairs). The keys
for attributes are lowercase or uppercase depending on how the columns
were defined in the database.

The JSON also contains information about columns stored under key info . Column names and types are under key columns . Each column has
SQL data type under sql_type in all caps. A boolean is_number specifies whether the value is a number, i.e., integer or floating point
number. The is_number value is added for convenience and it is
recommended to rely on the types derived from the JSON representation or
the SQL types. The definition of is_number may change in the future.

Example with added indentation:

JSON is the recommended format for reading the data in Python and for
any uses and environments where convenient access to individual values
is desired and JSON parser is available.

In the vertical plain text format, each value is on a single line and is
preceded by the name of the attribute (column) which is separated by
separator. The individual records can be separated by the vertical
separator ( vertical_separator option).

Example with (horizontal) separator = and vertical separator newline :

Newline is automatically added after a vertical separator unless it is a
newline which allows for separating the records, e.g., by multiple
dashes. The escaping ( -e ) need to should be enabled in case the
output is meant for reading by a computer rather than just as a data
overview for humans. Escaping will ensure that values with newlines will
be contained to a single line. This format is for special uses in
scripting, for example, in combination with columns option set to
one column only and escaping ( -e ) and no column names flags
( -c ). It is also advantageous when you need implement the parsing
yourself.

---

## See Also

Related tools:
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Minimal region extent added by Martin Landa, FBK-irst (formerly
ITC-irst), Trento, Italy Group option added by Luca Delucchi, Fondazione Edmund Mach, Trento,
Italy Huidae Cho (JSON output, escaping and features-only flags) Vaclav Petras (true CSV output, format option and documentation)

---

## Resources

- [Official v.db.select manual](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
