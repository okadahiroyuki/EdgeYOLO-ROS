# EdgeYOLO-ROS

EdgeYOLO-ROS humble

```
cd ~/ros2_ws_src
git clone --recursive https://github.com/okadahiroyuki/YOLOX-ROS -b humble
cd YOLOX-ROS/yolox_ros_cpp/docker/onnxruntime/
```

docker exec -it -e DISPLAY=$DISPLAY edgeyolo_onnxruntime bash


source /opt/ros/humble/setup.bash
cd /root/ros2_ws
source install/setup.bash

ros2 launch edgeyolo_ros_cpp edgeyolo_onnxruntime.launch.py \
  model_path:=/root/ros2_ws/src/EdgeYOLO-ROS/weights/onnx/edgeyolo_tiny_coco_416x416.onnx \
  imshow_isshow:=false


別ターミナルで：

source /opt/ros/humble/setup.bash
source /root/ros2_ws/install/setup.bash
ros2 topic list
# /edgeyolo/image_raw などが出てくるはず


rqt_image_view で /edgeyolo/image_raw を選べば、検出結果付き画像が見えるはずです。
