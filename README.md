# 3DKneeNet
This repository contains the code for training and infering the TL net based CNN for 3D reconstruction of objects. 



## Overview
3DKneeNet is a latent embedding matching approach for 3D point cloud reconstruction from a single image. To better incorporate the data prior and generate meaningful reconstructions, we first train a 3D point cloud auto-encoder and then learn a mapping from the 2D image to the corresponding learnt embedding. For a given image, there may exist multiple plausible 3D reconstructions depending on the object view. To tackle the issue of uncertainty in the reconstruction, we predict multiple reconstructions that are consistent with the input view, by learning a probablistic latent space using a view-specific ‘diversity loss’. We show that learning a good latent space of 3D objects is essential for the task of single-view 3D reconstruction.


## Dataset

### ShapeNet
We train and validate our model on the ShapeNet dataset. We use the rendered images from the dataset provided by <a href="https://github.com/chrischoy/3D-R2N2" target="_blank" >3d-r2n2</a>, which consists of 13 object categories. For generating the ground truth point clouds, we sample points on the corresponding object meshes from ShapeNet. We use the dataset split provided by r2n2 in all the experiments. Data download links are provided below:<br>
Rendered Images (~12.3 GB): http://cvgl.stanford.edu/data2/ShapeNetRendering.tgz <br>
ShapeNet pointclouds (~2.8 GB): https://drive.google.com/open?id=1cfoe521iTgcB_7-g_98GYAqO553W8Y0g <br>
ShapeNet train/val split: https://drive.google.com/open?id=10FR-2Lbn55POB1y47MJ12euvobi6mgtc

Download each of the folders, extract them and move them into *data/shapenet/*.<br>
The folder structure should now look like this:<br>
--data/shapenet/<br>
&nbsp;&nbsp;--ShapeNetRendering/<br>
&nbsp;&nbsp;--ShapeNet_pointclouds/<br>
&nbsp;&nbsp;--splits/<br>

### Pix3D
We evaluate the generalization capability of our model by testing it on the real-world <a href="https://github.com/xingyuansun/pix3d">pix3d dataset</a>. For the ground truth point clouds, we sample 1024 points on the provided meshes. Data download links are provided below:<br>
Pix3D dataset (~20 GB): Follow the instructions in https://github.com/xingyuansun/pix3d <br>
Pix3D pointclouds (~13 MB): https://drive.google.com/open?id=1RZakyBu9lPbG85SyconBn4sR8r2faInV

Download each of the folders, extract them and move them into *data/pix3d/*.<br>
The folder structure should now look like this:<br>
--data/pix3d/<br>
&nbsp;&nbsp;--img_cleaned_input/<br>
&nbsp;&nbsp;--img/<br>
&nbsp;&nbsp;--mask/<br>
&nbsp;&nbsp;--model/<br>
&nbsp;&nbsp;--pix3d_pointclouds/<br>
&nbsp;&nbsp;--pix3d.json<br>
