# Spatial Analysis for Historical Research

## Introduction

This tutorial covers advanced GIS analytical techniques specifically tailored for historical research questions. Move beyond basic mapping to perform sophisticated spatial analysis that generates new historical insights.

## Learning Objectives

By the end of this tutorial, you will be able to:
- Apply proximity analysis to historical data
- Perform network analysis on historical transportation systems
- Conduct density and clustering analysis
- Analyze spatial patterns and distributions
- Perform change detection over time
- Use spatial statistics for historical questions

## Part 1: Proximity Analysis

### Distance-Based Analysis

**Historical questions**:
- How close were settlements to water sources?
- What areas were accessible from trading posts?
- How far could armies march in a day?

### Creating Buffer Zones

**Example: Market Reach Analysis**

**Question**: What areas were within a day's travel (30 km) of market towns in medieval England?

**Steps**:
1. Load market town point data
2. Go to `Vector > Geoprocessing Tools > Buffer`
3. Set distance: 30 kilometers (30000 meters)
4. Run analysis
5. Result: Circles showing market reach

**Interpretation**:
- Where do buffers overlap? (Multiple market access)
- Where are gaps? (Underserved areas)
- Relate to population distribution
- Consider terrain effects (30 km harder in mountains)

### Multiple Ring Buffers

Show graduated distance zones:

**Example: Defensive perimeter analysis**

1. Select city/fortress point
2. Use "Multiple Ring Buffer" tool
3. Create rings at: 5, 10, 15, 20 km
4. Style with graduated transparency
5. Analyze what falls in each zone

### Distance to Nearest Feature

**Question**: How far was each village from the nearest Roman road?

1. Have village points and road lines
2. Use `Hub Distance` tool
3. Settings:
   - Hub layer: Roads
   - Spoke layer: Villages
4. Result: Distance values added to village attributes
5. Analyze distribution of distances

## Part 2: Network Analysis

### Analyzing Historical Transportation Networks

Network analysis studies movement along connected routes.

### Setting Up a Network

**Requirements**:
- Line layer representing routes (roads, rivers, trails)
- Topology (routes properly connected at intersections)
- Optional: Travel speed/cost attributes

**Preparing data**:
1. Use "Snap geometries" to ensure connections
2. Check for gaps using "Check validity"
3. Create proper network topology

### Shortest Path Analysis

**Question**: What was the shortest route between London and York in medieval times?

**Using Processing Toolbox**:
1. Open Processing Toolbox
2. Find "Shortest path (point to point)"
3. Settings:
   - Vector layer: Road network
   - Start point: London coordinates
   - End point: York coordinates
4. Run
5. Result: Line showing optimal route

**Historical considerations**:
- Shortest ≠ fastest (terrain matters)
- Roads quality varied
- Seasonal factors (flooding, snow)
- Political boundaries (tolls, safety)

### Service Area Analysis

**Question**: How far could travelers reach from Rome in one day?

1. Use "Service area (from point)" tool
2. Set travel distance or time
3. Result: Polygon showing reachable area
4. Compare to historical journey records

### Route Comparison

Compare calculated optimal routes to:
- Known historical itineraries
- Roman road atlases
- Pilgrimage routes
- Trade routes

**Discrepancies reveal**:
- Political factors
- Economic considerations
- Cultural significance
- Safety concerns
- Infrastructure quality

## Part 3: Density and Clustering

### Point Density Analysis

**Question**: Where were archaeological sites most concentrated?

**Heat maps**:
1. Use "Heatmap" tool (in Processing)
2. Input: Point layer of sites
3. Set radius (e.g., 50 km)
4. Output: Raster showing density
5. Style with color ramp (cool to hot)

**Interpretation**:
- High density: Settlement clusters
- Low density: Marginal areas
- Patterns related to: resources, terrain, political centers

### Kernel Density Estimation

More sophisticated than simple heat maps:

1. Processing > "Kernel Density Estimation"
2. Set bandwidth appropriately for scale
3. Results show probability distribution
4. Useful for site prediction modeling

### Cluster Analysis

**Question**: Are historical sites randomly distributed or clustered?

**DBSCAN Clustering**:
1. Processing > "DBSCAN clustering"
2. Set minimum points and distance
3. Algorithm identifies clusters
4. Color-code results
5. Analyze spatial groups

