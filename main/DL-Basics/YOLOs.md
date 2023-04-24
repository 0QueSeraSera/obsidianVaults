[[Object Detection]]
****
# Series overview
1.  YOLOv1: The original YOLO model was introduced in 2015 and used a single neural network to **simultaneously predict object classes and bounding boxes**. YOLOv1 was known for its speed but suffered from low accuracy and difficulty in detecting small objects.
    
2.  YOLOv2: This model was introduced in 2016 and addressed some of the weaknesses of YOLOv1. YOLOv2 used a more powerful backbone network and introduced **anchor boxes**, which improved the accuracy of small object detection.
    
3.  YOLOv3: This model was introduced in 2018 and was a significant improvement over YOLOv2. YOLOv3 used a feature pyramid network and introduced multiple scales of detection, resulting in improved accuracy across a wide range of object sizes. YOLOv3 also used a new architecture that allowed it to be trained on larger datasets, resulting in better generalization.
    
4.  YOLOv4: This model was introduced in 2020 and introduced several new features to improve accuracy and speed. YOLOv4 used a more powerful backbone network, introduced a novel CSP (Cross-Stage Partial) block, and used a novel SPP (Spatial Pyramid Pooling) module to improve the accuracy of small object detection. YOLOv4 also introduced a more efficient training process, resulting in faster convergence and better generalization.
    
5.  YOLOv5: This is the latest version of the YOLO model, which was introduced in 2020. YOLOv5 builds on the previous versions by using a more efficient backbone network and introducing a novel SPP module. YOLOv5 also introduced a more efficient training process and achieved state-of-the-art performance on several object detection benchmarks.
# YOLO principles
## loss function
![[Pasted image 20230313100327.png]]
![[Pasted image 20230313100355.png]]
1.  First, we find the bounding boxes with the highest **intersection over union** (**IoU**) and with the correct bounding boxes.
2.  Then, we calculate the _confidence loss_, which means the _probability of the object being present inside a given bounding box_.
3.  Next, we calculate the _classification loss_, which indicates the present class of objects within the bounding box.
4.  Finally, we calculate the coordinate loss for matching the detected boxes.