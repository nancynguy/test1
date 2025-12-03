# Seattle Ferry Traffic Animation Map of Puget Sound

## Project Description
Our project is an interactive web GIS application that visualizes ferry traffic in the Port of Seattle and across the central Puget Sound region. The map combines a custom-designed Mapbox basemap with ferry route data and time-based vessel information obtained from the Washington State Department of Transportation (WSDOT). We designed the application to be lightweight, visually engaging, and easy to navigate, allowing users to observe how ferries travel throughout Puget Sound and how traffic patterns change over time.

The ferry system is an essential part of daily life in Washington State, especially around Seattle, Bainbridge Island, and the surrounding islands. While ferry schedules and ridership statistics are widely available online, our project provides a spatial and animated representation of actual vessel movement. This allows users to view intensity, directionality, and changes in ferry activity by day or by hour in a way that is more intuitive than static text or tables.

## Project Goal
The primary goal of this project is to use real-time and scheduled ferry data provided by WSDOT to create an accurate visual representation and animation of how the ferry system operates in the Puget Sound area. We aim to show one of the many ways people travel around the region, how frequently these systems are used, and how extensive and interconnected the ferry network is. Our application highlights these dynamics through interactive movement, terminal selection, and live-updating vessel information.

## Application URL
https://christiankaylanuw.github.io/flow_map_g328/

## Favicon
Our custom favicon is a simplified version of our ferry icon. It is used across all pages of the application.

![Favicon](imgs/mini_ferry_cutout.png)

---

## Screenshots  
(Insert screenshots of each tab here once exported to your assets folder.)

---

## Main Functions
- Custom dark-marine Mapbox basemap designed specifically for Puget Sound.
- A legend showing ferry terminals, ferry routes, and ferry vessels.
- Custom SVG ferry icon used both as the favicon and for vessel markers.
- Toggle between real-time vessel locations and simulated vessel movement.
- Dropdown menu for selecting ferry terminals and zooming into them.
- Updated schedule and departure information for selected terminals.
- Refresh functionality that updates vessel locations using the most recent data.
- Interactive map navigation through mouse and trackpad controls.
- **animateParticles():** Animates the simulated movement of ferries along travel paths.
- **loadFerryData():** Fetches API data and generates a GeoJSON object containing ferry locations and attributes including active status and associated terminals.
- **handleFerryData():** Loads and reloads real-time ferry location data by replacing old JSON data with new API responses and updating HTML as needed.
- **updateMap():** Loads ferry and terminal layers depending on which dataset (vessels or terminals) is selected.
- **handleTerminalData():** Creates GeoJSON objects for each terminal, populates the terminal dropdown list, and triggers the schedule loading process.
- **loadTerminalData():** Fetches and updates terminal schedule information from the WSDOT terminal API.
- **parseMSDate():** Reformats date values from the API into valid JavaScript Date objects.
- **updateTerminalInfo():** Builds and displays the daily schedule for a selected terminal in the sidebar.

---

## Data Sources

### **Ferry Routes in Seattle**  
https://geo.wa.gov/datasets/WSDOT::wsdot-ferry-routes/explore?location=47.590612%2C-122.422831%2C11.79  
**Description:**  
This dataset provides the spatial geometry of Washington State public car ferry routes, along with some tribal, private, and provincial services. Each route is represented as a line feature with attributes such as operator, State Route number, and route name. It is intended for mapping and reference purposes.

---

### **Ferry Terminals & Routes (REST Service)**  
https://data.wsdot.wa.gov/arcgis/rest/services/Shared/FerryRoutes/MapServer  
**Description:**  
This feature layer portrays scheduled car-ferry routes and known tribal, provincial, private, and passenger-only services. Each line feature includes attributes like operator (“Owner”), route number (“SR”), and a display label identifying connected terminals. Designed for GIS reference, the layer supports queries in formats including JSON and GeoJSON.

---

### **WSDOT Ferry Schedule API**  
https://www.wsdot.wa.gov/ferries/api/schedule/documentation/rest.html  
**Description:**  
This API returns real-time and scheduled sailing information including upcoming departures, route schedules, direction, valid schedule ranges, and alerts or service adjustments. It is intended for developers handling live ferry operations data. Access requires an API key from WSDOT.

---

### **Custom Mapbox Basemap**  
[https://api.mapbox.com/styles/v1/nancy324/cmhxwciko001u01sq7rf76i37.html](https://api.mapbox.com/styles/v1/nancy324/cmhxwciko001u01sq7rf76i37.html?title=view&access_token=pk.eyJ1IjoibmFuY3kzMjQiLCJhIjoiY21oMTEyejlmMDY1YzJycHVwYXVyZ2U1ZiJ9.YSOrhRs2Nuc7-00ALC3Q_w&zoomwheel=true&fresh=true#10.16/47.5851/-122.4341)  
**Description:**  
This is the custom basemap used in our web application. The map features a dark-mode, ferry-focused design for visualizing Puget Sound ferry routes. It includes simplified land and water layers, highlighted coastlines, custom city labels, and an imported SVG ferry icon used to display animated ferry movement.

---

## Applied Libraries and Web Services

### **Mapbox GL JS**  
https://docs.mapbox.com/mapbox-gl-js/guides/  
Used to render the interactive map, display layers, apply the custom style, animate vessel movement, and handle all GeoJSON rendering.

### **Mapbox Studio**  
Used to design the custom dark-marine basemap and upload the custom ferry icon.

### **GitHub & GitHub Pages**  
GitHub serves as the version control platform and project repository. GitHub Pages hosts the web application publicly, allowing the project URL to load the website directly from the repository’s main branch.

---

## Acknowledgments
This project was created by **Nancy Nguyen**, **Mohaned Abdullatef Ibrahim**, **Christian Alviz**, **Will Senenko**, and **Micah Santos**, with guidance from **Dr. Bo Zhao** and **Hudson Dougan**.  
Data for the project was drawn from WSDOT’s open ferry terminal and route datasets, their ferry schedule API, and WSDOT’s ArcGIS REST Service Directory.

---

## AI Use Disclosure
- ChatGPT was used to debug the Mapbox basemap when a layer was not loading correctly.  
- ChatGPT generated the custom SVG ferry icon used for the moving markers and favicon.  
- ChatGPT was referenced to create a structural skeleton for the `about.html` page; however, all written content was original.  
- ChatGPT helped with organizing, formatting, and polishing the README structure.
