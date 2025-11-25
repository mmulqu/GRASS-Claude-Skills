# r.fill.stats

**Category**: raster

## Description

Rapidly fills 'no data' cells (NULLs) of a raster map with interpolated values (IDW).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_fill_stats(input,output,uncertainty=None,distance=3,mode="wmean",minimum=None,maximum=None,power=2.0,cells=8,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Raster map with data gaps to fill
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of result output map
   - Used as: output, raster, name

3. **`uncertainty : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name of uncertainty output map
   - Used as: output, raster, name

4. **`distance : float, required`**
   - Distance threshold (default: in cells) for interpolation
   - Used as: value
   - Default: 3

5. **`mode : str, required`**
   - Statistic for interpolated cell values
   - Used as: name
   - Allowed values: wmean, mean, median, mode

6. **`minimum : float, optional`**
   - Minimum input data value to include in interpolation
   - Used as: value

7. **`maximum : float, optional`**
   - Maximum input data value to include in interpolation
   - Used as: value

8. **`power : float, required`**
   - Power coefficient for IDW interpolation
   - Used as: value
   - Default: 2.0

9. **`cells : int, required`**
   - Minimum number of data cells within search radius
   - Used as: value
   - Default: 8

10. **`flags : str, optional`**
   - Allowed values: m, k, w, u, s
   - m
   - Interpret distance as map units, not number of cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.fill.stats.html#__tabbed_2_3) for all details)*

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.fill.stats.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.fill.stats is a module for fast gap filling and interpolation
(with smoothing) of dense raster data.

The r.fill.stats module is capable of quickly filling small data
gaps in large and high-resolution raster maps. It's primary purpose is
to improve high-resolution, rasterized sensor data (such as Lidar data).
As a rule of thumb, there should be at least as many data cells as there
are "no data" (NULL) cells in the input raster map. Several
interpolation modes are available. By default, all values of the input
raster map will be replaced with locally interpolated values in the
output raster map. This is the equivalent of running a low-pass
smoothing filter on the interpolated data and is often desirable, owing
to noisy nature of high-resolution sensor data. With dense data and
small gaps, this should result in only slight deviations from the
original data and produce smooth output. Alternatively, setting the -k flag will disable the low-pass filter and preserve the original
cell values.

Available gap filling modes:

The spatially weighted mean is equivalent to an Inverse Distance
Weighting (IDW; see also r.surf.idw ) interpolation.
The simple mean is equivalent to a simple low-pass filter. Median and
mode replacements can also be achieved using r.neighbors .

Note that r.fill.stats is highly optimized for fast processing of
large raster datasets with a small interpolation distance threshold
(i.e. closing small gaps). As a trade-off for speed and a small memory
foot print, some spatial accuracy is lost due to the rounding of the
distance threshold to the closest approximation in input raster cells
and the use of a matrix of precomputed weights at cell resolution (see
further down for details). Note also that processing time will increase
exponentially with higher distance settings. Cells outside the distance
threshold will not be interpolated, preserving the edges of the original
data extent.

This module is not well suited for interpolating sparse input data and
closing large gaps. For such purposes more appropriate methods are
available, such as v.surf.bspline , v.surf.idw or v.surf.rst .

Applications where the properties of r.fill.stats are advantageous
include the processing of high resolution, close range scanning and
remote sensing datasets. Such datasets commonly feature densely spaced
measurements that have some gaps after rasterization, due to blind
spots, instrument failures, and misalignments between the GIS' raster
cell grids and the original measurement locations. In these cases, r.fill.stats should typically be run using the "weighted mean"
(default) method and with a small distance setting (the default is to
use a search radius of just three cells).

The images below show a gradiometer dataset with gaps and its
interpolated equivalent, produced using the spatially weighted mean
operator ( mode="wmean" ).



In addition, r.fill.stats can be useful for raster map generalization.
Often, this involves removing small clumps of categorized cells and then
filling the resulting data gaps without "inventing" any new values. In
such cases, the "mode" or "median" interpolators should be used.

The most critical user-provided settings are the interpolation/gap
filling method ( mode ) and the maximum distance, up to which r.fill.stats will scan for cells with values ( distance ). The
distance can be expressed as a number of cells (default) or in the
current coordinate reference system's units (if the -m flag is
given). The latter are typically meters, but can be any other units of a planar coordinate system.

Note that proper handling of geodetic coordinates (lat/lon) and
distances is currently not implemented. For lat/lon data, the distance
should therefore be specified in cells and usage of r.fill.stats should be restricted to small areas to avoid large inaccuracies that may
arise from the different extents of cells along the latitudinal and
longitudinal axes.

Distances specified in map units ( -m flag) will be approximated as
accurately as the current region's cell resolution settings allow. The
program will warn if the distance cannot be expressed as whole cells at
the current region's resolution. In such case, the number of cells in
the search window will be rounded up. Due to the rounding effect
introduced by using cells as spatial units, the actual maximum distance
considered by the interpolation may be up to half a cell diagonal larger
than the one specified by the user.

The interpolator type "wmean" uses a precomputed matrix of spatial
weights to speed up computation. This matrix can be examined (printed to
the screen) before running the interpolation, by setting the -w flag. In mode "wmean", the power option has the usual meaning in
IDW: higher values mean that cell values in the neighborhood lose their
influence on the cell to be interpolated more rapidly with increasing
distance from the latter. Another way of explaining this effect is to
state that larger "power" settings result in more localized
interpolation, smaller ones in more globalized interpolation. The
default setting is power=2.0 .

The interpolators "mean", "median" and "mode" are calculated from all
cell values within the search radius. No spatial weighting is applied
for these methods. The "mode" of the input data may not always be
unique. In such case, the mode will be the smallest value with the
highest frequency.

Often, input data will contain spurious extreme measurements (spikes,
outliers, noise) caused by the limits of device sensitivity, hardware
defects, environmental influences, etc. If the normal, valid range of
input data is known beforehand, then the minimum and maximum options can be used to exclude those input cells that have values below
or above that range, respectively. This will prevent the influence of
spikes and outliers from spreading through the interpolation.

Unless the -k (keep) flag is given, data cells of the input map will
be replaced with interpolated values instead of preserving them in the
output. In modes "wmean" and "mean", this results in a smoothing effect
that includes the original data (see below)!

Besides the result of the interpolation/gap filling, a second output map
can be specified via the uncertainty option. The cell values in this
map represent a simple measure of how much uncertainty was involved in
interpolating each cell value of the primary output map, with "0" being
the lowest and "1" being the theoretic highest uncertainty. Uncertainty
is measured by summing up all cells in the neighborhood (defined by the
search radius distance ) that contain a value in the input map,
multiplied by their weights, and dividing the result by the sum of all
weights in the neighborhood. For mode=wmean , this means that
interpolated output cells that were computed from many nearby input
cells have very low uncertainty and vice versa. For all other modes, all
weights in the neighborhood are constant "1" and the uncertainty measure
is a simple measure of how many input data cells were present in the
search window.

The r.fill.stats module uses the interpolated values to adjust the
original values and create a smooth surface, which is akin to running a
low-pass filter on the data. Since most high-resolution sensor data is
noisy, this is normally a desired effect and results in output that is
more suitable for deriving secondary products, such as slope, aspect and
curvature maps. Larger settings for the search radius ( distance )
will result in a stronger smoothing. In practice, some experimentation
with different settings for distance and power might be required
to achieve good results. In some cases (e.g. when dealing with low-noise
or classified data), it might be desirable to turn off data smoothing by
setting the -k (keep) flag. This will ensure that the original cell
data is copied through to the result map without alteration.

Effect of smoothing the original data: The top row shows a gap-filled
surface computed from a rasterized Lidar point cloud (using mode=wmean and power=2 ), and the derived slope, aspect, and profile curvature
maps. The smoothing effect is clearly visible. The bottom row shows the
effect of setting the -k flag: Preserving the original cell values
in the interpolated output produces and unsmoothed, noisy surface, and
likewise noisy derivative maps.

The effect can be seen in the illustration above: Slope, aspect, and
profile curvature are computed using the r.slope.aspect module, which uses a window
(kernel) for computations that considers only the immediate neighborhood
of each cell. When performed on noisy data, such local operations result
in equally noisy derivatives if the original data is preserved (by
setting the -k flag) and no smoothing is performed.

(Note that the effects of noisy data can also be avoided by using
modules that are not restricted to minimal kernel sizes. For example,
aspect and other morphometric parameters can be computed using the r.param.scale module which operates with
variable-size cell neighborhoods.)

The key to getting good gap filling results is to understand the spatial
weighting scheme used in mode "wmean". The weights are precomputed and
assigned per cell within the search window centered on the location at
which to interpolate/gap fill all cells within the user-specified
distance.

The illustration below shows the precomputed weights matrix for a search
distance of four cells from the center cell:

Note that the weights in such a small window drop rapidly for the
default setting of power=2 .

If the distance is given in map units (flag -m ), then the search
window can be modeled more accurately as a circle. The illustration
below shows the precomputed weights for a distance in map units that is
approximately equivalent to four cells from the center cell:

When using a small search radius, cells must also be set to a small
value. Otherwise, there may not be enough cells with data within the
search radius to support interpolation.

---

## See Also

Related tools:
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [`v.fill.holes`](https://grass.osgeo.org/grass-devel/manuals/v.fill.holes.html)

---

## Resources

- [Official r.fill.stats manual](https://grass.osgeo.org/grass-devel/manuals/r.fill.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.fill.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
