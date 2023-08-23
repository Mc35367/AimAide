# AimAide for CS

External realtime object detection-based aim aiding powered by <b>YOLOv8</b>, <b>CUDA</b> and <b>TensorRT</b><br>
[Twitter for further development updates](https://twitter.com/AimAideCS)

<h3>Features</h3>
YOLOv8 Models trained on mirage with various CT and T agents (body and head).<br>
Simple smooth linear mouse mover locking onto target closest to crosshair.<br>

<h3>Hardware Requirements</h3>
To get this to work the detector has to run at 30fps at least.<br>
NVIDIA GTX1070 runs at 30fps on a 640x640 model or 60fps on a 320x320 model with TensorRT.<br>
NVIDIA RTX4090 should max out at ~120fps on a 640x640 model. (also TensorRT)<br>

<h3>Usage</h3>
I) Disable windows mouse acceleration<br>
II) Disable raw input in CSGO<br>
III) Cap max_fps in CSGO at your native display refresh rate<br>
<br>
1) Run "python launcher.py"<br>
2) Depending on your hardware choose from 3 different models (nano, small, medium)<br>
nano (highest framerate, lowest detection performance),<br>
medium (lowest framerate, best decetion performance)<br>
3) Run in benchmark mode first to see what framerate you get (over 60fps increase sensitivity mode)<br>
4) Adjust mouse sensitivity in CS and/or sensitivity mode of AimAide

<h3>Arguments<h3>
  
| arg      | default   | Description                                                                                                |
| ----      | ---       | ---                                                                                                       |
| <sub>--input_size</sub> | <sub>320</sub>             | <sub>dimension of the input image for the detector</sub>                  |
| <sub>--grabber</sub>    | <sub>'win32'</sub>         | <sub>select screen grabber (win32, d3d_gpu, d3d_np) </sub>                           |
| <sub>--model</sub>      | <sub>models/yolov8s_csgo_mirage-320-v41-al-gen-bg</sub>| <sub>selected engine (TensorRT) or weights (YOLOv8)</sub>|       
| <sub>--side </sub>      | <sub>'dm'</sub>  | <sub>which side your are on, 'ct', 't' or 'dm' (deathmatch)</sub>                  | 
| <sub>--minconf </sub>   | <sub>0.75</sub>  | <sub>minimum detection confidence</sub>                                            |  
| <sub>--sensitivity</sub>     | <sub>1</sub> | <sub>sensitivity mode, increase when having a high framerate or chaotic aim</sub>  |
| <sub>--flickieness</sub>     |<sub>4</sub>  | <sub>how flicky the mouse mover behaves (4 is slow, 16 is very flicky)</sub>  |
| <sub>--visualize</sub>       |<sub>False</sub> | <sub>show live detector output in a new window</sub>                               |
| <sub>--view_only </sub>      |<sub>False</sub> | <sub>run in view only mode (disarmed)</sub>                                        |
| <sub>--benchmark</sub>       | <sub>False</sub> | <sub>launch benchmark mode</sub>                                                   |
| <sub>--no_engine_check</sub> | <sub>False</sub> | <sub>skips engine checking and building (run_tensorrt.py only)</sub>       |
