# tensorflow-quantization-error-2471
Quantization converterError 2471 Check failed: status.ok()

Environment: tf-nightly=2.3, tensorflow-model-optimization=0.3.0, python=3.6.8

when convert keras model to tflite through below code:

    m1='ownmodel_pruW.h5'
    model=tf.keras.models.load_model(m1)
    tflite_model_file = 'ownnet.tflite'
    converter = tf.lite.TFLiteConverter.from_keras_model(model)
    tflite_model = converter.convert()
    with open(tflite_model_file, 'wb') as f:
        f.write(tflite_model)

error as below

ConverterError: See console for info. 2020-05-14 20:43:12.220536: F tensorflow/lite/toco/import_tensorflow.cc:2471] Check failed: status.ok() Neither input_content (0) nor float_val (73723) have the right dimensions (73728) for this float tensor (while processing node 'Modelnet/conv2/Conv2D/ReadVariableOp')

Any method to solve this error?
