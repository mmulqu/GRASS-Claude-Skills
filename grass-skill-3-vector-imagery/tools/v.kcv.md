# v.kcv

**Category**: vector

## Description

Randomly partition points into test/train sets.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_kcv(map,layer="1",npartitions,column="part",verbose=None,quiet=None,superquiet=None)
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

3. **`npartitions : int, required`**
   - Number of partitions
   - Must be > 1

4. **`column : str, optional`**
   - Name for new column to which partition number is written
   - Used as: input, dbcolumn, name
   - Default: part

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

v.kcv randomly divides a points lists into k sets of test/train data
(for npartitions -fold c ross v alidation). Test partitions are
mutually exclusive. That is, a point will appear in only one test
partition and k-1 training partitions. The module generates a random
point using the selected random number generator and then finds the
closest point to it. This site is removed from the candidate list
(meaning that it will not be selected for any other test set) and saved
in the first test partition file. This is repeated until enough points
have been selected for the test partition. The number of points chosen
for test partitions depends upon the number of sites available and the
number of partitions chosen (this number is made as consistent as
possible while ensuring that all sites will be chosen for testing). This
process of filling up a test partition is done k times.

---

## See Also

Related tools:
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

James Darrell McCauley, when he was at: Agricultural
Engineering Purdue
University
27 Jan 1994: fixed RAND_MAX for Solaris 2.3 13 Sep 2000: released under GPL Updated to 5.7 Radim Blazek 10 / 2004 OGR support by Martin Landa (2009) Speed-up by Jan Vandrol and Jan Ruzicka (2013)

---

## Resources

- [Official v.kcv manual](https://grass.osgeo.org/grass-devel/manuals/v.kcv.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.kcv.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
