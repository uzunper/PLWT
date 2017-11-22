# PLWT
If you use the code as a whole or partially please refer to 

"Uzun-Per, M., and Gökmen, M., “Face Recognition with Patch-based Local Walsh Transform”, in Signal Processing:Image Communication, in press."

The code is implemented by C++ on Microsoft Visual Studio 2010 and OpenCv 2.4.1 on Windows 7. You may need to change platform specific functions to run the code without bugs.

The program is used for face recognition problem. This code runs on FERET database and use Fa of the FERET as gallery set, Fb, Fc, Dup1 and Dup2 as test sets. In order to run this code for other databases you need to change some parts of the code according to test protocols of the databases. You can also use this code in face verification problem. 

Installation:
Open the code using Microsoft Visual Studio 2010. You need to change the path of the database before run. Change the path of the database for variables called PATH, trainPath, yedekCsvDosyasi. To obtain the same success rate on the paper you need to use following preprocessed grayscale FERET images. You can reach to the database (the frontalized grayscale FERET database) by the following link:

https://www.dropbox.com/s/t9i4npyfqams0iw/FERET-tif-Frontalized%20no%20symmetry.rar?dl=0

You may change parameters used in the code. The parameters you may change are given below:

* To change the size of Walsh kernel you need to change "kernelsize" and "bitlength" in "Walsh3.h". kernelsize is equal to 2^bitlength. 

* To change the selected LWT complex images for Cascaded LWT operation you need to change row_index2[] and col_index2[] in "Walsh3.cpp". This rows and columns indicate which filters are used to create LWT complex images