**Interpretation**:
- Clustered: Suggest common causes (resources, defense)
- Random: Might indicate individual decisions
- Dispersed: Possible competition or territory

### Nearest Neighbor Analysis

Statistical test for clustering:

1. Processing > "Nearest neighbor analysis"
2. Calculates index:
   - < 1: Clustered
   - = 1: Random
   - > 1: Dispersed
3. Provides p-value for significance

## Part 4: Spatial Pattern Analysis

### Centrographic Statistics

Find the center of spatial distributions:

**Mean Center**:
- Geographic center of a set of points
- "Average location"
- Useful for comparing distributions

**Example**: Compare mean center of:
- Roman settlements in 100 CE
- Same region in 300 CE
- Shows direction of population shift

**Weighted Mean Center**:
- Weights points by attribute (e.g., population)
- More important sites have greater influence

### Standard Distance

Measure of dispersion around the mean center:
- Like standard deviation in spatial form
- Shows how spread out features are
- Compare across time periods

### Directional Distribution (Standard Deviational Ellipse)

Shows:
- Orientation of distribution
- Degree of elongation
- Main axis of pattern

**Example**: Analyze settlement pattern along a river valley

## Part 5: Overlay Analysis

### Vector Overlay Operations

Combine multiple spatial datasets:

**Intersection**:
- Find areas where features overlap
- Example: Settlements within Roman provinces

**Union**:
- Combine all features
- Example: Total territory of allied kingdoms

**Difference**:
- Subtract one from another
- Example: Territory lost in a war

**Clip**:
- Cookie-cutter operation
- Example: Extract sites within study region

### Historical Application Example

**Question**: Which Roman roads passed through Gaul?

1. Load road network layer
2. Load Gaul boundary polygon
3. Use "Clip" tool
4. Settings:
   - Input: Roads
   - Overlay: Gaul boundary
5. Result: Only roads within Gaul
6. Calculate total length

### Multi-Layer Analysis

**Example**: Site location model

Combine factors:
1. Near water (buffer rivers)
2. Fertile soil (land use data)
3. Defensible position (slope/elevation)
4. Near trade routes (buffer roads)

**Process**:
- Create buffers/selections for each factor
- Intersect all layers
- Find areas meeting all criteria
- Compare to known site locations
- Predict unknown sites

## Part 6: Temporal Analysis

### Time-Series Mapping

Visualize change over time:

**Example**: Urban growth 1800-2000

1. Data: Urban extent for 1800, 1850, 1900, 1950, 2000
2. Create separate layers for each period
3. Calculate areas
4. Identify expansion directions
5. Calculate growth rates

### Change Detection

**Comparing two time periods**:

1. Load extent for Time 1
2. Load extent for Time 2
3. Use overlay tools:
   - Intersection: Stable areas (remained urban)
   - Symmetrical difference: Changed areas

**Categorize changes**:
- New urban development
- Abandoned areas
- Persistent urban core

### Rate of Change Analysis

Calculate spatial rate of change:

```
Rate = (Area_t2 - Area_t1) / (Time_t2 - Time_t1)
```

Compare rates:
- Different regions
- Different time periods
- Different phenomena

## Part 7: Terrain Analysis

### Digital Elevation Models (DEMs)

Essential for understanding:
- Defensibility
- Settlement patterns
- Agricultural potential
- Transportation routes

### Slope Analysis

**Question**: Were Roman villas built on gentle slopes?

1. Load DEM
2. `Raster > Analysis > Slope`
3. Result: Slope in degrees/percent
4. Extract slope values for villa locations
5. Compare to overall slope distribution

### Aspect Analysis

Direction slopes face:
- Important for agriculture (sun exposure)
- Climate (wind protection)
- Defense (visibility)

**Process**:
1. `Raster > Analysis > Aspect`
2. Result: Direction each cell faces (0-360°)
3. Analyze patterns

### Viewshed Analysis

**Question**: What was visible from a castle?

1. Load DEM
2. Use "Viewshed" tool
3. Input: Castle location
4. Optional: Observer height, radius
5. Result: Binary raster (visible/not visible)

**Historical applications**:
- Signal tower networks
- Defensive positions
- Settlement placement
- Symbolic locations (visibility to population)

