# face-melt
Facial de-identification for Head CTs and potentially MRIs

This code is an adaptation from the idea in this [nice paper](https://pubs.rsna.org/doi/10.1148/radiol.2020192617) published in _Radiology_. 

## Concept

This code implements a series of steps, including optional ones.

1. A binarization is performed to select voxels in the range of air (-150 to -1024 HU).
2. Optional: connected components can be used to remove from the mask the air bubbles in the head (sinuses/mastoid).
3. Optional: mask is smoothed with gaussian filter.
4. Mask is dilated.
5. Mask is applied to the original DICOM as air.
6. Optional: as debbuging, intermediate images can be shown (only if running in jupyter notebooks).
7. Optional: The result is persisted in a new dicom file.

## Instalation

Just git-clone or download this repo.

## Usage

Within the folder where melt.py is, run a python script/Jupyter notebook:


from melt import melt

melt("studies_folder/")


The result will be new DICOM files in a new "melt/" folder.

## Complete list of arguments

folder: folder where the head CT scans are located.

target_folder: name of the new folder where the facial de-identified DICOM will be stored.

sinus_mastoid_intact: option not to dilate the sinus and mastoids.

gaussian_filter: option to apply Gaussian filter in the mask.

kernel: size of the kernel to dilate.

iteration: number of dilation iterations.

