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

## Annotation Workflow
### Step 1: Annotate Class 1 (Cells with High Confidence)
Class 1 consists of cells that can be identified with high certainty without additional information such as forth and back planes data or larger field of view context.
#### Annotation Process for Class 1:
1. Open the green layer (signal channel) and adjust the contrast for optimal visibility. If uncertain about a potential cell, you’re allowed to open the purple layer (reference channel) to verify whether the structure more closely resembles a cell or a non-cell structure. Compare within the 256x256 field of view to finalize your judgment.
2. During this process,It is recommended to first remove all cells from top to bottom, line by line, to minimize omissions. This process should establish a boundary: above it are cells, below it are non-cells, ensuring data consistency
3. Then add any cells missed by the original Cellpose prediction, following the boundary established in 2. It is advised to add these from top to bottom to maintain consistency and avoid omissions.
#### Important Notes:
* Once you proceed to Class 2, no new cell annotations can be added to Class 1.
* Deletions in Class 1 are permitted after reviewing the cells in Class 2 and Class 3 views.

### Step 2: Annotate Class 2 (Cells with forth and back planes)
Class 2 consists of cells that require verification through examination of planes before and after the current one. During this process, you may also remove cells from Class 1 that you determine are not cells or should be annotated in Class 2.
#### Annotation Process for Class 2:
1. After examining cells’ forth and back planes, if you find any misclassified cells in Class 1, return to Class 1 and remove them. Perform this review from top to bottom to ensure no omissions.
2. Similar to Class 1, establish a boundary during annotation. Above this boundary are cells confirmed through forth and back planes observation; below are non-cells. Add cells to Class 2 that you determine to be cells after examining forth and back planes, proceeding line by line from top to bottom.
3. If a cell appears smaller in the current plane compared to others, annotate it smaller.
### Step 3: Annotate Class 3 (Cells with larger view)
Class 3 comprises cells identified as such after viewing a larger field of view (e.g., expanding from 256x256 to 768x768). You may also remove cells from Class 1 or Class 2 that you determine are not cells after viewing this larger context.
#### Annotation Process for Class 3:
1. After examining the larger view, return to Class 2 and Class 1 to remove any cells you now believe are not actually cells.
2. Add cells to Class 3 that you identify as cells in the larger view (768x768).

### Hotkeys for Annotation:
* h: Hide
* q: Quit without saving
* m: New label
* Ctrl + Z: Undo


more details in this google doc:
https://docs.google.com/document/d/1DkMFcapf0n9wRrT6lMXmcIcjaU7D5qLur-UeVthS-wQ/edit


