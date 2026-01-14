# Introduction to Historical GIS

## What is Historical GIS?

Historical GIS is the application of Geographic Information Systems technology to historical research and analysis. It combines the spatial thinking of geography with the temporal depth of history, allowing researchers to:

- Map historical events and phenomena
- Analyze spatial patterns over time
- Visualize change across landscapes
- Test hypotheses about spatial relationships
- Present research findings in compelling visual formats

## Why Use GIS for Historical Research?

### Spatial Analysis
Many historical questions have a geographic dimension:
- How did trade networks evolve?
- Where did populations migrate?
- What was the extent of political boundaries?
- How did disease spread through regions?

### Data Integration
GIS allows you to combine multiple types of historical evidence:
- Archaeological site locations
- Historical documents with place names
- Census data
- Environmental data
- Historical maps

### Visualization
Maps communicate complex spatial information effectively:
- Show patterns that aren't obvious in tables
- Reveal spatial relationships
- Engage both academic and public audiences
- Support data-driven storytelling

## Core GIS Concepts for Historians

### Spatial Data Types

**Vector Data**: Discrete features represented as:
- **Points**: Individual locations (cities, archaeological sites, battle locations)
- **Lines**: Linear features (roads, rivers, trade routes)
- **Polygons**: Areas (kingdoms, provinces, land parcels)

**Raster Data**: Grid-based data:
- Satellite imagery
- Scanned historical maps
- Elevation models
- Climate data

### Attributes

Each spatial feature can have associated information:
- A point representing a city might have: name, population, founding date
- A polygon representing a kingdom might have: ruler, time period, area

### Coordinate Reference Systems (CRS)

Understanding how locations are represented:
- **Geographic CRS**: Uses latitude/longitude (e.g., WGS84)
- **Projected CRS**: Converts curved Earth to flat map
- Historical maps may use different systems than modern data

### Scale and Resolution

Consider the appropriate level of detail:
- Regional vs. local analysis
- Generalized vs. detailed boundaries
- Temporal resolution (yearly, decadal, century)

## Historical GIS Workflows

### 1. Research Question
Start with a clear historical question that has a spatial component.

**Example**: "How did Roman settlement patterns change in Britain after the conquest?"

### 2. Data Collection
Gather relevant spatial historical data:
- Archaeological reports with site locations
- Historical texts mentioning places
- Existing GIS datasets (like DARMC)
- Historical maps to georeference

### 3. Data Preparation
Clean and organize your data:
- Standardize place names
- Convert dates to consistent format
- Geocode locations (convert place names to coordinates)
- Ensure coordinate systems match

### 4. Analysis
Apply GIS techniques:
- Mapping distributions
- Calculating distances
- Analyzing clusters
- Measuring densities
- Creating buffers around features

### 5. Interpretation
Connect spatial patterns to historical context:
- Why do you see these patterns?
- What historical processes explain them?
- What's missing from the data?
- What are the limitations?

### 6. Presentation
Share your findings:
- Static maps for publications
- Interactive web maps
- Map series showing change over time
- Combined with traditional historical narrative

## Challenges in Historical GIS

### Data Quality
- Incomplete historical records
- Uncertain locations
- Changing place names
- Missing temporal information

### Uncertainty
- Approximate boundaries
- Debated locations
- Variable dating
- Source reliability

### Representation
- How to show change over time?
- How to represent uncertainty?
- How to avoid false precision?
- How to maintain historical context?

### Technical Issues
- Learning curve for GIS software
- Data format compatibility
- Large file sizes
- Software costs (mitigated by QGIS!)

## Best Practices

### Document Your Sources
- Track where each data point comes from
- Note reliability assessments
- Include metadata with datasets
- Maintain a bibliography

### Be Transparent About Uncertainty
- Indicate approximations
- Show confidence levels
- Explain data gaps
- Discuss limitations

### Think Critically
- Question your data
- Consider bias in sources
- Recognize patterns vs. causation
- Connect spatial analysis to historical interpretation

### Start Simple
- Begin with straightforward mapping
- Add complexity gradually
- Focus on answering specific questions
- Don't let technology drive the research

## Examples of Historical GIS Projects

### Urban History
- Mapping city growth over centuries
- Analyzing neighborhood change
- Studying infrastructure development

### Military History
- Visualizing campaigns and battles
- Analyzing strategic locations
- Mapping supply lines and logistics

### Economic History
- Trade network analysis
- Market area studies
- Resource distribution patterns

### Social History
- Migration patterns
- Demographic change
- Social segregation studies

### Religious History
- Spread of religious movements
- Distribution of religious institutions
- Pilgrimage route analysis

## Tools and Technologies

### Desktop GIS
- **QGIS**: Free, open-source, powerful
- **ArcGIS**: Industry standard, expensive, extensive features
- **GRASS GIS**: Advanced analysis, steeper learning curve

### Web-Based Tools
- **ArcGIS Online**: Cloud-based mapping
- **Felt**: Modern, collaborative mapping
- **Carto**: Web mapping platform
- **Google My Maps**: Simple, limited functionality

### Programming Options
- **R with sf/tmap**: Statistical GIS
- **Python with GeoPandas**: Flexible scripting
- **JavaScript with Leaflet**: Web mapping

### Data Resources
- Digital Atlas of Roman and Medieval Civilization
- MormonPlaces
- Pelagios (linked ancient geodata)
- Natural Earth (base maps)
- Historical GIS databases by region

## Next Steps

Now that you understand the fundamentals, you're ready to work with actual historical GIS data! 

Proceed to:
- [Digital Atlas of Roman and Medieval Civilization Tutorial](./03-darmc-tutorial.md) - Learn to work with Roman and medieval spatial data
- [MormonPlaces Tutorial](./04-mormonplaces-tutorial.md) - Explore 19th-century American religious geography

## Further Reading

- **Books**:
  - *Placing History: How Maps, Spatial Data, and GIS Are Changing Historical Scholarship* edited by Anne Kelly Knowles
  - *Past Time, Past Place: GIS for History* by Anne Kelly Knowles
  - *The Spatial Humanities: GIS and the Future of Humanities Scholarship* edited by David J. Bodenhamer

- **Articles**:
  - "Historical GIS: Technologies, Methodologies, and Scholarship" by Ian Gregory
  - "Toward a Spatial History" by Richard White

- **Websites**:
  - [Harvard Center for Geographic Analysis](https://gis.harvard.edu/)
  - [QGIS Historical Data Tutorial](https://www.qgistutorials.com/)
