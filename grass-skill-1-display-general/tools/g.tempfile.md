# g.tempfile

**Category**: general

## Description

Creates a temporary file and prints it's file name.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_tempfile(pid,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`pid : int, required`**
   - Process id to use when naming the tempfile

2. **`flags : str, optional`**
   - Allowed values: d
   - d
   - Dry run - don't create a file, just prints it's file name

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

g.tempfile is designed for shell scripts that need to use large
temporary files. GRASS provides a mechanism for temporary files that
does not depend on /tmp/ . GRASS temporary files are created in the
data base with the assumption that there will be enough space under the
data base for large files. GRASS periodically removes temporary files
that have been left behind by programs that failed to remove them before
terminating.

g.tempfile creates an unique file and prints the name. The user is
required to provide a process-id which will be used as part of the name
of the file. Most Unix shells provide a way to get the process id of the
current shell. For /bin/sh and /bin/csh this is $$ . It is
recommended that $$ be specified as the process-id for g.tempfile .

---

## Resources

- [Official g.tempfile manual](https://grass.osgeo.org/grass-devel/manuals/g.tempfile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.tempfile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
