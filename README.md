# School Route Analyzer (location allocation)

## Overview

The School Route Analyzer is a powerful, browser-based web application designed for visualizing and analyzing school bus route data. It provides an interactive map and a dynamic data table to help transportation planners and school administrators understand pupil distribution, market share for each school, and other key metrics from a location-allocation perspective.

Users can upload a standard CSV file containing pickup information, and the application will instantly generate insightful visualizations and metrics, turning raw data into actionable intelligence.

## Features

-   **Interactive Map**: Utilizes Mapbox for a high-quality, detailed basemap.
    
-   **Multiple Visualization Layers**:
    
    -   **School Markers**: Each school is color-coded based on its total pupil count, from green (low) to red (high).
        
    -   **Spider Diagram**: Displays straight-line connections from each school to its assigned pupils.
        
    -   **Market Share Polygons**: Generates color-coded convex hulls representing the 25%, 50%, 75%, and 100% quartiles of pupil locations for each school. This helps visualize the density and geographic spread of the student body.
        
-   **Resizable Horizontal Layout**: A draggable divider allows you to resize the map and data table panes for optimal viewing on any screen.
    
-   **Dynamic Data Table**:
    
    -   **Calculated Metrics**: Automatically calculates the pupil count and the area (in square miles) for each market share polygon for every school.
        
    -   **Advanced Sorting**: Click on any column header to sort the entire dataset by that metric.
        
    -   **Column-Specific Filtering**: Filter data in real-time by school name or by using numeric operators (e.g., `>50`, `<10`) in the Pupils and Area columns.
        
    -   **Interactive Rows**: Clicking a row in the table instantly zooms the map to that specific school and displays its layers.
        
-   **Dynamic Statistical Summaries**: The table header displays the **Total** and **Mean** for all numeric columns, which update instantly as you filter the data.
    
-   **Data Export**: Export the currently filtered and sorted data to a CSV file with a single click.
    
-   **File-Based**: Simply upload a local CSV file to get started—no server-side setup required.
    

## How to Use

1.  **Launch the App**: Open the `index.html` file in a modern web browser.
    
2.  **Upload Data**: Click the "Upload CSV" button and select your data file. The application will process it and populate the map and table.
    
3.  **Interact with the Map**:
    
    -   Use the layer control in the top-right corner to toggle the "Spider Diagram" and "Market Share" layers.
        
    -   Click on any school marker to see its name and pupil count.
        
4.  **Analyze with the Table**:
    
    -   **Sort Data**: Click on headers like "Pupils" or "75% Area (sq mi)" to reorder the schools.
        
    -   **Filter Data**: Use the filter row below the headers to narrow down the schools. For example, type `>100` in the "Pupils" filter to see schools with more than 100 students.
        
    -   **Select a School**: Click anywhere on a school's row to focus the map on it and see its specific visualization layers.
        
5.  **Adjust Layout**: Click and drag the horizontal bar between the map and the table to give more or less space to either component.
    
6.  **Export Results**: After filtering and sorting, click the "Export to CSV" button to download a CSV file of the view you have created.
    

## Data Format

The application requires a CSV file with a header row. For a row to be processed as a valid pickup, it must contain the following columns:

-   `Seg_No`: A segment number. Any row where this value is not `0` is treated as a pickup.
    
-   `School_Code_&_Name`: The name of the school.
    
-   `school_lat`: The latitude of the school.
    
-   `school_lon`: The longitude of the school.
    
-   `pupil_lat`: The latitude of the pupil's pickup location.
    
-   `pupil_lon`: The longitude of the pupil's pickup location.
    

## Technical Stack

-   **Frontend**: HTML5, CSS3
    
-   **Styling**: [Tailwind CSS](https://tailwindcss.com/ "null")
    
-   **Mapping Library**: [Leaflet.js](https://leafletjs.com/ "null")
    
-   **Geospatial Analysis**: [Turf.js](https://turfjs.org/ "null")
    
-   **CSV Parsing**: [PapaParse](https://www.papaparse.com/ "null")
    
-   **Basemap Provider**: [Mapbox](https://www.mapbox.com/ "null")
