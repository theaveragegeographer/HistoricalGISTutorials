# Working with Historical Maps

## Introduction

Historical maps are invaluable sources for understanding past landscapes, boundaries, and spatial relationships. This tutorial teaches you to:

- Georeference historical maps
- Extract information from old maps
- Combine historical maps with modern GIS data
- Create historical reconstruction maps

## What is Georeferencing?

Georeferencing is the process of assigning real-world coordinates to a scanned historical map image. This allows you to:

- Overlay the historical map on modern geography
- Compare past and present landscapes
- Extract geographic features as GIS data
- Perform spatial analysis on historical information

## Learning Objectives

By the end of this tutorial, you will be able to:
- Prepare historical map images for georeferencing
- Use QGIS Georeferencer tool
- Choose appropriate control points
- Assess georeferencing accuracy
- Extract features from georeferenced maps
- Create historical basemaps

## Part 1: Finding Historical Maps

### Digital Map Collections

**Major repositories**:
- **David Rumsey Map Collection**: davidrumsey.com (over 150,000 maps)
- **Library of Congress Maps**: loc.gov/maps
- **Old Maps Online**: oldmapsonline.org
- **British Library**: bl.uk/maps
- **National Archives**: archives.gov
- **University Libraries**: Many have digitized collections

### Choosing Maps for Your Research

Consider:
- **Geographic coverage**: Does it cover your study area?
- **Time period**: When was it created?
- **Scale**: Is detail sufficient for your needs?
- **Purpose**: What was the map's original use?
- **Reliability**: Who created it? How accurate is it?
- **Image quality**: Is resolution high enough?

### Downloading Maps

Best practices:
- Download highest resolution available
- Save original metadata
- Note source, date, creator, copyright
- Keep unmodified copy
- Use TIFF format when available (better than JPEG)

## Part 2: Preparing for Georeferencing

### Understanding the Historical Map

Before georeferencing, examine your map:

**Map elements to identify**:
- Title and date
- Scale bar or scale statement
- Legend
- Orientation (north arrow)
- Projection information (if indicated)
- Known reference points

**Ask questions**:
- What is the map's purpose?
- How accurate was original surveying?
- Has the landscape changed significantly?
- Are place names still recognizable?

### Identifying Control Points

Control points are locations that appear on both the historical map and modern geography:

**Good control point choices**:
- Road intersections (if roads still exist)
- Building corners (for stable structures)
- River confluences
- Coastline features (if unchanged)
- Bridge locations
- Property corners
- Survey markers

**Poor control point choices**:
- Coastlines (change over time)
- River courses (can shift)
- Ephemeral features
- Locations where landscape has dramatically changed

### Choosing Reference System

**For most historical maps**:
- Use WGS84 (EPSG:4326) as your target CRS
- Or use a local projection appropriate to the area

**Consider**:
- Map's original projection (if known)
- Study area extent
- Need for area or distance accuracy

## Part 3: Georeferencing in QGIS

### Step 1: Open Georeferencer

1. In QGIS, go to `Layer > Georeferencer`
2. The Georeferencer window opens
3. This is a separate interface from the main QGIS window

### Step 2: Load Historical Map

1. Click `File > Open Raster`
2. Browse to your historical map image
3. The map displays in the georeferencer
4. Use zoom and pan tools to navigate

### Step 3: Set Transformation Settings

Before adding control points, configure settings:

1. Click `Settings > Transformation Settings`
2. **Transformation type**: 
   - Polynomial 1 (for simple maps)
   - Polynomial 2 or 3 (for maps with distortion)
   - Thin Plate Spline (for complex distortions)
3. **Resampling method**: 
   - Nearest neighbor (for categorical data)
   - Cubic (for smoother appearance)
4. **Target CRS**: Set to WGS84 (EPSG:4326) or appropriate projection
5. **Output raster**: Choose save location
6. Check "Load in QGIS when done"
7. OK

### Step 4: Add Control Points

**Process**:
1. Zoom to a recognizable feature on the historical map
2. Click `Add Point` button
3. Click on the feature in the historical map
4. Dialog opens: "Enter map coordinates"

