# tequ-api-client

### Before using these subflows prepare your machine for computer vision in Node-RED with Tensorflow.

Windows 10: https://github.com/juhaautioniemi/win10-nodered-tensorflow

Jetson Nano/NX: https://github.com/juhaautioniemi/jetson-nodered-tensorflow

Most of these subflows have external dependencies

### Available subflows

| Subflow                   | Version         | Desc | JSON |
| --------------------------|:---------------:| :-------------:| :-------------:| 
| IP-stream                 | 0.0.1           | Open MPJEG-stream from IP-camera. Tested with Basler BIP2-1920. | <a href="subflow-ip-camera.json">json</a> |
| [AI] Inference            | 0.0.1	          | Make prediction on image with Tensorflow.js model trained with Cloud Annotations pipeline. | |
| [AI] Annotate	            | 0.0.1           | Annotates prediction results from [AI] Inference subflow. | |
| [AI] Thumbnails           | 0.0.1           | Creates thumbnails of original image and annotated image. | |
| [API] Create datapacket   | 0.0.1           | Creates datapacket ready to send to Tequ-API. Supports Basler BIP2-1920 IP-camera at the moment. | |
| [API] Send image          | 0.0.1           | Send image to Tequ-API. Saves image to local filesystem if API is not available. | |
| [API] Get Token           | 0.0.1           | Retrieves token from Tequ-API. | |
| [AI] Crop & TM            | 0.0.1           | Crops results from '[AI] Inference' and makes prediction on cropped images with Teachable Machine model. | |
| [AI] Crop detected object | 0.0.1           | Crops results from '[AI] Inference' | |
| [AI] Azure Custom Vision  | 0.0.1           | Make prediction on image with Tensorflow.js model exported from Microsoft Custom Vision | |

![alt text](
https://github.com/juhaautioniemi/tequ-api-client/blob/master/subflows.JPG "subflows")

