# Object-size-measurement
This project developed a system that utilizes the Mask R-CNN model to perform object detection and segmentation using a custom dataset. Images were collected under various conditions, and bounding boxes and segmentation masks were annotated before training the model. Finally, the system was implemented to enable size measurement during model testing.

## Dataset
The COCO dataset was utilized, and a custom dataset was created by labeling with LabelMe.

## Usage
### Train
Just the head. Here I freeze all backbone layers and train only randomly initialized layers (i.e. layers that do not use pre-trained weights from MS COCO). 
To train only the head layer, we passed layer='heads' to the train() function.

### Measurement
Measure the size using the mask created by executing inference. 
I used opencv. Find the contours, find the boundingrect, and then use this to find the height.
