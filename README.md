# Matlab-Annotations-to-Yolov4-Annotations

The car dataset is available in this link: https://ai.stanford.edu/~jkrause/cars/car_dataset.html

The annotations are in .mat format (Matlab Matrix) which is not accepted by Yolov4 Darknet.

Moreover, the annotations for a image is available in the following format:

    bbox_x1: Min x-value of the bounding box, in pixels
    bbox_x2: Max x-value of the bounding box, in pixels
    bbox_y1: Min y-value of the bounding box, in pixels
    bbox_y2: Max y-value of the bounding box, in pixels
    class: Integral id of the class the image belongs to.
    fname: Filename of the image within the folder of images.

However, Yolov4 Darknet implementtion requires all the annotations in the following format:

object-class x_center y_center width height
    
  Where:

    object-class - integer object number from 0 to (classes-1)
    x_center y_center width height - float values relative to width and height of image, it can be equal from (0.0 to 1.0]
    for example: x = absolute_x / image_width or height = absolute_height / image_height
    atention: x_center y_center - are center of rectangle (are not top-left corner)

The provided code snippet convert the .mat files and the labels in proper .txt annotation formats to use in Yolov4. 
