# Getting Started with Historical GIS

## Introduction

Welcome to Historical GIS Tutorials! This guide will help you set up your environment and prepare for the tutorials ahead.

## What is GIS?

Geographic Information Systems (GIS) are tools and technologies for capturing, managing, analyzing, and displaying spatial data. For historians, GIS provides powerful ways to:

- Visualize historical events and phenomena in space and time
- Analyze spatial patterns and relationships
- Create interactive maps and visualizations
- Combine multiple historical datasets
- Answer research questions that involve geography

## Software Installation

### QGIS (Recommended)

QGIS is a free, open-source GIS application that works on Windows, Mac, and Linux.

**Installation Steps:**

1. Visit [qgis.org](https://qgis.org)
2. Download the Long Term Release (LTR) version for stability
3. Follow the installation instructions for your operating system
4. Launch QGIS to verify installation

### Alternative: Web-Based Tools

Many tutorials can also be completed using web-based tools:
- ArcGIS Online (requires account)
- Google My Maps (free, limited functionality)
- Felt (modern, user-friendly interface)

## Basic Skills Review

Before starting the tutorials, ensure you're comfortable with:

### File Management
- Creating and organizing folders
- Understanding file paths
- Working with different file formats (CSV, GeoJSON, Shapefiles)

### Data Organization
- Working with spreadsheets
- Understanding tabular data
- Basic data cleaning concepts

### Historical Research
- Evaluating source reliability
- Understanding historical context
- Working with primary and secondary sources

## Understanding Coordinate Systems

One of the most important concepts in GIS is coordinate systems. Historical data often comes in various formats:

- **Latitude/Longitude**: Geographic coordinates (e.g., 41.9028° N, 12.4964° E for Rome)
- **Projected Coordinates**: Planar coordinates for specific regions
- **Historical Place Names**: Require geocoding to convert to coordinates

Don't worry if this seems complex - we'll cover it in detail in later tutorials!

## Data Formats You'll Encounter

- **CSV/Excel**: Tabular data with location information
- **Shapefiles**: Vector GIS format (polygons, lines, points)
- **GeoJSON**: Web-friendly geographic data format
- **KML/KMZ**: Google Earth format
- **Raster**: Images and scanned historical maps

## Setting Up Your Workspace

Create a folder structure for your work:

```
HistoricalGIS/
├── data/
│   ├── raw/
│   └── processed/
├── maps/
└── projects/
```

This organization will help you manage files as you progress through tutorials.

## Getting Help

- QGIS has extensive documentation at [docs.qgis.org](https://docs.qgis.org)
- Stack Exchange GIS community
- Historical GIS communities on social media
- Your tutorial materials in this repository

## Next Steps

Now that you're set up, proceed to [Introduction to Historical GIS](./02-introduction-to-historical-gis.md) to begin learning core concepts.

## Troubleshooting

### QGIS Won't Launch
- Check system requirements
- Try reinstalling
- Check for conflicting software

### Can't Find Data Files
- Verify file paths
- Check file extensions
- Ensure files aren't corrupted

### Map Layers Not Displaying
- Check coordinate reference systems (CRS)
- Verify layer visibility settings
- Check data extent and zoom level
