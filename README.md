# 3DKneeNet
This repository contains the code for training and infering the TL net based CNN for 3D reconstruction of objects. 



## Overview
3DKneeNet is a latent embedding matching approach for 3D point cloud reconstruction from a single image. To better incorporate the data prior and generate meaningful reconstructions, we first train a 3D point cloud auto-encoder and then learn a mapping from the 2D image to the corresponding learnt embedding. For a given image, there may exist multiple plausible 3D reconstructions depending on the object view. To tackle the issue of uncertainty in the reconstruction, we predict multiple reconstructions that are consistent with the input view, by learning a probablistic latent space using a view-specific ‘diversity loss’. We show that learning a good latent space of 3D objects is essential for the task of single-view 3D reconstruction.


## Dataset
