# cell annotation
cell annotation tool with napari
## Installation
### step1 install napari
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
### step2 clone this github repository
```bash
git clone https://github.com/yin-n/cell_annotation.git
```
### clarification for class in annotation
- Class 1(sure): the cell you are very sure it's a cell
- Class 2(front_back): the cell you are not very sure, and need to verify through slide front and back
- Class 3(large_view): the cell you are not very sure, and need to verify through larger view in the whole field of view(768x768)

more details in this google doc:
https://docs.google.com/document/d/1DkMFcapf0n9wRrT6lMXmcIcjaU7D5qLur-UeVthS-wQ/edit


