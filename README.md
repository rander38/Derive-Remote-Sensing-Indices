## Remote Sensing Indices Derivation Tool

Processes stacked raster file to calculate spectral remote sensing indices and export individual bands.

Sensors supported:

* Landsat 1-5 MSS
* Landsat 4-5 TM
* Landsat 7 ETM+
* Landsat 8 OLI
* Worldview-02
* MODIS Terra and Aqua

Indices supported (sensor dependent):
* [NDVI (Normalized Difference Vegetation Index)] (http://www.indexdatabase.de/db/i-single.php?id=58)
* [EVI (Enhanced Vegetation Index] (http://www.indexdatabase.de/search/?s=evi)
* [EVI2 (Enhanced Vegetation Index 2] (http://www.indexdatabase.de/search/?s=evi)
* [NDMI (Normalized Difference Moisture Index)] (http://www.indexdatabase.de/db/i-single.php?id=56)
* [NDSI (Normalized Difference Soil Index)] (http://www.exelisvis.com/portals/0/pdfs/envi/8_bands_Antonio_Wolf.pdf)
* [NDWI (Normalized Difference Water Index)] (http://www.indexdatabase.de/db/i-single.php?id=60)
* [MNDWI (Modified Normalized Difference Water Index)] (http://www.tandfonline.com/doi/abs/10.1080/01431160600589179)
* [SAVI (Soil Adjusted Vegetation Index)] (http://www.indexdatabase.de/db/i-single.php?id=87)
* [MSAVI2 (Modified Soil Adjusted Vegetation Index 2)] (http://www.sciencedirect.com/science/article/pii/0034425794901341)
* [NBR (Normalized Burn Ratio)] (http://www.indexdatabase.de/db/i-single.php?id=53)
* [NMDI (Normalized Multi-band Drought Index)] (http://onlinelibrary.wiley.com/doi/10.1029/2007GL031021/abstract)
* [NHFD (Non-Homogenous Feature Difference (NHFD)] (http://www.exelisvis.com/portals/0/pdfs/envi/8_bands_Antonio_Wolf.pdf)
* [Tasseled Cap Transformation - Brightness, Greenness, Wetness, Yellowness (MSS)] (http://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=1160&context=lars_symp&sei-redir=1&referer=http%3A%2F%2Fscholar.google.com%2Fscholar%3Fhl%3Den%26q%3Dkauth%20and%20thomas#search=%22kauth%20thomas%22)
  * Reflectance required for TM, ETM+, OLI, WV02, and MODIS
  * Digital Number (DN) required for MSS

## Instructions

Requires arcpy and [Tkinter] (https://wiki.python.org/moin/TkInter). 

Run the Python script (RS_Indices_Derivation.py) and use the GUI to select the satellite sensor, indices to calculate, input raster, and output path.

<p align="center">
  <img src="https://github.com/rander38/Remote-Sensing-Indices-Derivation-Tool/blob/master/Documentation/GUI.png" alt="Interface"/>
</p>

**Input raster should be stacked as follows:**

*Landsat 1-5 MSS*

* Blue - Green - Red - NIR


*Landsat 4-5 TM/Landsat 7 ETM+:*

* Blue - Green - Red - NIR - SWIR1 - SWIR2


*Landsat 8 OLI:*

* Coastal - Blue - Green - Red - NIR - SWIR1 - SWIR2 - Cirrus


*MODIS:*

* Red - NIR - Green - Blue - SWIR1 - SWIR2 - SWIR3


*Worldview 02:*

* Coastal - Blue - Green - Yellow - Red - Red Edge - NIR1 - NIR2

### Future Plans

* Additional Sensors/Indices (Requests are welcome)
* Remove arcpy in favor of GDAL
* QGIS/ArcGIS Toolbox

### Works Cited
  Baig, M. H. A., Zhang, L., Shuai, T., & Tong, Q. (2015). Derivation of a tasselled cap transformation 
based on Landsat 8 at-satellite reflectance. Remote Sensing Letters, 5(5), 423–431. doi:10.1080/2150704X.2014.915434

  Crist, E. P. (1985). A TM Tasseled Cap equivalent transformation for reflectance factor data. Remote Sensing of Environment, 17(3), 301–306. doi:10.1016/0034-4257(85)90102-6
  
  Huang, C., Wylie, B., Yang, L., Homer, C., & Zylstra, G. (2002). Derivation of a tasselled cap transformation based on Landsat 7 at-satellite reflectance. International Journal of Remote Sensing, 23(8), 1741–1748. doi:10.1080/01431160110106113

  Huete, A. . (1988). A soil-adjusted vegetation index (SAVI). Remote Sensing of Environment, 25(3), 295–309. doi:10.1016/0034-4257(88)90106-X

  Kauth, R., & Thomas, G. (1976). The tasselled cap--a graphic description of the spectral-temporal development of agricultural crops as seen by Landsat. LARS Symposia.

  Qi, J., Chehbouni, A., Huete, A. R., Kerr, Y. H., & Sorooshian, S. (1994). A modified soil adjusted vegetation index. Remote Sensing of Environment, 48(2), 119–126. doi:10.1016/0034-4257(94)90134

  Roy, D. P., Boschetti, L., & Trigg, S. N. (2006). Remote Sensing of Fire Severity: Assessing the Performance of the Normalized Burn Ratio. IEEE Geoscience and Remote Sensing Letters, 3(1), 112–116. doi:10.1109/LGRS.2005.858485

  Tucker, C. J. (1979). Red and photographic infrared linear combinations for monitoring vegetation. Remote Sensing of Environment, 8(2), 127–150. doi:10.1016/0034-4257(79)90013-0

  Wang, L., & Qu, J. J. (2007). NMDI: A normalized multi-band drought index for monitoring soil and vegetation moisture with satellite remote sensing. Geophysical Research Letters, 34(20), L20405. doi:10.1029/2007GL031021

  Wilson, E. H., & Sader, S. A. (2002). Detection of forest harvest type using multiple dates of Landsat TM imagery. Remote Sensing of Environment, 80(3), 385–396. doi:10.1016/S0034-4257(01)00318-2

  Yarbrough, L. D., Navulur, K., & Ravi, R. (2014). Presentation of the Kauth–Thomas transform for WorldView-2 reflectance data. Remote Sensing Letters, 5(2), 131–138. doi:10.1080/2150704X.2014.885148

  Zhang, X. Z. X., Schaaf, C. B., Friedl, M. a., Strahler, a. H., Gao, F. G. F., & Hodges, J. C. F. (2002). MODIS tasseled cap transformation and its utility. IEEE International Geoscience and Remote Sensing Symposium, 2(C), 1063–1065. doi:10.1109/IGARSS.2002.1025776

### License

The MIT License (MIT)
	
Copyright (c) 2015 Ryan S. Anderson
	
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and to permit persons 
to whom the Software is furnished to do so, subject to the following conditions:
	
1.  You MAY NOT sell any application that you derive from the code in this repository 
without specific written permission from Ryan S. Anderson.
	  
2.  The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
	
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

**Contact: ryananderson57@gmail.com**
