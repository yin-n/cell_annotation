# cell annotation
cell annotation tool with napari
## Installation
### step 1 install napari
#### create environment
```bash
conda create -y -n annotate -c conda-forge python=3.10
conda activate annotate
```
#### install pip
```bash
conda install pip
```
#### install napari
```bash
python -m pip install "napari[all]"
```
#### try napari
```bash
napari
```
### step 2 clone this github repository
```bash
git clone https://github.com/yin-n/cell_annotation.git
```
### step 3 run blocks in annotation.ipynb


### Clarification for Class in Annotation
- Class 1(sure): Cells that you are very confident are cells.
- Class 2(front/back): Cells that require verification by examining the slide from the front and back to confirm them.
- Class 3(larger view): Cells that require verification by observing a larger view of the entire field of view (768x768) to confirm them.

more details in this google doc:
https://docs.google.com/document/d/1DkMFcapf0n9wRrT6lMXmcIcjaU7D5qLur-UeVthS-wQ/edit


