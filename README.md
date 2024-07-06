# Athens Heat Risk Index
An interactive map illustrating the intensity of heat across various areas in Athens, Greece. Designed to aid in implementing preventative measures for cooling the city and enhancing its resilience.

<img alt = "Heat Map GIF" img src="./Athens Heat Risk Index_EmekaEmeche (3).gif"/>

## How It's Made:

**Tech used:** ArcGIS Pro, ArcGIS Online, ArcGIS Living Atlas of the World, ArcGIS Spatial Analyst extension

The first step was to obtain the land surface temperature using a Multispectral Landsat imagery layer from ArcGIS Living Atlas. I set the study area to Athens, Greece, zoomed into the GRC_Postcodes3 layer, accessed the attributes layer, filtered out postcodes that could skew the data, and removed them accordingly. Using the Copy Features tool, I created a new layer called Athens_Postcodes with the remaining postcodes.

Creating a Heat Risk Index involves three steps. The first step is assessing land surface temperature. The Multispectral Landsat layer, containing decades of thermal energy data, was adjusted to display Band 10 Surface Temperature in Celsius via the Processing Templates tab. I set the Mosaic tab's operator to 'Mean' and applied a Definition Query to filter out images with cloud cover greater than 5% (_Where Cloud Cover is less than or equal to 0.05_). This ensured accuracy by excluding cloud and shadow interference. I then customized the Symbology layer, using dark purple for cooler areas and orange/yellow for hotter areas. To define the study area, I filtered by the extent of the Athens_Postcodes layer, used the Copy Raster tool to create a new layer for Athens, and summarized temperature values with the Zonal Statistics As Table tool to generate a table of High Surface Temperature by Postcodes.

The second step involves tree canopy coverage. I added the European Space Agency WorldCover 2020 Land Cover layer from ArcGIS Living Atlas, which shows geographic areas with 10% or more tree cover. Using the Raster Functions tool, I isolated and grouped cells, assigning and remapping them to create a new layer. I calculated tree canopy coverage, set the study area's boundaries, and used the Copy Raster and Zonal Statistics As Table tools to create a new raster layer and table, counting tree cover cells in each postcode region. I then calculated the tree canopy percentage using the Calculate Field tool, creating a new field in the table to reflect the percentage of tree canopy present and the percentage lacking.

The third step is calculating population density. I added a new column for population density in the Athens_Postcodes layer. I then combined the three input variables—land surface temperature, tree canopy coverage, and population density—using the Join Field tool. The Standardized Field tool was used to ensure all input variables had consistent measurement types. Finally, I visualized the heat map using the Expression Builder tool with Arcade code, symbolizing the map of Athens based on the sum of the HRI values for each input variable. I adjusted transparency to emphasize heat effects and published the map on ArcGIS Online for public viewing.

## Lessons Learned:

The key takeaway from this project was the invaluable experience of utilizing ArcGIS Living Atlas. This resource offers a vast array of data, from thermal imagery to other types of visualization data, enabling effective storytelling through clean, filtered presentations. I vividly remember thinking, "Wow, I'm really working with extensive land surface temperature data and refining it into manageable sizes." This realization was exhilarating, as it showcased how I can apply my skills to tackle significant issues like this.

I also learned the importance of meticulously filtering data and converting it into specific formats to enhance interactivity and usability. This project underscored how time-consuming the process can be, which encouraged me to take my time and be intentional with every action. This careful, deliberate approach ensures accuracy and effectiveness in my work.

## Repositories
**Profile:** [T3ch12et](https://github.com/T3ch12et) <br>
**GIS Climate Action Repository:** [ESRI MOOC GIS for Climate Action](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action) <br>
**Main Repository:** [GIS Data Science Portfolio](https://github.com/T3ch12et/GIS-Data-Science-Portfolio)

## Examples:
Take a look at these couple examples that I have in my own portfolio:

**Miami Sea Level Rise:** [3D Miami Beach Sea Level Rise](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action/3D-Miami-Beach-Sea-Level-Rise) <br>
**Oso Mudslide:** [Oso Mudslide](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-Cartography/Oso-Mudslide) <br>
**Hurricanes since 1851:** [Hurricanes since 1851](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-Cartography/Hurricanes-since-1851) <br>
**Coral Reef Dashboard:** [Coral Reef Dashboard](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action/Coral-Reef-Dashboard) <br>
**Rondonia Land Cover Change:** [Rondonia Land Cover Change from 1992 to 2020](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/tree/main/ESRI-MOOC-GIS-for-Climate-Action/Rondonia-Land-Cover-Change) <br>
**Addressing Climate Change:** [Using GIS to address climate change](https://github.com/T3ch12et/GIS-Data-Science-Portfolio/blob/main/ESRI-MOOC-GIS-for-Climate-Action/Addressing-Climate-Change/README.md)
