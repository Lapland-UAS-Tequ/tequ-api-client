# tequ-api-client

Tequ-API documentation

https://tequ-api.eu-de.mybluemix.net/


### Before using these subflows prepare your machine for computer vision in Node-RED with Tensorflow.

- Windows 10: https://github.com/juhaautioniemi/win10-nodered-tensorflow

- Jetson Nano/NX: https://github.com/juhaautioniemi/jetson-nodered-tensorflow

Most of these subflows have external dependencies, that will be (hopefully) installed when you import flow to Node-RED.

### Available subflows

| Subflow                   | Version         | Desc | JSON |
| --------------------------|:---------------:| :-------------:| :-------------:|
| IP-stream                 | 0.0.1           | Open MPJEG-stream from IP-camera. Tested with Basler BIP2-1920. | <a href="subflows/ip-camera.json">json</a> |
| [AI] Inference            | 0.0.1	          | Make prediction on image with Tensorflow.js model trained with Cloud Annotations pipeline. | <a href="subflows/ai-inference.json">json</a> |
| [AI] Annotate	            | 0.0.1           | Annotates prediction results from [AI] Inference subflow. | <a href="subflows/ai-annotate.json">json</a> |
| [AI] Thumbnails           | 0.0.1           | Creates thumbnails of original image and annotated image. | <a href="subflows/ai-thumbnails.json">json</a> |
| [API] Create datapacket   | 0.0.1           | Creates datapacket ready to send to Tequ-API. Supports Basler BIP2-1920 IP-camera at the moment. | <a href="subflows/api-create-datapacket.json">json</a> |
| [API] Send image          | 0.0.1           | Send image to Tequ-API. Saves image to local filesystem if API is not available. | <a href="subflows/api-send-image.json">json</a> |
| [API] Get Token           | 0.0.1           | Retrieves token from Tequ-API. | <a href="subflows/api-get-token.json">json</a> |
| [AI] Crop & TM            | 0.0.1           | Crops results from '[AI] Inference' and makes prediction on cropped images with Teachable Machine model. | <a href="subflows/ai-crop-tm.json">json</a> |
| [AI] Crop detected object | 0.0.1           | Crops results from '[AI] Inference' | <a href="subflows/ai-crop-detected-object.json">json</a> |
| [AI] Azure Custom Vision  | 0.0.1           | Make prediction on image with Tensorflow.js model exported from Microsoft Custom Vision | <a href="subflows/ai-azure-custom-vision.json">json</a> |

### Subflows palette

![alt text](
https://github.com/juhaautioniemi/tequ-api-client/blob/master/images/subflows.JPG "Subflows")

### Available example flows

| Flow                      | Version         | Desc           | JSON           |
| --------------------------|:---------------:| :-------------:| :-------------:|
| Crop CA files             | 0.0.1           | Process and crop Cloud Annotations project files. Sort images to folders named by annotation label. | <a href="flows/crop-ca.json">json</a> |
