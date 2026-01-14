# Digital Atlas of Roman and Medieval Civilization (DARMC) Tutorial

## Introduction to DARMC

The Digital Atlas of Roman and Medieval Civilization (DARMC) is a comprehensive spatial database developed by Harvard University's Center for Geographic Analysis. It provides georeferenced data for:

- Ancient and medieval settlements
- Road networks
- Political boundaries
- Physical geography
- Trade routes
- Military campaigns

**Website**: [darmc.harvard.edu](https://darmc.harvard.edu/)

## Learning Objectives

By the end of this tutorial, you will be able to:
- Access and download DARMC datasets
- Import DARMC data into QGIS
- Create maps of Roman and medieval geography
- Analyze spatial patterns in ancient settlements
- Combine multiple DARMC layers

## Part 1: Accessing DARMC Data

### Step 1: Navigate to DARMC

1. Visit [darmc.harvard.edu](https://darmc.harvard.edu/)
2. Explore the available datasets
3. Review the data documentation

### Step 2: Understanding the Data Structure

DARMC provides data in several formats:
- **Shapefiles**: Standard GIS vector format
- **KML**: Google Earth format
- **GeoJSON**: Web-friendly format

Data categories include:
- **Settlements**: Cities, towns, and villages
- **Infrastructure**: Roads, aqueducts, bridges
- **Political**: Boundaries, provinces, kingdoms
- **Physical**: Rivers, mountains, coastlines
- **Cultural**: Temples, theaters, amphitheaters

### Step 3: Download Sample Dataset

For this tutorial, we'll work with Roman settlements and road networks.

1. Download the Roman settlements layer
2. Download the Roman roads layer
3. Save both to your `data/raw/` folder

## Part 2: Loading Data in QGIS

### Step 1: Start a New Project

1. Open QGIS
2. Create a new project: `Project > New`
3. Save as "Roman_Geography.qgz" in your projects folder

### Step 2: Add Base Map

1. In the Browser panel, expand "XYZ Tiles"
2. Double-click "OpenStreetMap" for context
3. This provides modern geography for reference

### Step 3: Import DARMC Settlements

1. Click `Layer > Add Layer > Add Vector Layer`
2. Browse to your downloaded settlements shapefile
3. Click "Add"
4. The layer appears on your map

### Step 4: Import DARMC Roads

1. Repeat the process for the roads shapefile
2. Arrange layers in the Layers panel (roads above base map, settlements on top)

## Part 3: Styling Your Map

### Styling Settlements by Size

1. Right-click settlements layer > `Properties`
2. Go to `Symbology` tab
3. Change from "Single Symbol" to "Graduated"
4. Choose a population attribute (if available)
5. Set size ranges to represent different settlement sizes
6. Apply and OK

**Tip**: Use graduated symbols to show hierarchy:
- Small dots for villages
- Medium circles for towns  
- Large circles for major cities

### Styling Roman Roads

1. Right-click roads layer > `Properties`
2. Go to `Symbology` tab
3. Choose a distinctive color (e.g., red or brown)
4. Set appropriate line width (1-2 pixels)
5. Consider using dashed lines for secondary roads

### Color Schemes for Historical Maps

Choose colors that evoke the historical period:
- Earth tones: browns, ochres, tans
- Classical colors: red for roads, gold for cities
- Muted palette: avoid bright modern colors

## Part 4: Basic Spatial Analysis

### Analyzing Settlement Distribution

**Question**: Where were Roman settlements concentrated?

1. Use the `Identify Features` tool to click on settlements
2. Examine attribute data (name, type, date)
3. Observe patterns:
   - Coastal vs. inland
   - Along roads vs. isolated
   - Regional clustering

### Measuring Distances

**Question**: How far apart were major cities?

1. Select `View > Toolbars > Advanced Digitizing`
2. Click the `Measure Line` tool
3. Click between two settlements
4. View distance in the measure dialog

**Historical Context**: 
- Roman mile ≈ 1,479 meters
- Typical day's travel: 20-25 Roman miles
- Use this to understand ancient perceptions of distance

### Creating Buffers

**Question**: What areas were within 50 km of Roman roads?

1. Select roads layer
2. Go to `Vector > Geoprocessing Tools > Buffer`
3. Set distance to 50 km (50000 meters)
4. Run the analysis
5. Style the buffer with transparency to see the extent of road influence

### Spatial Queries

**Question**: Which settlements were within 10 km of roads?

1. Go to `Vector > Research Tools > Select by Location`
2. Select settlements that intersect road buffers
3. View selected features
4. Export selection if needed: `Right-click layer > Export > Save Selected Features`

## Part 5: Creating a Publishable Map

### Step 1: Set Up Print Layout

1. Go to `Project > New Print Layout`
2. Name it "Roman Roads and Settlements"
3. The layout designer opens

### Step 2: Add Map Frame

1. Click `Add Item > Add Map`
2. Draw a rectangle on the canvas
3. The map view appears in the frame

### Step 3: Add Map Elements

**Title**:
1. Click `Add Item > Add Label`
2. Enter "Roman Roads and Settlements in [Region]"
3. Format the text (font, size, bold)

**Legend**:
1. Click `Add Item > Add Legend`
2. Place on the map
3. Remove unnecessary items
4. Rename items for clarity

**Scale Bar**:
1. Click `Add Item > Add Scale Bar`
2. Place at bottom of map
3. Choose appropriate style

**North Arrow**:
1. Click `Add Item > Add North Arrow`
2. Place in a corner
3. Choose a simple style

**Attribution**:
1. Add a label with: "Data: Digital Atlas of Roman and Medieval Civilization (Harvard CGA)"
2. Include your name and date

### Step 4: Export

1. Click `Layout > Export as Image` or `Export as PDF`
2. Choose resolution (300 DPI for print quality)
3. Save to your maps folder

## Part 6: Advanced Exercises

### Exercise 1: Temporal Analysis

If your DARMC data includes dates:
1. Filter settlements by time period
2. Create maps showing different periods
3. Observe changes in settlement patterns

**Method**:
- Right-click layer > `Filter`
- Write expression: `"date" >= 100 AND "date" <= 200` (for 100-200 CE)

### Exercise 2: Network Analysis

Analyze the Roman road network:
1. Install the "Networks" plugin
2. Calculate shortest paths between cities
3. Compare to actual Roman itineraries

### Exercise 3: Multi-Period Comparison

Create a series showing:
1. Republican period settlements
2. Early Imperial settlements
3. Late Imperial settlements
4. Medieval settlements

Use consistent symbology across all maps for comparison.

### Exercise 4: Regional Focus

Choose a specific province:
1. Britannia (Roman Britain)
2. Aegyptus (Roman Egypt)  
3. Gallia (Roman Gaul)

Create detailed maps with:
- All settlement types
- Road networks
- Provincial boundaries
- Major features (rivers, mountains)

## Part 7: Historical Interpretation

### Connecting Patterns to History

When you observe spatial patterns, ask:

**Settlement Patterns**:
- Why are settlements concentrated in certain areas?
- How does geography influence location?
- What historical events affected distribution?

**Road Networks**:
- What was the strategic purpose of this road?
- How did roads facilitate administration?
- How did they enable trade and communication?

**Temporal Changes**:
- How did Roman conquest change settlement patterns?
- What happened during periods of instability?
- How did medieval patterns differ from Roman?

### Limitations and Uncertainties

Be aware of data limitations:
- **Survival bias**: We know more about large sites
- **Archaeological coverage**: Some regions better studied
- **Dating precision**: Dates may be approximate
- **Name variations**: Same place, different names over time

Always include these considerations in your analysis.

## Resources and Data Sources

### DARMC Components
- **DARMC Geodatabase**: Comprehensive spatial database
- **Base Maps**: Ancient world geography
- **Thematic Layers**: Specialized datasets

### Complementary Resources
- **Pleiades**: Ancient place names and coordinates
- **Barrington Atlas**: Standard reference for ancient geography
- **Orbis**: Stanford's Roman world travel time model
- **Pelagios**: Linked ancient data

### Further Reading
- *The Barrington Atlas of the Greek and Roman World*
- DARMC documentation and methodology papers
- Research articles using DARMC data

## Next Steps

Continue learning with:
- [MormonPlaces Tutorial](./04-mormonplaces-tutorial.md) - Different time period and region
- [Working with Historical Maps](./05-historical-maps.md) - Georeferencing techniques
- [Spatial Analysis for Historical Research](./06-spatial-analysis.md) - Advanced analytical methods

## Troubleshooting

### Data Won't Load
- Check file format (shapefile requires .shp, .shx, .dbf, .prj)
- Verify file paths
- Try different import method

### Wrong Location/Projection
- Check Coordinate Reference System (CRS)
- DARMC typically uses WGS84 (EPSG:4326)
- Set project CRS to match data

### Performance Issues
- Simplify geometry for display
- Create spatial index
- Reduce number of features shown

### Style Not Showing
- Check layer order in Layers panel
- Verify transparency settings
- Ensure attribute field exists for graduated symbols
