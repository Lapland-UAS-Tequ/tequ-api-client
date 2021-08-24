# tequ-api-client

### Before using these subflows prepare your machine for computer vision in Node-RED with Tensorflow.

Windows 10: https://github.com/juhaautioniemi/win10-nodered-tensorflow

Jetson Nano/NX: https://github.com/juhaautioniemi/jetson-nodered-tensorflow

Most of these subflows have external dependencies

### Available subflows

| Subflow                   | Version         | Desc | JSON |
| --------------------------|:---------------:| :-------------:| :-------------:| 
| IP-stream                 | 0.0.1           | Open MPJEG-stream from IP-camera. Tested with Basler BIP2-1920. | <a href="subflow-ip-camera.json">json</a> |
| [AI] Inference            | 0.0.1	          | Make prediction on image with Tensorflow.js model trained with Cloud Annotations pipeline. | <a href="subflow-ai-inference.json">json</a> |
| [AI] Annotate	            | 0.0.1           | Annotates prediction results from [AI] Inference subflow. | <a href="subflow-ai-annotate.json">json</a> |
| [AI] Thumbnails           | 0.0.1           | Creates thumbnails of original image and annotated image. | <a href="subflow-ai-thumbnails.json">json</a> |
| [API] Create datapacket   | 0.0.1           | Creates datapacket ready to send to Tequ-API. Supports Basler BIP2-1920 IP-camera at the moment. | <a href="subflow-api-create-datapacket.json">json</a> |
| [API] Send image          | 0.0.1           | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflow-api-send-image.json">json</a> |
| [API] Get Token           | 0.0.1           | Retrieves token from Tequ-API. | <a href="subflow-api-get-token.json">json</a> |
| [AI] Crop & TM            | 0.0.1           | Crops results from '[AI] Inference' and makes prediction on cropped images with Teachable Machine model. | <a href="subflow-ai-crop-tm.json">json</a> |
| [AI] Crop detected object | 0.0.1           | Crops results from '[AI] Inference' | <a href="subflow-ai-crop-detected-object.json">json</a> |
| [AI] Azure Custom Vision  | 0.0.1           | Make prediction on image with Tensorflow.js model exported from Microsoft Custom Vision | <a href="subflow-ai-azure-custom-vision.json">json</a> |

![alt text](
https://github.com/juhaautioniemi/tequ-api-client/blob/master/images/subflows.JPG "subflows")

