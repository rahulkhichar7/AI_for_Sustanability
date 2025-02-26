Solar Panels in Satellite Imagery: Object Labels
________________________________________________


The folders in labels.zip contain labels for solar panel objects as part of the Solar Panels in Satellite Imagery dataset. 

The labels are partitioned based on corresponding image type: 31 cm native and 15.5 cm HD resolution imagery. 
In total, there are 2,542 object labels for each image type, following the same naming convention as the corresponding image chips. 
The corresponding image chips may be accessed at: 

https://resources.maxar.com/product-samples/15-cm-hd-and-30-cm-view-ready-solar-panels-germany

The naming convention for all labels includes the name of the dataset, image type, tile identification number, minimum x bound, minimum y bound, and window size. 
The minimum bounds correspond to the origin of the chip in the full tile. An example label would be "solarpanels_hd_1__x0_0_y0_14027_dxdy_832.txt," 
which is a label from HD Tile 1 in the solar panel dataset, with a minimum x bound of 0, minimum y bound of 14,207 and window size of 832 by 832 pixels. 
The corresponding image chip for this example would be "solarpanels_hd_1__x0_0_y0_14027_dxdy_832.tif."    

Labels are provided in .txt format compatible with the YOLTv4 architecture (https://github.com/avanetten/yoltv4), 
where a single row in a label file contains the following information for one solar panel object: category, x-center, y-center, x-width, and y-width.  
Center and width values are normalized by chip sizes (416 by 416 pixels for native chips and 832 by 832 pixels for HD chips).
Each row in a label file corresponds to one object in the corresponding image chip. A single label file contains all of the object labels in the corresponding image chip.

The geocoordinates for each solar panel object may be determined using the native resolution labels (found in the labels_native directory). 
The center and width values for each object, along with the relative location information provided by the naming convention for each label, 
may be used to determine the pixel coordinates for each object in the full, corresponding native resolution tile. 
The pixel coordinates may be translated to geocoordinates using the EPSG:32633 coordinate system and the following geotransform for each tile:

Tile 1: (307670.04, 0.31, 0.0, 5434427.100000001, 0.0, -0.31)
Tile 2: (312749.07999999996, 0.31, 0.0, 5403952.860000001, 0.0, -0.31)
Tile 3: (312749.07999999996, 0.31, 0.0, 5363320.540000001, 0.0, -0.31)

________________________________________________

If using these labels, please cite as:
Clark, C. N. (2023). Solar Panels in Satellite Imagery: Object Labels. figshare. http://doi.org/10.6084/m9.figshare.22081091