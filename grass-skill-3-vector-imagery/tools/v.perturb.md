# v.perturb

**Category**: vector

## Description

Random location perturbations of vector points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_perturb(input,layer="-1",output,distribution="uniform",parameters,minimum=0.0,seed=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`distribution : str, optional`**
   - Distribution of perturbation
   - Allowed values: uniform, normal
   - Default: uniform

5. **`parameters : float | list[float] | str, required`**
   - Parameter(s) of distribution
   - If the distribution is uniform, only one parameter, the maximum, is needed. For a normal distribution, two parameters, the mean and standard deviation, are required.

6. **`minimum : float, optional`**
   - Minimum deviation in map units
   - Default: 0.0

7. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

8. **`flags : str, optional`**
   - Allowed values: s, b
   - s
   - Generate random seed (result is non-deterministic)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.perturb reads a vector map of points and writes the same points but perturbs the eastings and northings by adding either a uniform or
normal delta value. Perturbation means that a variating spatial
deviation is added to the coordinates.

---

## See Also

Related tools:
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Authors

James Darrell McCauley when he was at: Agricultural
Engineering Purdue
University
Random number generators originally written in FORTRAN by Wes Peterson
and translated to C using f2c .

---

## Resources

- [Official v.perturb manual](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
