# v.qcount

**Category**: vector

## Description

Indices for quadrat counts of vector point lists.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_qcount(input,layer="-1",output=None,nquadrats,radius,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, optional`**
   - Name for output quadrat centers map (number of points is written as category)
   - Used as: output, vector, name

4. **`nquadrats : int, required`**
   - Number of quadrats

5. **`radius : float, required`**
   - Quadrat radius

6. **`flags : str, optional`**
   - Allowed values: g
   - g
   - Print results in shell script style

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.qcount computes six different quadrat count statistics that provide
a measure of how much an user defined point pattern departs from a
complete spatial random point pattern.

Points are distributed following a complete spatial randomness (CSR)
pattern if events are equally likely to occur anywhere within an area.
There are two types departure from a CSR: regularity and clustering.
Figure 1 gives an example of a complete random, regular and a clustered
pattern.

Figure 1: Realization of two-dimensional Poisson processes of 50 points
on the unit square exhibiting (a) complete spatial randomness, (b)
regularity, and (c) clustering.

Various indices and statistics measure departure from CSR. The v.qcount function implements six different quadrat count indices
that are described in Cressie (1991; p. 590-591)[1] and in Ripley
(1981; p. 102-106)[2] and summarized in Table 1.

Table 1: Indices for Quadrat Count Data. Adapted from Cressie [1],
this table shows the statistics computed for the quadrats in Figure 2.

These indices are computed as follows: v.qcount chooses nquadrads circular quadrats of radius radius such that they are completely
within the bounds of the current region and no two quadrats overlap. The
number of points falling within each quadrat are counted and indices are
calculated to estimate the departure of point locations from complete
spatial randomness. This is illustrated in Figure 2.

Figure 2: Randomly placed quadrats (n = 100) with 584 sample points.

The number of points is written as category to the output map (and
not to an attribute table).

---

## See Also

Related tools:
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)
- [`v.neighbors`](https://grass.osgeo.org/grass-devel/manuals/v.neighbors.html)
- [`v.perturb`](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html)

---

## Authors

James Darrell McCauley when he was at: Agricultural
Engineering Purdue
University
Modified for GRASS 5.0 by Eric G. Miller (2000-10-28) Modified for GRASS 5.7 by R. Blazek (2004-10-14)

---

## Resources

- [Official v.qcount manual](https://grass.osgeo.org/grass-devel/manuals/v.qcount.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.qcount.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
