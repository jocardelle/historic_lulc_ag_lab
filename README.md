# Digitizing Historic Land Use Maps for Kern County

<img width="639" alt="Screenshot 2025-06-07 at 4 18 53 PM" src="https://github.com/user-attachments/assets/f5c10ea6-af01-44f2-b343-cce9fd70e0d5" />


## About
This repository contains scripts to digitize hand-drawn, georeferenced historical land use maps from Kern County, California. The maps are from the California Department of Water Resources (DWR). The ultimate goal is to identify lands that were once used for agriculture but have since been retired, and analyze how those areas may have revegetated over time.
The digitization process involves several steps:
1. Georeferencing: Historical maps from 1958, 1969, 1977, and 1984 are georeferenced using Quad-G+ to align them with real-world coordinates
2. Digitization: The `batching_test.ipynb` notebook processes the georeferenced maps
3. Processing: The `plotting.ipynb` notebook combines individual quads into a single shapefile for analysis and visualization

The `excel_map_info` folder contains Excel sheets with coordinate and metadata information for each map, which is used during both georeferencing and digitization to ensure spatial accuracy.

## Data

This repository uses hand-drawn land use maps from the California Department of Water Resources (DWR) for the years 1958, 1969, 1977, and 1984. More information about these mapping efforts can be found in this [ArcGIS StoryMap](https://storymaps.arcgis.com/stories/3c2a4a5a9fe24f3daaf415451ce4eae1).
The historical maps were scanned and georeferenced outside of this repository using Quad-G+. Once georeferenced, the maps are digitized in Python and the output is used for visual inspection and future analysis. Coordinate information for each map quad is stored in Excel files within the `excel_map_info` folder.


 ## Repository Structure
 ```
historic_lulc_ag_lab/
├── batching_test.ipynb       # Main digitizing workflow
├── plotting.ipynb            # Plotting
├── excel_map_info/           # Coordinate and map metadata (excel files)
├── .gitignore                # Files/folders excluded from Git
└── README.md                 

```

## Prerequisites
Before using this repository, the original hand-drawn maps must be georeferenced using Quad-G+. Both the application and detailed documentation can be found at this [UW-Madison Box folder](https://uwmadison.app.box.com/s/tkccw1j5u3ensn2e10hrl1eiek78z9r6/folder/145924177108).

## Georeferencing with Quad-G+

### Setup Requirements
To use Quad-G+, you need CSV files containing information about each individual quad. These CSV files are located in the excel_map_info folder of this repository. Below is an example of the required file structure:

<img width="846" alt="Screenshot 2025-06-07 at 3 45 10 PM" src="https://github.com/user-attachments/assets/3eea344a-7550-42d6-b220-5db1b6100278" />

### Quad-G+ Configuration
#### Preferences Settings
Use the following settings under the Preferences tab:

<img width="672" alt="Screenshot 2025-06-07 at 4 00 08 PM" src="https://github.com/user-attachments/assets/1d56ba9c-e699-4b15-b67e-727406dc22e4" />

#### Output Setup
Customize the Output Setup tab to your desired file locations. The settings used for this project are shown below:

<img width="499" alt="Screenshot 2025-06-07 at 3 58 39 PM" src="https://github.com/user-attachments/assets/b725540e-82b9-4e85-8034-f5786138c77f" />

#### Important settings
- Set GCP Text Info (bottom right) to CSV
- Mode can be set to either automatic or manual
- For this project, automatic mode was used first, with manual troubleshooting as needed

#### Running the Georeferencing Process
1. Upload the CSV file: **File > Open Batch File**
2. Start georeferencing by clicking:
   - "Run Batch" (automatic mode)
   - "Find Corners" (manual mode)
4. Output GeoTIFF files will be saved to the folder specified in Output Setup

## Usage
1. Ensure historical maps are georeferenced using Quad-G+ (see above)
2. Run `batching_test.ipynb` to digitize the georeferenced maps
3. Use `plotting.ipynb` to visualize and combine individual quad shapefiles into a single shapefile
4. Reference Excel files in excel_map_info/ for coordinate and metadata information on maps

## Acknowledgements

Thank you to Dr. Ashley Larsen for bringing me onto this project.