### Least-Cost Path

**Question**: What was the easiest route through mountains?

1. Create cost surface (based on slope)
2. Steep slopes = high cost
3. Use "Least cost path" tool
4. Compare to actual historical routes

**Cost factors to consider**:
- Slope
- Land cover
- Water crossings
- Political boundaries

## Part 8: Spatial Statistics

### Global Moran's I

Tests for spatial autocorrelation:
- Are similar values clustered?
- Or randomly distributed?

**Example**: Testing if wealthy areas cluster together in historical city

### Getis-Ord Gi* (Hot Spot Analysis)

Identifies statistically significant hot and cold spots:

**Example**: Where were pottery production centers concentrated?

1. Count pottery finds by region
2. Run hot spot analysis
3. Identify high-concentration areas
4. Interpret: Production centers? Trade hubs?

### Ripley's K-Function

Analyzes clustering at multiple distance scales:
- Shows at what distances clustering occurs
- Helps understand spatial processes

## Part 9: Spatial Interpolation

### Predicting Unknown Values

When you have sample points, interpolate to create continuous surface:

**Methods**:
- **IDW (Inverse Distance Weighting)**: Simple, intuitive
- **Kriging**: Statistical, accounts for spatial autocorrelation
- **Splines**: Smooth surfaces

### Historical Applications

**Example**: Reconstructing population density

1. Known population for cities
2. Interpolate across region
3. Result: Estimated density surface
4. Use for questions about regional population

**Caveats**:
- Only as good as sample data
- Assumes smooth variation
- May not reflect historical reality
- Document assumptions

## Part 10: Case Study Integration

### Complete Analysis Project

**Topic**: Medieval Market Town Spatial Economics

**Research question**: What factors influenced market town success?

**Data needed**:
- Market town locations with founding dates
- Population estimates
- Road network
- River network  
- Elevation data
- Agricultural land quality

**Analyses to perform**:

1. **Proximity analysis**:
   - Distance between markets
   - Market territories (Thiessen polygons)

2. **Network analysis**:
   - Centrality measures
   - Optimal trade routes

3. **Terrain analysis**:
   - Relationship to topography
   - Agricultural land access

4. **Statistical analysis**:
   - Correlation between factors and success
   - Cluster analysis of town types

5. **Temporal analysis**:
   - When were markets founded?
   - How did network evolve?

**Deliverables**:
- Series of analytical maps
- Statistical results
- Historical interpretation
- Research paper

## Part 11: Best Practices

### Choose Appropriate Methods

Match method to question:
- Don't use complex analysis for simple questions
- Ensure method assumptions are met
- Understand what results mean

### Validate Results

Check if results make historical sense:
- Compare to known historical patterns
- Consult historical sources
- Use multiple methods
- Statistical significance ≠ historical significance

### Document Methods

For reproducibility:
- Record all parameters
- Document data sources
- Explain choices
- Share scripts/models

### Interpret Carefully

Remember:
- GIS shows patterns, not causes
- Correlation ≠ causation
- Historical context essential
- Uncertainty exists

## Resources

### QGIS Tools
- Processing Toolbox (extensive algorithms)
- GRASS GIS (advanced analysis)
- SAGA GIS (terrain analysis)
- Network Analysis Library

### R Packages for Spatial Analysis
- sf: Spatial features
- raster: Raster data
- spatstat: Point pattern analysis
- spdep: Spatial dependence

### Further Reading
- *Geographic Information Analysis* by David O'Sullivan and David Unwin
- *Spatial Analysis: A Guide for Ecologists* (methods applicable to history)
- Research articles in *Journal of Historical Geography*

## Next Steps

- [Data Sources and Resources](./07-data-sources.md) - Find data for your analyses
- Apply these techniques to your own research questions
- Combine multiple methods for comprehensive analysis

## Practice Exercises

### Exercise 1: Proximity
Analyze how proximity to rivers affected settlement in your region of interest.

### Exercise 2: Network
Calculate travel times between historical cities using road networks.

### Exercise 3: Clustering
Test if archaeological sites cluster and identify significant clusters.

### Exercise 4: Terrain
Determine optimal locations for historical fortifications using viewshed analysis.

### Exercise 5: Change
Quantify and visualize urban growth over a 100-year period.
