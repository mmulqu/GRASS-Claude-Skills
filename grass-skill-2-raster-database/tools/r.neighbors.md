# r.neighbors

**Category**: raster

## Description

Makes each cell category value a function of the category values assigned to the cells around it, and stores new cell values in an output raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_neighbors(input,selection=None,output,size=3,method="average",weighting_function="none",weighting_factor=None,weight=None,quantile=None,title=None,nprocs=0,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`selection : str | np.ndarray, optional`**
   - Name of an input raster map to select the cells which should be processed
   - Used as: input, raster, name

3. **`output : str | list[str], required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`size : int, optional`**
   - Neighborhood size
   - Default: 3

5. **`method : str | list[str], optional`**
   - Neighborhood operation
   - Allowed values: average, median, mode, minimum, maximum, range, stddev, sum, count, variance, diversity, interspersion, quart1, quart3, perc90, quantile
   - Default: average

6. **`weighting_function : str, optional`**
   - Weighting function
   - Allowed values: none, gaussian, exponential, file
   - none: No weighting
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html#__tabbed_2_3) for all details)*

7. **`weighting_factor : float, optional`**
   - Factor used in the selected weighting function (ignored for none and file)

8. **`weight : str | io.StringIO, optional`**
   - Text file containing weights
   - Used as: input, file, name

9. **`quantile : float | list[float] | str, optional`**
   - Quantile to calculate for method=quantile
   - Allowed values: 0.0-1.0

10. **`title : str, optional`**
   - Title for output raster map
   - Used as: phrase

11. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

12. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

13. **`flags : str, optional`**
   - Allowed values: a, c
   - a
   - Do not align output with the input
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html#__tabbed_2_3) for all details)*

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.neighbors looks at each cell in a raster input map, and examines
the values assigned to the cells in some user-defined "neighborhood"
around it. It outputs a new raster map layer in which each cell is
assigned a value that is some (user-specified) function of the values in
that cell's neighborhood. For example, each cell in the output layer
might be assigned a value equal to the average of the values appearing
in its 3 x 3 cell "neighborhood" in the input layer. Note that the
centre cell is also included in the calculation.

Figure: Illustration for an 3x3 average neighborhood

The user must specify the names of the raster map layers to be used for input and output , the method used to analyze neighborhood
values (i.e., the neighborhood function or operation to be performed),
and the size of the neighborhood.

The user can optionally specify a selection map, to compute new
values only where the raster cells of the selection map are not NULL. In
case of a NULL cells, the values from the input map are copied into the
output map. This may useful to smooth only parts of an elevation map
(pits, peaks, ...).

Example how to use a selection map with method=average: input map:

selection map, NULL values are marked as *:

The output map:

Without using the selection map, the output map would look like this:

It is also possible to weigh cells within the neighborhood. This can be
either done with a custom weights matrix or by specifying a weighting
function.

In order to use a custom weights matrix, file needs to be specified as
a weighting_function and a path to a text file containing the
weights needs to be given in the weight option.

Alternatively, gaussian and exponential weighting functions can be
selected as weighting function.

For the gaussian weighting function, the user specifies the sigma
value (σ) for the gauss filter in the weighting_factor option. The
sigma value represents the standard deviation of the gaussian
distribution, where the weighting formula for the gaussian filter is
defined as follows:

exp(-(x*x+y*y)/(2*σ^2))/(2*π*σ^2)

Lower values for sigma result in a steeper curve, so that more weight is
put on cells close to the center of the moving window with a steeper
decrease in weights with distance from the center.

For the exponential weighting function, the user specifies a factor
for an exponential kernel in the weighting_factor . Negative factors
result in negative exponential decrease in weights from the center cell.
The weighting formula for the exponential kernel is defined as follows:

exp(factor*sqrt(x*x+y*y))

Stronger negative values for the factor result in a steeper curve, so
that more weight is put on cells close to the center of the moving
window with a steeper decrease in weights with distance from the center.

Optionally, the user can also run r.neighbors specify the TITLE to be assigned to the raster map layer output , select to
not align the resolution of the output with that of the input (the -a option). These options are described further below.

Neighborhood Operation Methods: The neighborhood operators
determine what new value a center cell in a neighborhood will have after
examining values inside its neighboring cells. Each cell in a raster map
layer becomes the center cell of a neighborhood as the neighborhood
window moves from cell to cell throughout the map layer. r.neighbors can perform the following operations:

average The average value within the neighborhood. In the following example, the
result would be: (7*4 + 6 + 5 + 4*3)/9 = 5.6667 The result is rounded to the nearest integer (in this case 6).

median The value found half-way through a list of the neighborhood's values,
when these are ranged in numerical order.

mode The most frequently occurring value in the neighborhood.

minimum The minimum value within the neighborhood.

maximum The maximum value within the neighborhood.

range The range value within the neighborhood.

stddev The statistical standard deviation of values within the neighborhood
(rounded to the nearest integer).

sum The sum of values within the neighborhood.

count The count of filled (not NULL) cells.

variance The statistical variance of values within the neighborhood (rounded to
the nearest integer).

diversity The number of different values within the neighborhood. In the above
example, the diversity is 4.

interspersion The percentage of cells containing values which differ from the values
assigned to the center cell in the neighborhood, plus 1. In the above
example, the interspersion is: 5/8 * 100 + 1 = 63.5 The result is rounded to the nearest integer (in this case 64).

quart1, quart3 The result will be the first or the third quartile (equal of 25th and
75th percentiles).

perc90 The result will be the 90th percentile of neighborhood.

quantile Any quantile as specified by "quantile" input parameter.

Neighborhood Size: The neighborhood size specifies which cells
surrounding any given cell fall into the neighborhood for that cell. The size must be an odd integer and represent the length of one of
moving window edges in cells. For example, a size value of 3 will result
in

Matrix weights: A custom matrix can be used if none of the
neighborhood operation methods are desirable by using the weight .
This option must be used in conjunction with the size option to
specify the matrix size and file needs to be specified as weighting_function . The weights desired are to be entered into a
text file. For example, to calculate the focal mean with a matrix size of 3,

The contents of the weight.txt file:

This corresponds to the following 3x3 matrix:

To calculate an annulus shaped neighborhood the contents of weight.txt
file may be e.g. for size=5:

The way that weights are used depends upon the specific aggregate
( method ) being used. However, most of the aggregates have the
property that multiplying all of the weights by the same factor won't
change the final result (an exception is method=count ). Also, most
(if not all) of them have the properties that an integer weight of N is
equivalent to N occurrences of the cell value, and having all weights
equal to one produces the same result as when weights are not used. When
weights are used, the calculation for method=average is:

In the case where all weights are zero, this will end up with both the
numerator and denominator to zero, which produces a NULL result.

-a If specified, r.neighbors will not align the output raster map
layer with that of the input raster map layer. The r.neighbors program works in the current geographic region. It is recommended, but
not required, that the resolution of the geographic region be the same
as that of the raster map layer. By default, if unspecified, r.neighbors will align these geographic region settings.

-c This flag will use a circular neighborhood for the moving analysis
window, centered on the current cell.

The exact masks for the first few neighborhood sizes are as follows:

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)

---

## Authors

Original version: Michael Shapiro, U.S.Army Construction Engineering
Research Laboratory Updates for GRASS GIS 7 by Glynn Clements and others

---

## Resources

- [Official r.neighbors manual](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
