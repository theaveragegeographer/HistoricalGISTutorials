# Example Data and Projects

This directory contains sample datasets and example projects to help you practice the techniques covered in the tutorials.

## Sample Datasets

### ancient_cities.csv
A sample dataset of major ancient Roman cities with coordinates and attributes, useful for practicing:
- Data import from CSV
- Point mapping
- Attribute visualization
- Basic spatial analysis

### historical_roads_sample.geojson
Sample road network data for practicing:
- Line feature styling
- Network analysis
- Buffer analysis
- Proximity calculations

## Example Projects

### Project 1: Mapping Ancient Trade Routes
**Tutorial References**: Tutorials 02, 03, 06

**Objective**: Create a map showing major ancient cities and the trade routes connecting them

**Skills Practiced**:
- Importing point and line data
- Styling features appropriately
- Creating a publication-quality map
- Adding cartographic elements

**Data Needed**: 
- ancient_cities.csv (provided)
- historical_roads_sample.geojson (provided)

**Steps**:
1. Import cities dataset into QGIS
2. Import roads dataset
3. Add a basemap for context
4. Style cities by population or importance
5. Style roads with appropriate symbology
6. Create a print layout with title, legend, scale bar
7. Export as PDF or image

### Project 2: Settlement Proximity Analysis
**Tutorial References**: Tutorials 06

**Objective**: Analyze the relationship between settlements and water sources

**Skills Practiced**:
- Buffer analysis
- Distance calculations
- Spatial queries
- Statistical summary

**Steps**:
1. Load settlement points
2. Load river/water body data
3. Create buffers around water features
4. Calculate distances from settlements to nearest water
5. Analyze and visualize results
6. Interpret findings in historical context

### Project 3: Temporal Change Visualization
**Tutorial References**: Tutorials 02, 06

**Objective**: Show how settlement patterns changed over different time periods

**Skills Practiced**:
- Filtering data by attributes
- Creating time-series maps
- Comparison and change analysis
- Map series creation

**Steps**:
1. Filter cities dataset by founding date
2. Create separate maps for different centuries
3. Use consistent symbology across maps
4. Create a map series showing temporal progression
5. Analyze patterns of expansion

## Creating Your Own Examples

As you work through the tutorials, you can:
1. Add your own practice datasets here
2. Save your QGIS project files (.qgz) 
3. Document your workflow
4. Share examples with others learning Historical GIS

## Data Format Notes

### CSV Format
CSV files should include:
- Place name
- Latitude (decimal degrees)
- Longitude (decimal degrees)
- Date information
- Other relevant attributes

Example:
```csv
Name,Latitude,Longitude,Type,Founded,Population
Rome,41.9028,12.4964,Capital,753 BCE,1000000
Athens,37.9838,23.7275,City,3000 BCE,250000
```

### GeoJSON Format
GeoJSON is a modern, web-friendly format for geographic data. It can represent points, lines, and polygons with attributes.

## Resources for Finding Practice Data

- Natural Earth Data: https://www.naturalearthdata.com/
- Pleiades: https://pleiades.stoa.org/
- DARMC: https://darmc.harvard.edu/
- See Tutorial 07 for comprehensive list

## Getting Help

If you encounter issues with the example data or projects:
1. Review the relevant tutorial sections
2. Check QGIS documentation
3. Consult Stack Exchange GIS community
4. Open an issue in this repository

## Contributing Examples

Have a great example project? Consider contributing:
1. Document your workflow clearly
2. Include source citations for data
3. Provide step-by-step instructions
4. Share both data and final outputs
5. Submit via pull request

## License Note

Sample data provided here is for educational purposes. When using external datasets, always:
- Check the license
- Provide proper attribution
- Respect usage restrictions
- Cite sources appropriately
