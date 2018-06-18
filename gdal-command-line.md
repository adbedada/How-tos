**Mosaicking**
 
*gdal_merge: Output file path/name, input file path/name, Compression, file type(size)*
 
	 gdal_merge -o Sri_Lanka_2017_mosaic.tif Sl1.tif Sl2.tif Sl3.tif -co COMPRESS=LZW -co BIGTIFF=YES

**Changing the order of Bands**

*gdal_translate Input file name, output file name, Compression type, file type(size)*

	gdal_translate -o Sri_Lanka_2017_Mosaic.tif Sri_Lanka_2017_Mosaic_V2.tif -co COMPRESS=LZW BIGTIFF=YES

**Create vrt file**

*gdalbuildvrt [vrt_file_name, input folder path/images]*

	gdalbuildvrt PAN_1_384.vrt Sri_Lanka_2017_Mosaic_V2_PAN_1_384\*.tif

**Convert VRT to TIFF**

*gdal_translate [data type, tiled, input vrt_file, output tiff file]*

	gdal_translate -of GTiff -co “TILED=YES” PAN_1_384.vrt PAN_1_384.tif

**Create Shapefile Mask**

*gdaltindex: [shapefile_name, tiff_name]*

	gdaltindex PAN_1_384.shp PAN_1_384.tif

**Clip Raster with a shape file mask**

*gdalwarp: [shape file name, image to clip from, name of output]*

	gdalwarp -cutline my_shapefile.shp -crop_to_cutline mytif_2018.tif mytif_2018_1.tif -co COMPRESS=LZW

**Change the scale of image to 0-255**

*gdal_translate:[Type of image, type of output, input scale, output scale, input data, output data]*

	 gdal_translate -of GTiff -ot Byte -scale 0 1 0 255 input_image.tif output_image.tif 

**Convert greyscale image to RGBA**

Create custom color palette like the on below and save the file as .txt file. 

       0.  255 255 255 0
       50. 255  0   0  50
       100. 0  255  0  100
       150. 0   0  255 150

*gdaldem:[ function, type of data, input data, color palette, output data]*

	gdaldem color-relief -of GTiff current_vacc_final_3.tif color.txt current_vacc_final_4.tif -alpha
