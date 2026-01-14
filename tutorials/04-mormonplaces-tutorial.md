# MormonPlaces Tutorial

## Introduction to MormonPlaces

MormonPlaces is a comprehensive digital gazetteer of places significant to the history of The Church of Jesus Christ of Latter-day Saints (Mormon Church). It provides georeferenced data for:

- Settlement locations
- Migration routes
- Church historical sites
- Temple locations
- Pioneer trails
- Historical events

**Website**: [mormonplaces.org](https://mormonplaces.org/) or accessible through Church History resources

## Learning Objectives

By the end of this tutorial, you will be able to:
- Access and download MormonPlaces data
- Map Mormon settlement patterns in the 19th century
- Analyze migration routes to Utah
- Visualize the expansion of Mormon settlements
- Create timeline maps showing historical progression

## Historical Context

### The Mormon Pioneer Movement (1830s-1890s)

Understanding the history enhances your spatial analysis:

**1830-1839**: Early period in New York, Ohio, Missouri
**1839-1846**: Nauvoo, Illinois period
**1846-1847**: Exodus and westward migration
**1847-1869**: Establishment of Salt Lake City and settlement expansion
**1869-1890s**: Railroad era and continued expansion

### Key Geographic Events

- **1847**: Arrival in Salt Lake Valley
- **Mormon Trail**: 1,300-mile route from Nauvoo to Salt Lake City
- **Colonization missions**: Systematic settlement of the Intermountain West
- **Handcart companies**: 1856-1860 migrations

## Part 1: Accessing MormonPlaces Data

### Step 1: Navigate to Data Sources

MormonPlaces data may be available through:
1. Church History Library
2. FamilySearch resources
3. Academic datasets (check with university libraries)
4. Public domain historical records

For this tutorial, we'll work with sample datasets representing:
- Settlement locations with dates
- Migration routes
- Historical landmarks

### Step 2: Understanding the Data Structure

Typical attributes in Mormon historical geographic data:
- **Place name**: Official or common name
- **Type**: Settlement, landmark, temple, historical site
- **Date founded/established**: Year or date range
- **Population**: If available
- **Significance**: Brief description
- **Coordinates**: Latitude/longitude

### Step 3: Data Preparation

Create a CSV file with Mormon settlement data:

```csv
Name,Type,Founded,Latitude,Longitude,State,Notes
Salt Lake City,Settlement,1847,40.7608,-111.8910,Utah,Original settlement
Provo,Settlement,1849,40.2338,-111.6585,Utah,Established by colonizing mission
Ogden,Settlement,1848,41.2230,-111.9738,Utah,Fort Buenaventura site
St. George,Settlement,1861,37.0965,-113.5684,Utah,Dixie mission
Brigham City,Settlement,1851,41.5102,-112.0155,Utah,Box Elder settlement
Nauvoo,Settlement,1839,40.5501,-91.3849,Illinois,City of Joseph pre-exodus
Winter Quarters,Camp,1846,41.3055,-95.9345,Nebraska,Temporary settlement
```

Save this as `mormon_settlements.csv` in your data folder.

## Part 2: Loading Data in QGIS

### Step 1: Create New Project

1. Open QGIS
2. Create new project: `Project > New`
3. Save as "Mormon_Settlement_History.qgz"

### Step 2: Add Base Map

1. Add OpenStreetMap or another base layer
2. Zoom to western United States
3. Consider using a terrain base map to show geographic challenges

### Step 3: Import Settlement Data

**From CSV**:
1. Go to `Layer > Add Layer > Add Delimited Text Layer`
2. Browse to your CSV file
3. Set options:
   - File format: CSV
   - Geometry definition: Point coordinates
   - X field: Longitude
   - Y field: Latitude
   - Geometry CRS: EPSG:4326 (WGS 84)
4. Click Add

### Step 4: Verify Data

1. Open attribute table (right-click layer > `Open Attribute Table`)
2. Verify all records imported correctly
3. Check that points appear in correct locations

## Part 3: Creating Timeline Maps

### Visualizing Settlement Expansion Over Time

**Method 1: Color by Decade**

1. Right-click settlements layer > `Properties`
2. Go to `Symbology`
3. Change to "Categorized"
4. Choose "Founded" field
5. Click `Classify`
6. Assign colors:
   - 1830s: Light color
   - 1840s: Medium color
   - 1850s: Darker color
   - 1860s+: Darkest color
7. Apply

**Method 2: Graduated Symbols by Date**

1. In Symbology, choose "Graduated"
2. Use "Founded" field
3. Set size to increase over time
4. This visually shows expansion chronology

### Creating an Animated Map

For showing change over time:

1. Install "TimeManager" plugin (`Plugins > Manage and Install Plugins`)
2. Configure time settings
3. Set time attribute to "Founded"
4. Create animation showing settlements appearing chronologically
5. Export as video or image sequence

## Part 4: Mapping Migration Routes

### The Mormon Trail

Create a line feature for the Mormon Trail:

**Method 1: Manual Digitizing**

1. Create new shapefile: `Layer > Create Layer > New Shapefile Layer`
2. Geometry type: Line
3. Add field: "Route_Name" (Text)
4. Save as "mormon_trail.shp"

**Digitizing the route**:
1. Toggle editing (click pencil icon)
2. Click `Add Line Feature`
3. Click along the trail route:
   - Nauvoo, IL
   - Through Iowa
   - Winter Quarters, NE
   - Along Platte River
   - Through Wyoming
   - Salt Lake City, UT
4. Right-click to finish line
5. Enter route name in dialog
6. Save edits and stop editing

**Method 2: Using Historical Route Data**

If you have GPS track or waypoint data:
1. Import GPX file
2. Or create from coordinate list
3. Style appropriately

### Styling the Trail

1. Right-click trail layer > `Properties`
2. Go to `Symbology`
3. Choose distinctive style:
   - Dashed line
   - Brown or gold color
   - 2-3 pixel width
4. Add arrow decorations to show direction

## Part 5: Spatial Analysis

### Analyzing Settlement Patterns

**Question**: How far apart were settlements?

1. Install "Distance Matrix" plugin
2. Run analysis to calculate distances between all settlements
3. Find average, minimum, and maximum distances
4. Interpret in historical context (day's travel, communication networks)

### Elevation Analysis

**Question**: At what elevations were settlements established?

1. Download elevation data (SRTM or similar)
2. Add raster layer to QGIS
3. Use `Sample Raster Values` tool
4. Extract elevation for each settlement point
5. Analyze distribution

**Historical Context**:
- Valley locations for agriculture
- Water access critical
- Defensive considerations

### Proximity to Water

**Question**: How close were settlements to rivers?

1. Add river/water body layer (Natural Earth Data)
2. Use `Distance to nearest hub` tool
3. Calculate distance from each settlement to nearest river
4. Visualize with graduated symbols

### Regional Clustering

**Question**: Were there distinct settlement clusters?

1. Use `DBSCAN Clustering` tool
2. Identify regional groups:
   - Wasatch Front corridor
   - Southern Utah "Dixie" settlements
   - Northern settlements
3. Analyze why clusters formed where they did

## Part 6: Creating Comprehensive Maps

### Map 1: Settlement Expansion (1847-1869)

**Elements to include**:
- All settlements with founding dates
- Mormon Trail route
- State/territory boundaries
- Major rivers and topography
- Legend showing time periods
- Title: "Mormon Settlement in the Intermountain West, 1847-1869"

**Analysis text to include**:
"Settlements radiated outward from Salt Lake City along transportation corridors and to locations with agricultural potential."

### Map 2: The Mormon Trail

**Elements to include**:
- Complete trail route
- Starting point (Nauvoo) and destination (Salt Lake City)
- Intermediate stops (Winter Quarters, Fort Laramie, etc.)
- Distances marked
- Elevation profile
- Historical imagery if available

### Map 3: Temple Locations

If your data includes temples:
- Map all temple locations
- Show when each was built
- Analyze spatial distribution
- Relate to population centers

## Part 7: Combining Multiple Datasets

### Overlay with Other Historical Data

**Native American territories**:
- Show whose traditional lands were affected
- Important for complete historical understanding
- Context for intercultural interactions

**US Territory boundaries**:
- Show political context
- Utah Territory vs. modern state
- Changing boundaries over time

**Railroads**:
- First Transcontinental Railroad (1869)
- How it changed settlement patterns
- Before and after comparisons

## Part 8: Historical Interpretation

### Understanding Spatial Patterns

**Systematic colonization**:
- Not random settlement
- Church-directed missions
- Strategic locations chosen
- Resource distribution considered

**Environmental adaptation**:
- Irrigation necessity in arid climate
- Cooperative water management
- Settlement site selection criteria

**Transportation networks**:
- Following rivers and valleys
- Creating new roads
- Connection to trade routes

### Addressing Historical Context

When presenting your maps, include:

**Primary sources**:
- Pioneer journals
- Church records
- Contemporary accounts

**Secondary sources**:
- Historical scholarship
- Archaeological evidence
- Demographic studies

**Critical perspectives**:
- Multiple viewpoints
- Impact on indigenous populations
- Environmental changes
- Social organization

## Part 9: Advanced Projects

### Project 1: Migration Timing Analysis

Create visualizations showing:
- Seasonal patterns of migration
- Company sizes and routes
- Handcart companies vs. wagon trains
- Success and tragedy events along the trail

### Project 2: Comparative Settlement Studies

Compare Mormon settlement patterns to:
- Other western US settlement
- Planned vs. organic growth
- Religious vs. secular communities
- Success rates in different environments

### Project 3: Network Analysis

Analyze communication networks:
- Mail routes between settlements
- Telegraph lines
- Trade relationships
- Administrative hierarchy

### Project 4: Environmental History

Study human-environment interactions:
- Land use change
- Water management systems
- Agricultural development
- Long-term environmental impact

## Resources and Further Reading

### Online Resources
- Church History Library
- FamilySearch research tools
- Overland Trails Digital Collections
- National Park Service Trail documentation

### Books
- *The Mormon Trail: Yesterday and Today* by William E. Hill
- *Pioneer Women of Faith and Fortitude* (various authors)
- *Kingdom in the West: The Mormons and the American Frontier* by Eugene E. Campbell

### Academic Resources
- Historical Geography journals
- Western History collections
- Digital Humanities projects
- University special collections

### Related Datasets
- Oregon Trail data
- California Trail data
- Pioneer Register databases
- Census records

## Next Steps

Continue your Historical GIS learning:
- [Working with Historical Maps](./05-historical-maps.md) - Georeference historical trail maps
- [Spatial Analysis for Historical Research](./06-spatial-analysis.md) - Advanced analytical techniques
- [Data Sources and Resources](./07-data-sources.md) - Find more historical datasets

## Troubleshooting

### Date Field Issues
- Ensure dates in consistent format (YYYY or YYYY-MM-DD)
- Handle date ranges appropriately
- Use earliest date for chronological mapping

### CSV Import Problems
- Check delimiter (comma vs. semicolon)
- Verify coordinate format (decimal degrees)
- Remove special characters from field names

### Coordinate System Errors
- Always use EPSG:4326 for lat/long data
- Reproject if needed for analysis
- Check that X=longitude, Y=latitude (not reversed)

### Historical Accuracy
- Cross-reference multiple sources
- Document data provenance
- Note uncertainties in metadata
- Distinguish between exact and approximate locations
