# yolov9-wholebody25-tensorflowjs-web-test
A test environment running yolov9-wholebody25 on TensorFlow.js.

```
pip install -U onnx2tf

pip install -U --no-deps \
tensorflowjs \
tensorflow_decision_forests \
ydf \
tensorflow_hub

onnx2tf -i yolov9_n_wholebody25_post_0100_1x3x480x640.onnx -cotof -dgc

tensorflowjs_converter \
--input_format tf_saved_model \
--output_format tfjs_graph_model \
saved_model \
tfjs_model
```
![image](https://github.com/user-attachments/assets/23930019-854e-4346-b502-e7a051f3b7d2)
![image](https://github.com/user-attachments/assets/f6a24109-5dd6-421d-a7c8-06b29ae45843)

- Starting the inference web server
    ```
    python -m http.server
    ```

- Displaying a web page (with TensorFlow.js)

    http://localhost:8000/test-tfjs.html

- Results

    ![image](https://github.com/user-attachments/assets/3b5115a1-d241-44b0-b6d5-16f4dcd67e94)

- Displaying a web page (with TensorFlow.js + USB Camera)

    http://localhost:8000/test-tfjs-usbcam.html
