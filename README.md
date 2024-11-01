# Object-size-measurement
This project developed a system that utilizes the Mask R-CNN model to perform object detection and segmentation using a custom dataset. Images were collected under various conditions, and bounding boxes and segmentation masks were annotated before training the model. Finally, the system was implemented to enable size measurement during model testing.

## Mask R-CNN Architecture
![1](https://github.com/user-attachments/assets/c99f1899-7097-44e6-9e9c-6875570274b7)

## Dataset
The COCO dataset was utilized, and a custom dataset was created by labeling with LabelMe.

## Usage
### For Training
Just the head. Here I freeze all backbone layers and train only randomly initialized layers (i.e. layers that do not use pre-trained weights from MS COCO). 
To train only the head layer, we passed layer='heads' to the train() function.

### For Measuring
Measure the size using the mask created by executing inference. 
I used opencv. Find the contours, find the boundingrect, and then use this to find the height.
