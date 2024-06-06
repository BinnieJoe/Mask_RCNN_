# Object-size-measurement

## Dataset
    I used cocodataset and created a custom dataset by labeling with labelme.

## Train
    Just the head. Here I freeze all backbone layers and train only randomly initialized layers (i.e. layers that do not use pre-trained weights from MS COCO). 
    To train only the head layer, we passed layer='heads' to the train() function.

## Measurement
    Measure the size using the mask created by executing inference. 
    I used opencv. Find the contours, find the boundingrect, and then use this to find the height.
