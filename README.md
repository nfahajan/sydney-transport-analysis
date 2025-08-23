# Sydney Public Transport Data Analysis

## Overview

This project analyzes Sydney's public transport system using GTFS (General Transit Feed Specification) data. The analysis provides insights into the city's transportation network, including busiest stops, routes, peak hours, and service patterns. The project processes raw GTFS data to generate visualizations and metrics that help understand Sydney's public transport efficiency and usage patterns.

## Features

- **Data Processing**: Handles large GTFS datasets with efficient memory management
- **Statistical Analysis**: Identifies busiest stops and routes by trip frequency
- **Temporal Analysis**: Analyzes peak hours and weekly service patterns
- **Headway Analysis**: Calculates average wait times between services
- **Geographic Visualization**: Interactive maps showing stop locations and usage
- **Data Export**: Generates CSV files with key insights

## Dataset

The project uses GTFS data from Sydney's public transport system, including:

- **Agency information** (57KB)
- **Routes** (1.2MB) - Bus, train, ferry, and light rail routes
- **Stops** (16MB) - All transport stops with coordinates
- **Trips** (25MB) - Individual service trips
- **Stop Times** (390MB) - Detailed arrival/departure schedules
- **Calendar** (131KB) - Service availability by day
- **Shapes** (969MB) - Geographic route shapes

## Prerequisites

- Python 3.7+
- Google Colab (for running the notebook)
- Google Drive (for data storage)

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/nfahajan/sydney-transport-analysis.git
   cd sydney-transport-analysis
   ```

2. **Download the Required Datasets:**

Google Drive Link:

3. **Install required packages:**

   ```bash
   pip install pandas numpy matplotlib folium
   ```

4. **Upload GTFS data to Google Drive:**
   - Place your GTFS CSV files in a folder (e.g., `datasetnws/gtfs`)
   - Update the `BASE` variable in the script to point to your data location

## Usage

### Option 1: Google Colab Notebook

1. Open `public_transport_data_of_sydney.ipynb` in Google Colab
2. Mount your Google Drive
3. Update the `BASE` path to point to your GTFS data folder
4. Run all cells sequentially

### Option 2: Python Script

1. Update the `BASE` variable in `public_transport_data_of_sydney.py`
2. Run the script:
   ```bash
   python public_transport_data_of_sydney.py
   ```

## Analysis Outputs

### 1. Busiest Stops

- Identifies top 20 stops by unique trips
- Bar chart visualization of stop usage
- Exported to `busiest_stops.csv`

### 2. Busiest Routes

- Ranks routes by trip frequency
- Shows route names and trip counts
- Exported to `busiest_routes.csv`

### 3. Peak Hour Analysis

- Hourly distribution of stop events
- Identifies peak service hours
- Exported to `hourly_stop_events.csv`

### 4. Weekly Service Patterns

- Service availability by day of week
- Bar chart showing daily service counts

### 5. Headway Analysis

- Average wait times between services
- Distribution of headways across routes and hours
- Exported to `route_hour_headway.csv`

### 6. Geographic Visualization

- Interactive Folium map of Sydney
- All stops shown as faint markers
- Top 200 busiest stops highlighted in red
- Popup information with stop names and trip counts

## Key Functions

- **`parse_gtfs_time()`**: Safely parses GTFS time format (handles >24:00:00 times)
- **`time_to_sec()`**: Converts time strings to seconds for analysis
- **`avg_headway()`**: Calculates average wait times between services

## Data Processing Pipeline

1. **Data Loading**: Reads GTFS CSV files with appropriate data types
2. **Data Cleaning**: Removes duplicates, handles missing values, filters valid coordinates
3. **Time Conversion**: Converts arrival/departure times to seconds for analysis
4. **Data Merging**: Combines stop times, trips, routes, and stops data
5. **Analysis**: Performs statistical analysis and generates visualizations
6. **Export**: Saves key insights to CSV files

## Output Files

- `busiest_stops.csv` - Top stops by trip frequency
- `busiest_routes.csv` - Top routes by trip frequency
- `hourly_stop_events.csv` - Hourly service distribution
- `route_hour_headway.csv` - Average wait times by route and hour

## Customization

- **Location**: Update map center coordinates for different cities
- **Time Range**: Modify to analyze specific time periods
- **Filters**: Add route type or service day filters
- **Visualizations**: Customize chart styles and colors

## Performance Notes

- The script is optimized for large GTFS datasets
- Uses `low_memory=False` for better performance with large files
- Filters data early to reduce memory usage
- Processes only necessary columns from large datasets

## License

This project is open source and available under the [MIT License](LICENSE).
