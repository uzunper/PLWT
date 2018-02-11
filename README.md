# PLWT
If you use the code as a whole or partially please refer to 

"Uzun-Per, M., and Gökmen, M., “Face Recognition with Patch-based Local Walsh Transform”, in Signal Processing:Image Communication, in press."

The code is implemented in Microsoft Visual Studio 2010 C++ and OpenCv 2.4.1 on Windows 7. You may need to change platform specific functions to run the code without bugs.

This code is used for face recognition problem. It runs on the FERET database and use Fa of the FERET as gallery set, Fb, Fc, Dup1 and Dup2 as test sets. In order to run this code for other databases you need to change some parts of the code according to test protocols of the databases. You can also use this code in face verification problem. double is used as variable types. If you use float instead of double it will run faster. 

Installation:

Download "PLWT code.rar" and unzip it. Open the .sln using Microsoft Visual Studio 2010. You need to change the path of the database before run. Change the path of the database for variables called PATH, trainPath, yedekCsvDosyasi in "main.cpp". To obtain the same success rate in the paper you need to use following preprocessed grayscale FERET images. You can reach to the database (the frontalized grayscale FERET database) by the following link:

https://www.dropbox.com/s/t9i4npyfqams0iw/FERET-tif-Frontalized%20no%20symmetry.rar?dl=0

You may change parameters used in the code. The parameters you may change are given below:

* To change the size of Walsh kernel you need to change "kernelsize" and "bitlength" in "Walsh3.h". kernelsize is equal to 2^bitlength. 

* To change the selected LWT complex images for Cascaded LWT operation you need to change row_index2[] and col_index2[] in "Walsh3.cpp". This rows and columns indicate which filters are used to create LWT complex images.

* In "main.cpp" you can change the following parameters. To see the ideal values of these parameters, please read the experiments section of the paper. 

  - patchSize: this indicates the size of patch which are extracted around the selected landmarks.
  
  - gridCellN: this determines the number of the subregions. So, if you want to divide a patch into 5x5 subregions, assign 5 to gridCellN.
  
  - PMhistogramBinCount: this indicates the Phase-Magnitude Histogram bin count. [0, 2pi] angle interval is into PMhistogramBinCount bins. So, if we select PMhistogramBinCountas 8, this means [0, 2pi] angle interval will be divided into 8 bins. [0,45) -> first bin, [45,90) -> second bin, and so on.

  - eigenVectorCount: dimensions of the features of each patch that are reduced to. Value of eigenVectorCount is generally taken as one less than the number of images in the training set. Setting this value greater or equal than to the number of training images causes bug for PCA dimension reduction method.
  
  - selectedLandmarks[]: this array holds the selected landmarks. Values in the array differ according to the landmark detection program. We used SDM or Dlib as landmark detector. The selected landmarks are determined by the tests on the FERET. Refer to article for more information. 
  
  - scales[]: this array holds which scales of images are used in the code. Using more than scales of images is optional. If you use just original scale of the image, scales[] should be {1.0}. 
  
  - numberOfpatches: this is equal to the number of the scales multiplied by number of the selected landmarks. You should set the value of the numberOfpatches according to the number of scales and number of the selected landmarks. 
  
  - apply2ndLWT: if this is set as true, this means that CLWT operation will be applied to the images, otherwise LWT operation will be applied. 
  
  - imageNormalization: this is generally selected as false, because LWT is invariant to illumination changes. 
  
  - searchPattern: this is equal to *.(extension of images)
  
  - landmarkExtension: this is equal to extension of landmark files. 
  
