# r.random.surface

**Category**: raster

## Description

Generates random surface(s) with spatial dependence.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_random_surface(output,distance=0.0,exponent=1.0,flat=0.0,seed=None,high=255,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | list[str], required`**
   - Name for output raster map(s)
   - Used as: output, raster

2. **`distance : float, optional`**
   - Maximum distance of spatial correlation (value >= 0.0)
   - Default: 0.0

3. **`exponent : float, optional`**
   - Distance decay exponent (value > 0.0)
   - Default: 1.0

4. **`flat : float, optional`**
   - Distance filter remains flat before beginning exponent
   - Default: 0.0

5. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

6. **`high : int, optional`**
   - Maximum cell value of distribution
   - Default: 255

7. **`flags : str, optional`**
   - Allowed values: u
   - u
   - Uniformly distributed cell values

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.random.surface.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.random.surface generates a spatially dependent random surface. The
random surface is composed of values representing the deviation from the
mean of the initial random values driving the algorithm. The initial
random values are independent Gaussian random deviates with a mean of 0
and standard deviation of 1. The initial values are spread over each
output map using filter(s) of diameter distance. The influence of each
random value on nearby cells is determined by a distance decay function
based on exponent. If multiple filters are passed over the output maps,
each filter is given a weight based on the weight inputs. The resulting
random surface can have any mean and variance, but the theoretical
mean of an infinitely large map is 0.0 and a variance of 1.0.
Description of the algorithm is in the NOTES section.

The random surface generated are composed of floating point numbers, and
saved in the category description files of the output map(s). Cell
values are uniformly or normally distributed between 1 and high values
inclusive (determined by whether the -u flag is used). The category
names indicate the average floating point value and the range of
floating point values that each cell value represents.

r.random.surface's original goal is to generate random fields for
spatial error modeling. A procedure to use r.random.surface in spatial
error modeling is given in the NOTES section.

output Random surface(s). The cell values are a random distribution between the
low and high values inclusive. The category values of the output map(s)
are in the form #.# #.# to #.# where each #.# is a floating point
number. The first number is the average of the random values the cell
value represents. The other two numbers are the range of random values
for that cell value. The average mean value of generated output map(s) is 0. The average variance of map(s) generated is 1. The random
values represent the standard deviation from the mean of that random
surface.

distance Distance determines the spatial dependence of the output map(s). The
distance value indicates the minimum distance at which two map cells
have no relationship to each other. A distance value of 0.0 indicates
that there is no spatial dependence (i.e., adjacent cell values have no
relationship to each other). As the distance value increases, adjacent
cell values will have values closer to each other. But the range and
distribution of cell values over the output map(s) will remain the same.
Visually, the clumps of lower and higher values gets larger as distance
increases. If multiple values are given, each output map will have
multiple filters, one for each set of distance, exponent, and weight
values.

exponent Exponent determines the distance decay exponent for a particular filter.
The exponent value(s) have the property of determining the texture of
the random surface. Texture will decrease as the exponent value(s) get
closer to 1.0. Normally, exponent will be 1.0 or less. If there are no
exponent values given, each filter will be given an exponent value of
1.0. If there is at least one exponent value given, there must be one
exponent value for each distance value.

flat Flat determines the distance at which the filter.

weight Weight determines the relative importance of each filter. For example,
if there were two filters driving the algorithm and weight=1.0, 2.0 was
given in the command line: The second filter would be twice as important
as the first filter. If no weight values are given, each filter will be
just as important as the other filters defining the random field. If
weight values exist, there must be a weight value for each filter of the
random field.

high Specifies the high end of the range of cell values in the output map(s).
Specifying a very large high value will minimize the errors caused by
the random surface's discretization. The word errors is in quotes
because errors in discretization are often going to cancel each other
out and the spatial statistics are far more sensitive to the initial
independent random deviates than any potential discretization errors.

seed Specifies the random seed(s), one for each map, that r.random.surface will use to generate the initial set of random values that the resulting
map is based on. If the random seed is not given, r.random.surface will get a seed from the process ID number.

---

## See Also

Related tools:
- [`r.random`](https://grass.osgeo.org/grass-devel/manuals/r.random.html)
- [`r.random.cells`](https://grass.osgeo.org/grass-devel/manuals/r.random.cells.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.surf.random`](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)

---

## Authors

Charles Ehlschlaeger, Michael Goodchild, and Chih-chang Lin; National
Center for Geographic Information and Analysis, University of
California, Santa Barbara

---

## Resources

- [Official r.random.surface manual](https://grass.osgeo.org/grass-devel/manuals/r.random.surface.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.random.surface.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
