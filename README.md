# yolov7_obb_onnxruntime
## Introduce
This is a C++ ONNX Runtime deployment code for YOLOv7 parking spot corner detection. The model input size is [1,3,768,256], and the model inference output tensor dimensions are [1, 12096, 11],which the 11 corresponds to {x1, y1, x2, y2, x3, y3, x4, y4, prob, park, no_park}. YOLOv7_rotated is an anchor-free detection algorithm that directly outputs the coordinates of the 4 pairs of vertices of a quadrilateral detection box. Additionally, the detection box is not necessarily a rectangle. This code also includes the geometric computation method for convex polygon IoU, allowing for more precise prediction box non-maximum suppression (NMS).

## Get Start
* Install  opencv4 and onnxruntime
* Edit CMakeLists.txt, set(ONNXRUNTIME_DIR "your_onnxruntime_path").
* Next <br>`cd yolov7_rotated_ort` <br>`mkdir build && cd build` <br>`cmake ..`<br>`make`<br>`./rotated_yolov7_ort`<br>
![](https://github.com/zhang324-L/yolov7_obb_onnxruntime/blob/main/yolov7_rotated_ort/yolov7images/img1.jpg) ![](https://github.com/zhang324-L/yolov7_obb_onnxruntime/blob/main/yolov7_rotated_ort/yolov7images/img2.jpg) 
