## Deep Learning (with Prince Lawson, Svenja Dobelmann: https://github.com/SvenjaDo)

### Title : Deep Learning For Tree Crown Detection.

### Objective :  Detecting tree crowns from very high resolution RGB Drone Imagery using a Keras Deep Learning model.
### Description :
The final model (model_tree_crowns.hdf5) is trained with RGB Data with 10 cm resolution from the University Forest of Julius-Maximilians University Würzburg. We used tree crown shapes derived from LiDAR to generate training data (create_training_data.ipynb). 
A simple U-net model architecture is imported and trained with our data (modelling_commented.ipynb). 

### Overview: 

example data: (All uploaded in shared google drive)
 - WingtraUniwald.tiff ->  UAV generated RGB Image to be predicted 
 - treeCrowns1.shp -> LiDAR derived tree crown shapes, used to generate training masks 
 - training_img_256 -> pre-processed RGB training tiles  
 - training_mask_256 -> pre-processed tree crown mask tiles 
 
scripts: 
 - create_training_data.ipynb -> script to generate training data 
 - unet_model.py -> simple Unet model architecture. Will be imported into model.py
 - modelling_commented.ipynb  -> script for building, compiling and running the model 
 - model_tree_crowns.hdf5 -> final model that is trained with our example data


TO USE: 

1. Run create_training_data.ipynb script to generate image tiles from the RGB Tiff and mask tiles from the Lidar tree crown shape file. Please save these two files (WingtraUniwald.tiff, treecrowns1.shp) in the same directory where ipynb files are stored. Four directories (training_img_256, training_img, mask_img, mask_256_img) are also uploaded in google drive. If you run the create_training_data.ipynb script, four directories will be created by the script and the output will be identical with them, so you do not have to download all these directories. 
2. Run the model.py script. Do not forget to add the directory of your training data (Default is the example data) in the same directory where you saved the script. Optionally adjust tuning parameters. 

Alternatively the model_tree_crowns.hdf5 can be used directly to predict new data.

Last Updated: 22/09/2022
