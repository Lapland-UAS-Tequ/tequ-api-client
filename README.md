# tequ-api-client

Tequ-API documentation

https://tequ-api.eu-de.mybluemix.net/


### Before using these subflows prepare your machine for computer vision in Node-RED with Tensorflow.

- Windows 10: https://github.com/juhaautioniemi/win10-nodered-tensorflow

- Jetson Nano/NX: https://github.com/juhaautioniemi/tequ-jetson-nodered-tensorflow/

- RPI3/4: https://github.com/juhaautioniemi/tequ-rpi-setup

- NVIDIA Triton https://github.com/juhaautioniemi/tequ-setup-triton-inference-server

Most of these subflows have external dependencies, that will you need to install before you import flow to Node-RED.

### Available subflows

| Subflow                     | Version         | Desc | JSON |
| ----------------------------|:---------------:| :-------------:| :-------------:|
| [CAM] MPJEG stream          | 0.0.1           | Open MPJEG-stream from IP-camera. Tested with Basler BIP2-1920. | <a href="subflows/cam-ip-camera.json">json</a> |
| [AI] Detect-sm              | 0.0.1           | Make prediction on image using Tensorflow SavedModel trained with tequ-tf2-ca-training-pipeline | <a href="subflows/ai-detect-sm.json">json</a> |
| [AI] Detect-Triton        | 0.0.1           | Make prediction on image using Tensorflow SavedModel hosted in NVIDIA Triton Inference Server | <a href="subflows/ai-detect-triton.json">json</a> |
| [AI] Detect-v1*             | 0.0.1	          | Make prediction on image using Tensorflow.js model trained with tequ-tf1-ca-training-pipeline. | <a href="subflows/ai-detect-v1.json">json</a> |
| [AI] Detect-v2*             | 0.0.1           | Make prediction on image using Tensorflow.js model trained with tequ-tf1-ca-training-pipeline. | <a href="subflows/ai-detect-v2.json">json</a> |
| [AI] Detect-acv**            | 0.0.1          | Make prediction on image using Tensorflow.js model trained and exported from Microsoft Azure Custom Vision | <a href="subflows/ai-detect-acv.json">json</a>  |
| [AI] Crop & TM***            | 0.0.1          | Crops results from '[AI] detect subflows' and classify cropped area(s) using Tensorflow.js model trained and exported from Google Teachable Machine. | <a href="subflows/ai-crop-tm.json">json</a> |
| [IMG] Annotate	            | 0.0.1           | Annotates prediction results from [AI] Inference subflow. | <a href="subflows/img-annotate.json">json</a> |
| [IMG] Thumbnails            | 0.0.1           | Creates thumbnails of original image and annotated image. | <a href="subflows/img-thumbnails.json">json</a> |
| [IMG] Crop detected object(s) | 0.0.1         | Creates thumbnails of original image and annotated image. | <a href="subflows/img-crop-detected-object.json">json</a> |
| [API] Get Token             | 0.0.1           | Retrieve token from Tequ-API. | <a href="subflows/api-get-token.json">json</a> |
| [API] Create datapacket     | 0.0.1           | Creates datapacket ready to send to Tequ-API. Supports Basler BIP2-1920 IP-camera at the moment. | <a href="subflows/api-create-datapacket.json">json</a> |
| [API] Add image            | 0.0.1            | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflows/api-add-image.json">json</a> |
| [API] Add video clip       | 0.0.1            | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflows/api-add-video.json">json</a> |
| [API] Operation            | 0.0.1            | **N/A** | <a href="subflows/api-operation.json">json</a> |


*Remove folder "node_modules" from /.node-red/node_modules/@cloud-annotations/models-node-gpu

**To enable GPU support when using [AI] Detect-acv
```
Modify file .node-red\node_modules\@microsoft\customvision-tfjs-node\lib\index.js

Replace Line 28:

var tf = _interopRequireWildcard(require("@tensorflow/tfjs-node"));

with:

var tf = _interopRequireWildcard(require("@tensorflow/tfjs-node-gpu"));
```

You might also need to re-install tfjs-node-gpu to make everything work and tfjs-node to make everything work.

***To enable GPU support when using [AI] Crop & TM
```
Modify file .node-red\node_modules\node-red-contrib-teachable-machine\teachable_machine.js

Replace Line 5:

var tf = require('@tensorflow/tfjs')

with:

var tf = require('@tensorflow/tfjs-node-gpu')

```
You might also need to re-install tfjs-node-gpu to make everything work.

### Subflows palette

![alt text](
https://github.com/juhaautioniemi/tequ-api-client/blob/master/images/subflows.JPG "Subflows")

### Available example flows

| Flow                      | Version         | Desc           | JSON           |
| --------------------------|:---------------:| :-------------:| :-------------:|
| crop-ca                   | 0.0.1           | Process and crop Cloud Annotations project files. Sort images to folders named by annotation label. | <a href="flows/crop-ca.json">json</a> |
| example-ai-detect-v2      | 0.0.1           | Use [AI] Detect-v2 and [IMG] Annotate | <a href="flows/example-ai-detect-v2.json">json</a> |
| example-ai-detect-sm      | 0.0.1           | Use [AI] Detect-sm and [IMG] Annotate | <a href="flows/example-ai-detect-sm.json">json</a> |
| example-ai-detect-triton  | 0.0.1           | Use [AI] Detect-triton and [IMG] Annotate | <a href="flows/example-ai-detect-triton.json">json</a> |
