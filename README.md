# Athens Heat Risk Index
An interactive map illustrating the intensity of heat across various areas in Athens, Greece. Designed to aid in implementing preventative measures for cooling the city and enhancing its resilience.

<img alt = "Heat Map GIF" img src="./Athens Heat Risk Index_EmekaEmeche (3).gif"/>

## How It's Made:

**Tech used:** ArcGIS Pro, ArcGIS Online, ArcGIS Living Atlas of the World, ArcGIS Spatial Analyst extension

The project began with obtaining land surface temperature data using a Multispectral Landsat imagery layer from the ArcGIS Living Atlas. I focused on Athens, Greece, zooming into the GRC_Postcodes3 layer, and filtered out postcodes that could skew the data. Using the Copy Features tool, I created a new layer named Athens_Postcodes with only the relevant data.

Creating a Heat Risk Index (HRI) involved three main steps. First, I assessed the land surface temperature. The Multispectral Landsat layer, which contains decades of thermal data, was configured to display Band 10 Surface Temperature in Celsius using the Processing Templates tab. To ensure accuracy, I set the Mosaic tab's operator to 'Mean' and applied a Definition Query to exclude images with more than 5% cloud cover. I customized the Symbology layer, using dark purple for cooler areas and orange/yellow for hotter ones. The study area was defined by the Athens_Postcodes layer. I used the Copy Raster tool to create a new Athens temperature layer and summarized the values using the Zonal Statistics As Table tool, generating a table of high surface temperatures by postcode.

The second step involved analyzing tree canopy coverage. I added the European Space Agency WorldCover 2020 Land Cover layer, which identifies areas with at least 10% tree cover. I used the Raster Functions tool to isolate and group these cells, creating a new layer that mapped tree coverage across Athens. I calculated the tree canopy percentage using the Calculate Field tool, reflecting areas with and without sufficient tree cover.

The third step was to calculate population density. I added a new column for population density in the Athens_Postcodes layer and combined the three input variables—land surface temperature, tree canopy coverage, and population density—using the Join Field tool. I standardized the data with the Standardized Field tool, ensuring consistent measurement types across all variables. Finally, I visualized the Heat Risk Index map with the Expression Builder tool using Arcade code, symbolizing Athens based on the sum of the HRI values. Adjusting transparency helped to emphasize heat effects. The map was then published on ArcGIS Online, making it available for public viewing and engagement. This project taught me the importance of data accuracy, methodological rigor, and clear communication when addressing complex environmental issues.

## Lessons Learned:

The key takeaway from this project was the invaluable experience of utilizing ArcGIS Living Atlas. This resource offers a vast array of data, from thermal imagery to other types of visualization data, enabling effective storytelling through clean, filtered presentations. I vividly remember thinking, "Wow, I'm really working with extensive land surface temperature data and refining it into manageable sizes." This realization was exhilarating, as it showcased how I can apply my skills to tackle significant issues like this.

I also learned the importance of meticulously filtering data and converting it into specific formats to enhance interactivity and usability. This project underscored how time-consuming the process can be, which encouraged me to take my time and be intentional with every action. This careful, deliberate approach ensures accuracy and effectiveness in my work.

## Examples:
Take a look at these couple examples that I have in my own portfolio:

**Coral Reef Dashboard:** [Coral Reef Dashboard](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action/Coral-Reef-Dashboard)

**Sumner Boundary Map:** [Sumner Boundary Map](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/Furtado-and-Associates-Projects/Sumner%20Boundary%20Map)

**Climate Change Report:** [Climate Change Report](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/Climate-Change/project-report-saejinm)

## Repositories
**Profile:** https://github.com/T3ch12et

**GIS Climate Action Repository:** [ESRI MOOC GIS for Climate Action](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action)

**Main Repository:** https://github.com/T3ch12et/GIS-Data-Science-Portfolio
