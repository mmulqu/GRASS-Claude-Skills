# v.cluster

**Category**: vector

## Description

Performs cluster identification.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_cluster(input,output,layer="2",distance=None,min=None,method="dbscan",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`layer : str, optional`**
   - Layer number or name for cluster ids
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`distance : float, optional`**
   - Maximum distance to neighbors

5. **`min : int, optional`**
   - Minimum number of points to create a cluster

6. **`method : str, optional`**
   - Clustering method
   - Allowed values: dbscan, dbscan2, density, optics, optics2
   - Default: dbscan

7. **`flags : str, optional`**
   - Allowed values: 2, b, t
   - 2
   - Force 2D clustering

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.cluster.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.cluster partitions a point cloud into clusters or clumps.

If the minimum number of points is not specified with the min option, the minimum number of points to constitute a cluster is number
of dimensions + 1 , i.e. 3 for 2D points and 4 for 3D points.

If the maximum distance is not specified with the distance option,
the maximum distance is estimated from the observed distances to the
neighbors using the upper 99% confidence interval.

v.cluster supports different methods for clustering. The recommended
methods are method=dbscan if all clusters should have a density
(maximum distance between points) not larger than distance or method=density if clusters should be created separately for each
observed density (distance to the farthest neighbor).

The Density-Based Spatial Clustering of Applications with
Noise is a commonly used
clustering algorithm. A new cluster is started for a point with at least min - 1 neighbors within the maximum distance. These neighbors are
added to the cluster. The cluster is then expanded as long as at least min - 1 neighbors are within the maximum distance for each point
already in the cluster.

Similar to dbscan , but here it is sufficient if the resultant cluster
consists of at least min points, even if no point in the cluster has
at least min - 1 neighbors within distance .

This method creates clusters according to their point density. The
maximum distance is not used. Instead, the points are sorted ascending
by the distance to their farthest neighbor (core distance), inspecting min - 1 neighbors. The densest cluster is created first, using as
threshold the core distance of the seed point. The cluster is expanded
as for DBSCAN, with the difference that each cluster has its own maximum
distance. This method can identify clusters with different densities and
can create nested clusters.

This method is Ordering Points to Identify the Clustering
Structure . It is
controlled by the number of neighbor points (option min - 1). The core
distance of a point is the distance to the farthest neighbor. The
reachability of a point q is its distance from a point p (original
optics: max(core-distance(p), distance(p, q))). The aim of the optics method is to reduce the reachability of each point. Each unprocessed
point is the seed for a new cluster. Its neighbors are added to a queue
sorted by smallest reachability if their reachability can be reduced.
The points in the queue are processed and their unprocessed neighbors
are added to a queue sorted by smallest reachability if their
reachability can be reduced.

The optics method does not create clusters itself, but produces an
ordered list of the points together with their reachability. The output
list is ordered according to the order of processing: the first point
processed is the first in the list, the last point processed is the last
in the list. Clusters can be extracted from this list by identifying
valleys in the points' reachability, e.g. by using a threshold value. If
a maximum distance is specified, this is used to identify clusters,
otherwise each separated network will constitute a cluster.

The OPTICS algorithm uses each yet unprocessed point to start a new
cluster. The order of the input points is arbitrary and can thus
influence the resultant clusters.

EXPERIMENTAL This method is similar to OPTICS, minimizing the
reachability of each point. Points are reconnected if their reachability
can be reduced. Contrary to OPTICS, a cluster's seed is not fixed but
changed if possible. Each point is connected to another point until the
core of the cluster (seed point) is reached. Effectively, the initial
seed is updated in the process. Thus separated networks of points are
created, with each network representing a cluster. The maximum distance
is not used.

---

## See Also

Related tools:
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`v.hull`](https://grass.osgeo.org/grass-devel/manuals/v.hull.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)

---

## Resources

- [Official v.cluster manual](https://grass.osgeo.org/grass-devel/manuals/v.cluster.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.cluster.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
