# t.sample

**Category**: temporal

## Description

Samples the input space time dataset(s) with a sample space time dataset and print the result to stdout.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_sample(inputs,sample,intype="strds",samtype="strds",method="during,overlap,contain,equal",separator="pipe",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`inputs : str | list[str], required`**
   - Name of the input space time datasets
   - Used as: input, stds, name

2. **`sample : str, required`**
   - Name of the sample space time dataset
   - Used as: input, stds, name

3. **`intype : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

4. **`Default: strds`**

5. **`samtype : str, optional`**
   - Type of the sample space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

6. **`Default: strds`**

7. **`method : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: start, during, overlap, contain, equal, follows, precedes

8. **`separator : str, optional`**
   - Do not use "," as this char is reserved to list several map ids in a sample granule
   - Field separator between output columns, default is tabular " | "
   - Used as: input, separator, character

9. **`flags : str, optional`**
   - Allowed values: c, s
   - c
   - Print the column names as first row
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.sample.html#__tabbed_2_3) for all details)*

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.sample.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The purpose of t.sample is to compute and to show spatio-temporal
relations between space time datasets of different type. Several input
space time datasets are sampled by a sample space time dataset using
temporal topological relations. The types of the input space time
datasets and the type of the sample space time dataset can be different.

This module is useful to analyze temporal relationships between space
time datasets using temporal topology. The flag -s enables a
spatio-temporal topology, so that only spatio-temporal related map
layers of space time datasets are considered in the analysis.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.sample manual](https://grass.osgeo.org/grass-devel/manuals/t.sample.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.sample.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