**Option A - From map canvas**:
1. Click "From map canvas" button
2. QGIS main window activates
3. Navigate to the same location (use OpenStreetMap as reference)
4. Click on the corresponding location
5. Returns to georeferencer with coordinates filled

**Option B - Manual entry**:
1. If you know exact coordinates, enter them
2. Useful for surveyed points

**Repeat**:
- Add at least 6-10 control points
- Distribute evenly across the map
- More points = better accuracy
- Focus on edges and corners

### Step 5: Check Residual Errors

As you add points, the GCP (Ground Control Point) table shows:
- **Residual**: Error for each point (in map units)
- Lower is better
- Look for outliers
- High residual = bad point or error

**Reviewing errors**:
1. Sort by residual column
2. Identify high-error points
3. Right-click problem points > `Delete`
4. Or click point and reposition
5. Aim for residuals < 5 pixels

### Step 6: Run Georeferencing

1. Click green "Start Georeferencing" button (play icon)
2. Processing occurs
3. Georeferenced raster saves to specified location
4. Automatically loads in QGIS (if option checked)

### Step 7: Verify Results

Back in main QGIS:
1. The georeferenced map appears
2. Toggle visibility to compare with base map
3. Check alignment at control points and elsewhere
4. Assess overall accuracy

**If results are poor**:
- Add more control points
- Remove bad control points
- Try different transformation type
- Check CRS settings

## Part 4: Extracting Features from Historical Maps

### Digitizing Process

Once your map is georeferenced, extract geographic features:

### Example: Digitizing Historical Roads

**Step 1: Create new layer**
1. `Layer > Create Layer > New Shapefile Layer`
2. Geometry type: Line
3. Add fields:
   - Name (Text)
   - Type (Text)
   - Date (Text)
4. Save as "historical_roads.shp"

**Step 2: Start editing**
1. Select your new layer
2. Click "Toggle Editing" (pencil icon)
3. Click "Add Line Feature"

**Step 3: Trace features**
1. Click along a road on the historical map
2. Follow the route
3. Right-click to finish
4. Enter attributes
5. Repeat for other roads

**Step 4: Save**
1. Save edits frequently
2. Stop editing when done

### Digitizing Buildings

Create polygon layer for historical buildings:
1. New shapefile with polygon geometry
2. Add attributes: Name, Type, Date, Use
3. Trace building footprints
4. Record information from map

### Digitizing Land Use

For areas with different uses (forest, farmland, urban):
1. Create polygon layer
2. Attribute: Land_Use, Date
3. Digitize boundaries between different uses
4. Create comprehensive land use map

## Part 5: Advanced Georeferencing Techniques

### Working with Map Series

For atlases or series of maps covering one area:

**Approach**:
1. Georeference one map carefully (primary)
2. Use same control points for others in series
3. Export/save control points
4. Import for next map
5. Adjust as needed

### Handling Distorted Maps

Some historical maps have significant distortions:

**Solutions**:
- Use Thin Plate Spline transformation
- Add many control points (20+)
- Georeference in sections
- Accept limitations
- Document distortions

### Mosaicking Multiple Map Sheets

For large areas covered by multiple map sheets:

1. Georeference each sheet separately
2. Use `Raster > Miscellaneous > Merge`
3. Select all georeferenced sheets
4. Create single mosaic
5. May need to adjust seams

## Part 6: Creating Historical Basemaps

### Styling Georeferenced Maps

Make your historical map more readable:

**Transparency**:
1. Right-click layer > Properties
2. Transparency tab
3. Adjust global opacity (50-70% often works)
4. Allows modern data to show through

**Contrast enhancement**:
1. In Symbology tab
2. Adjust contrast, brightness
3. Enhance readability

**Clipping to area of interest**:
1. Use `Raster > Extraction > Clip Raster by Extent`
2. Remove unwanted map areas
3. Focus on your study region

### Combining Multiple Historical Layers

Layer different time periods:
- 1850s map
- 1900s map
- 1950s map
- Modern basemap

