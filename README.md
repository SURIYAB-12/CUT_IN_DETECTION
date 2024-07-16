➤ Requirements
Python 3.7+

OpenCV, Scikit-learn, onnxruntime, pycuda and pytorch.

Install :

The requirements.txt file should list all Python libraries that your notebooks depend on, and they will be installed using:

pip install -r requirements.txt


Convert Onnx to TenserRT model :

Need to modify onnx_model_path and trt_model_path before converting.

python convertOnnxToTensorRT.py -i <path-of-your-onnx-model>  -o <path-of-your-trt-model>
Quantize ONNX models :

Converting a model to use float16 instead of float32 can decrease the model size.

python onnxQuantization.py -i <path-of-your-onnx-model>
Video Inference :

Setting Config :
Note : can support onnx/tensorRT format model. But it needs to match the same model type.

lane_config = {
 "model_path": "./TrafficLaneDetector/models/culane_res18.trt",
 "model_type" : LaneModelType.UFLDV2_CULANE
}

object_config = {
 "model_path": './ObjectDetector/models/yolov8l-coco.trt',
 "model_type" : ObjectModelType.YOLOV8,
 "classes_path" : './ObjectDetector/models/coco_label.txt',
 "box_score" : 0.4,
 "box_nms_iou" : 0.45
}

