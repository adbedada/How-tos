**Mosaicking**
 
*gdal_merge: Output file path/name, input file path/name, Compression, file type(size)*
 
	 gdal_merge -o Sri_Lanka_2017_mosaic.tif Sl1.tif Sl2.tif Sl3.tif Sl4.tif Sl5.tif Sl6.tif Sl7.tif Sl8.tif -co COMPRESS=LZW -co BIGTIFF=YES

**Changing the order of Bands**

*gdal_translate Input file name, output file name, Compression type, file type(size)*

	gdal_translate -o Sri_Lanka_2017_Mosaic.tif Sri_Lanka_2017_Mosaic_V2.tif -co COMPRESS=LZW BIGTIFF=YES

**Create vrt file**

*gdalbuildvrt [vrt_file_name, input folder path/images]*

	gdalbuildvrt PAN_1_384.vrt Sri_Lanka_2017_Mosaic_V2_PAN_1_384\*.tif

**Convert VRT to TIFF**

*gdal_translate [data type, tiled, input vrt_file, output tiff file]*

	gdal_translate -of GTiff -co “TILED=YES” H:\Colonial_One\Sri_Lanka_subs\PAN_1_384.vrt H:\Colonial_One\Sri_Lanka_subs\PAN_1_384.tif

**Create Shapefile Mask**

*gdaltindex: [shapefile_name, tiff_name]*

	gdaltindex H:\Colonial_One\Sri_Lanka_subs\PAN_1_384.shp H:\Colonial_One\Sri_Lanka_subs\PAN_1_384.tif

**Clip Raster with a shape file mask**

*gdalwarp: [shape file name, image to clip from, name of output]*

	Script: gdalwarp H:\Colonial_One\Sri_Lanka_subs\PAN_1_384.shp H:\Colonial_One\Sri_Lanka_2017_Mosaic_V2.tif H:\Colonial_One\Sri_Lanka_subs\Sri_Lanka_Clip_1_1_384.tif -co COMPRESS=LZW