Toggle visibility to compare change over time.

## Part 7: Analyzing Historical Maps

### Comparing Past and Present

**Overlay analysis**:
1. Place georeferenced historical map over modern imagery
2. Identify changes:
   - Urban expansion
   - Land use change
   - Transportation network evolution
   - Water body changes

### Measuring Historical Features

Use measurement tools on georeferenced maps:
- Lengths of historical roads
- Areas of historical land uses
- Distances between historical features

**Note**: Accuracy limited by map quality and georeferencing precision.

### Creating Change Maps

Show what's changed:

1. Digitize features from historical map (e.g., forest extent in 1850)
2. Digitize same features from modern data
3. Use overlay analysis to show:
   - What was lost
   - What was gained
   - What remained stable

## Part 8: Case Study - Urban Growth

### Example Project: City Expansion 1880-2020

**Data needed**:
- Historical map(s) of city from 1880s
- Modern satellite imagery or map
- City boundary data

**Steps**:
1. Georeference 1880s map
2. Digitize historical city boundary
3. Obtain modern city boundary
4. Create overlay showing expansion
5. Calculate area change
6. Analyze direction of growth
7. Relate to historical factors (railroads, industry, topography)

**Map output**:
- Side-by-side comparison
- Overlay showing old and new boundaries
- Statistical summary

## Part 9: Best Practices

### Documentation

Always document:
- Source of historical map
- Date of map creation
- Georeferencing parameters used
- Number and distribution of control points
- Estimated accuracy
- Known limitations

### Accuracy Assessment

Be realistic about accuracy:
- Historical maps often have errors
- Georeferencing adds additional uncertainty
- Document uncertainty in your analysis
- Don't claim false precision

### Preservation

- Keep original high-resolution image
- Save georeferencing control points
- Document transformation parameters
- Maintain metadata

### Citation

Properly cite historical maps:
- Creator/cartographer
- Title
- Date
- Publisher
- Archive/collection
- Access date (for digital collections)

## Part 10: Common Challenges and Solutions

### Challenge: Map has no recognizable features
**Solution**: 
- Research historical place names
- Use historical gazetteers
- Consult other maps from same period
- Use physical features (rivers, coastlines)

### Challenge: Landscape has changed dramatically
**Solution**:
- Focus on stable features
- Use geological features
- Accept lower accuracy
- Document assumptions

### Challenge: Map is torn or damaged
**Solution**:
- Work with undamaged portions
- Scan before and after restoration attempts
- Focus control points on good areas

### Challenge: Unknown projection
**Solution**:
- Try common projections for region/period
- Test different options
- Look for historical documentation
- Consult cartographic history resources

### Challenge: Map has artistic distortions
**Solution**:
- Some maps prioritized aesthetics over accuracy
- Use many control points
- Accept limitations
- Note in documentation

## Resources

### Tutorials
- QGIS Georeferencing Documentation
- "Georeferencing Historical Maps" by Harvard CGA
- Library of Congress georeferencing guide

### Tools
- **QGIS Georeferencer**: Primary tool
- **MapWarper**: Online collaborative georeferencing
- **ArcGIS**: Professional option
- **GDAL**: Command-line option

### Collections
- David Rumsey Map Collection (extensive tutorials)
- NYC Space/Time Directory (georeferenced historical maps)
- Georeferencer.com (collaborative platform)

## Next Steps

Continue learning:
- [Spatial Analysis for Historical Research](./06-spatial-analysis.md) - Analyze your georeferenced data
- [Data Sources and Resources](./07-data-sources.md) - Find more historical maps and data

## Assignment Ideas

### Beginner
1. Georeference a simple city map from 1900
2. Digitize main streets
3. Compare to modern street network

### Intermediate
1. Georeference historical topographic map
2. Extract elevation contours
3. Compare to modern DEM

### Advanced
1. Georeference series of maps (1850, 1900, 1950, 2000)
2. Digitize urban extent for each period
3. Analyze patterns and rates of urban growth
4. Create animated map showing change over time
5. Write research paper interpreting findings
