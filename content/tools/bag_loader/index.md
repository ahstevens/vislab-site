---
title: "BAG Loader Unity Plugin"
weight: 30
img: BAGThumb.png
---

The BAG Loader Unity plugin, developed by PhD student [Kindrat Beregovyi](/people/kindrat_beregovyi), makes it easy to load georeferenced bathymetry files directly into the Unity engine for use in simulations, virtual reality experiences, and other interactive projects.  It uses the GDAL library, and supports the common .bag (Bathymetric Attributed Grid) file format, as provided from NOAA’s online bathymetric data repositories (e.g. NOAA's [Bathymetric Data Viewer](https://www.ncei.noaa.gov/maps/bathymetry/)), including multi-resolution bag files.

**Download the [BAG Loader Plugin for Unity](/downloads/BAGLoader_20211116.unitypackage)** *(November 16, 2021)*

It is released for general use under the [BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause).

{{< webgl dir="bagloader" name="buildweb2" >}}
_Click and drag the mouse or use the WASD keys to move the view_

### Instructions:

{{< video src="bagloader">}}
_How to use the BAG Loader plugin for Unity_

* Download the plugin file: **[BAGLoader.unitypackage](BAGLoader_20211116.unitypackage)**
* Load the plugin into your Unity project by going to Assets -> Import Package -> Custom Package, and then selecting the BAGLoader.unitypackage file you downloaded.
* Click the “All” button, then the “Import” button.
* There should now be a “Hydrographic Toolkit” option available on your menu bar.  Here you can select the “BAG Loader” tool.  
* In the popup window, click “Import BAG file” and select the .bag file you wish to open.
* A visual preview and information about the file’s content (size/resolution, coordinate system, etc.) will be displayed.
  * Select the desired output resolution for the Unity terrain object to be created.
  * Unity’s terrain engine only supports power-of-two sizes, and we suggest picking the next size up from your file’s original resolution, though smaller resolutions can be chosen to speed up rendering and reduce the file size of the application.
* Click the “Create Terrain from current BAG file” button, and a new bathymetric terrain object will appear in your project.
* Selecting a bathymetric terrain object gives you access to visualization settings in the Inspector panel.  Here you can hide or show areas with no data, switch between different color maps, and add and adjust contour lines.
  * Color maps include a simple two color map, smooth and stepped rainbows, and a draft dependent go/no-go/warning scheme useful for precision navigation visualizations.
  * The upper “no-go” depth and the lower “warning” depth can be set via these boxes, or by script (e.g. if you have dynamic tidal heights).  
  * **Note**: if you adjust the scale/height of the terrain, and the color map is affected, you can reset the color map min/max values by re-selecting the color map type.
* For large multi-resolution BAG files, there is an option to “Select an Area with Full Resolution”. 
  * Checking this box lets you select a region-of-interest that will be output as a terrain object with all data within interpolated to the highest resolution available in that region.
  * The region-of-interest cropping values can be interactively adjusted with the mouse by clicking and dragging left/right over the “area.left in %” and “area.top in %” text labels.

### Contact

We hope you find our tool useful for creating interactive experiences with real bathymetric data. NOAA employees and CCOM industrial partners are encouraged to reach out to us with their particular applications that require support or modifications.  Other uses are welcome to contact us with bug reports and feature requests as well.  You can email the developer, Kindrat Beregovyi at kberegovyi@ccom.unh.edu or the lab director Thomas Butkiewicz at tbutkiewicz@ccom.unh.edu.