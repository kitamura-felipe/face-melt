# face-melt
Facial de-identification for Head CTs and potentially MRIs

This code is an adaptation from the idea in this [nice paper](https://pubs.rsna.org/doi/10.1148/radiol.2020192617) published in _Radiology_. 

## Instalation

Just git-clone or download this repo.

## Usage

Within the folder where melt.py is, run a python script/Jupyter notebook:


from melt import melt

melt("studies_folder/")


The result will be new DICOM files in a new "melt/" folder.

