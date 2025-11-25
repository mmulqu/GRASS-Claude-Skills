# v.kernel

**Category**: vector

## Description

Generates a raster density map from vector points map. Density is computed using a moving kernel. Optionally generates a vector density map on a vector network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_kernel(input,net=None,output=None,net_output=None,radius,dsize=0.,segmax=100.,distmax=100.,multiplier=1.,node="none",kernel="gaussian",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map with training points
   - Used as: input, vector, name

2. **`net : str, optional`**
   - Name of input network vector map
   - Used as: input, vector, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`net_output : str, optional`**
   - Name for output vector density map
   - Outputs vector map if network map is given
   - Used as: output, vector, name

5. **`radius : float, required`**
   - Kernel radius in map units

6. **`dsize : float, optional`**
   - Discretization error in map units
   - Default: 0.

7. **`segmax : float, optional`**
   - Maximum length of segment on network
   - Default: 100.

8. **`distmax : float, optional`**
   - Maximum distance from point to network
   - Default: 100.

9. **`multiplier : float, optional`**
   - Multiply the density result by this number
   - Default: 1.

10. **`node : str, optional`**
   - Node method
   - Allowed values: none, split
   - none: No method applied at nodes with more than 2 arcs
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.kernel.html#__tabbed_2_3) for all details)*

11. **`kernel : str, optional`**
   - Kernel function
   - Allowed values: uniform, triangular, epanechnikov, quartic, triweight, gaussian, cosine
   - Default: gaussian

12. **`flags : str, optional`**
   - Allowed values: o, q, n, m
   - o
   - Try to calculate an optimal radius with given 'radius' taken as maximum (experimental)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.kernel.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.kernel.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.kernel generates a raster density map from vector points data using
a moving kernel. Available kernel density
functions are uniform, triangular, epanechnikov, quartic, triweight, gaussian,
cosine . The default function is gaussian .

The module can also generate a vector density map on a vector network.
Conventional kernel functions produce biased estimates by overestimating
the densities around network nodes, whereas the equal split method of
Okabe et al. (2009) produces unbiased density estimates. The equal split
method uses the kernel function selected with the kernel option and
can be enabled with node=split .

---

## See Also

Related tools:
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Stefano Menegon, ITC-irst , Trento, Italy Radim Blazek (additional kernel density functions and network part)

---

## Resources

- [Official v.kernel manual](https://grass.osgeo.org/grass-devel/manuals/v.kernel.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.kernel.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
