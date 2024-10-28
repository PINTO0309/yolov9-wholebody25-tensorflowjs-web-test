# yolov9-wholebody25-tensorflowjs-web-test
A test environment running yolov9-wholebody25 on TensorFlow.js.

https://github.com/PINTO0309/PINTO_model_zoo/tree/main/459_YOLOv9-Wholebody25

- Model conversion

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

- Displaying a web page (with TensorFlow.js + WebGL backend (AUTO) + USB Camera)

    If your browser cache is enabled, model loading and inference may fail. If this does not work, try starting your browser in an incognito window or in secret mode before accessing the URL below.

    http://localhost:8000/test-tfjs-usbcam.html

    or

    http://localhost:8000/test-tfjs-usbcam-low.html

- Results

    - Normal Resolution Mode 640x480

        https://github.com/user-attachments/assets/64f1e6b1-2cca-4960-93a0-66f3c95c89cb

    - Low Resolution Mode 320x256

        https://github.com/user-attachments/assets/d98c06ef-2869-4843-aea5-c92b9f8033c1

- Check if your browser supports WebGL hardware acceleration

    https://get.webgl.org/

    ![image](https://github.com/user-attachments/assets/19e42666-e334-49d2-a1e9-c08121b9f709)

- Extra

    This is a game where you interactively draw a polygonal area with a mouse click or double click and a message is displayed when your hand enters the area.

    http://localhost:8000/test-tfjs-usbcam-inner-polygon.html

    https://github.com/user-attachments/assets/d0c557fe-1a2d-4e8f-9db5-ded08d4b01d1
