# Air Quality Analysis of Poland, Switzerland, and Germany

## Project Overview

This project focuses on the analysis of air quality data from Poland, Switzerland, and Germany using the Air Quality Analysis API. The objective is to collect, store, and visualize critical air quality parameters like PM2.5 and PM10. These parameters are essential for monitoring air pollution levels that affect public health. Interactive Grafana dashboards are used to display trends in real-time data, including line graphs, bar charts, and gauges.

## Air Quality Parameters

### PM2.5
PM2.5 (particulate matter ≤ 2.5 micrometers) can penetrate deep into the lungs and bloodstream, leading to severe health issues. Sources include:
- Vehicle emissions
- Industrial processes
- Combustion of fossil fuels

### PM10
PM10 (particulate matter ≤ 10 micrometers) primarily affects the respiratory system. Sources include:
- Dust
- Pollen
- Construction sites
- Industrial activities

### Importance
High levels of PM2.5 and PM10 can:
- Reduce visibility
- Harm ecosystems
- Lead to significant health risks

The World Health Organization (WHO) and the Air Quality Index (AQI) provide standard ranges to classify air quality.

## Tools and Technologies Used

- **Node-RED**: A flow-based development tool used to connect APIs, databases, and services. It fetches air quality data using HTTP GET requests from the Air Quality Analysis API, processes the response, and pushes the data into InfluxDB.
- **InfluxDB**: A time-series database optimized for storing and querying time-stamped data, used to store air quality data for Poland, Switzerland, and Germany, including PM2.5, PM10, and timestamps.
- **Grafana**: A visualization tool used to create interactive dashboards that connect to InfluxDB and display air quality data in various formats, such as line graphs, bar charts, and gauges.
- **JSON**: JavaScript Object Notation used as the data format for API responses, which Node-RED processes to extract relevant air quality parameters.

## Dashboard Visualisations

- **Data Sources**: InfluxDB buckets for Poland, Switzerland, and Germany.
- **Panels**:
  - Line graphs showing trends in PM2.5 and PM10 levels over time.
  - Bar charts comparing weekly averages.
  - Gauges displaying real-time levels with color-coded thresholds.
  - Tables listing the highest and lowest values.

### Threshold Colours
In the dashboards, colors visually represent air quality levels based on PM10 and PM2.5 concentrations, aligned with WHO guidelines:
- **Green**: Safe levels
  - PM10: 0–20 µg/m³
  - PM2.5: 0–12 µg/m³
- **Yellow/Orange**: Moderate levels, indicating potential health risks for sensitive groups
  - PM10: 20–50 µg/m³
  - PM2.5: 12–35 µg/m³
- **Red**: Unhealthy levels, indicating significant health risks for everyone
  - PM10: 50–100 µg/m³
  - PM2.5: 35–55 µg/m³

## Data Flow

### Data Collection
- **Sensors**: Physical sensors (temperature, humidity, PM2.5, PM10) collect real-time data and send it to a Raspberry Pi.

### Data Processing
- The Raspberry Pi processes the data using a Python script and a REST-based AirQuality API.

### Data Access
- The Air Quality data is retrieved using the GET method.

### Data Integration
- Node-RED integrates the Air Quality API with InfluxDB, fetching and parsing the data.

### Data Storage
- InfluxDB stores the parsed data in buckets for Switzerland and Germany.

### Visualization
- Grafana connects to InfluxDB and visualizes the data using line graphs, bar charts, and gauges, providing insights into pollution trends and enabling users to set alerts for threshold breaches.

## Graphs

The graphs display data in the following ways:
- **X-Axis**: Represents the timeline.
- **Y-Axis**: Represents the concentration of particulate matter (PM10 and PM2.5) in micrograms per cubic meter (µg/m³).
- **Lines**: PM10 and PM2.5 are represented by lines on the graph.
- **Colour Codes**: PM10 is typically represented in green, while PM2.5 is in yellow or orange.

## Key Questions Answered

The dashboards help answer important questions such as:
- What was the highest PM2.5 value in Germany yesterday?
- Is the current PM10 level in Poland within the safe range?
- Show the weekly average PM2.5 values for Switzerland over the last 15 weeks.
- How many times did PM10 levels exceed the unhealthy threshold in the last month?

## Conclusion

This project integrates Node-RED, InfluxDB, and Grafana to provide a scalable and interactive solution for air quality analysis. It offers valuable insights into pollution trends, helping users monitor and understand air quality and its potential impact on health.

## References

- [Air Quality Analysis API Documentation](https://example.com/api-docs)  
- [InfluxDB Documentation](https://docs.influxdata.com/influxdb/)  
- [Grafana Documentation](https://grafana.com/docs/grafana/latest/)
