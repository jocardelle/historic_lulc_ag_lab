# Digitizing Historic Land Use Maps for Kern County

## About
This repository contains scripts to digitize hand-drawn, georeferenced historical land use maps from Kern County, California. The ultimate goal is to identify lands that were once used for agriculture but have since been retired, and to look at how those areas may have revegetated over time.

The process starts with georeferencing historical maps from 1958, 1969, 1977, and 1984 using a program called Quad-G+. Once the maps are aligned to real-world coordinates, the batching_test.ipynb notebook is used to digitize them. After that the quads are plotted and combined into one shapefile in the plotting.ipynb notebook.

There’s also a folder called excel_map_info. This contains Excel sheets that hold coordinate and metadata info for each map. That info gets used during both Quad-G+ and digitizing to make sure everything’s spatially accurate.

## Data
The historical maps were scanned and georeferenced outside of this repo using Quad-G+. I’m currently working with maps from 1958, 1969, 1977, and 1984. Once georeferenced, the maps get digitized in Python and the output is used for visual inspection and future analysis. The coordinate info for each map is stored in the Excel files in the excel_map_info folder.

 ## Repository Structure
 ```
historic_lulc_ag_lab/
├── batching_test.ipynb       # Main digitizing workflow
├── plotting.ipynb            # Plotting
├── excel_map_info/           # Coordinate and map metadata (excel files)
├── .gitignore                # Files/folders excluded from Git
└── README.md                 

```


## Acknowledgements

