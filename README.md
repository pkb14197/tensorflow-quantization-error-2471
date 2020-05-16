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

Error as below:

ConverterError: See console for info.
2020-05-16 17:48:30.914124: I tensorflow/lite/toco/import_tensorflow.cc:1324] Converting unsupported operation: FusedBatchNormV3

2020-05-16 17:48:30.914668: E tensorflow/core/framework/op_kernel.cc:1325] OpKernel ('op: "WrapDatasetVariant" device_type: "CPU"') for unknown op: WrapDatasetVariant

2020-05-16 17:48:30.914953: E tensorflow/core/framework/op_kernel.cc:1325] OpKernel ('op: "WrapDatasetVariant" device_type: "GPU" host_memory_arg: "input_handle" host_memory_arg: "output_handle"') for unknown op: WrapDatasetVariant

2020-05-16 17:48:30.915355: E tensorflow/core/framework/op_kernel.cc:1325] OpKernel ('op: "UnwrapDatasetVariant" device_type: "CPU"') for unknown op: UnwrapDatasetVariant

2020-05-16 17:48:30.915642: E tensorflow/core/framework/op_kernel.cc:1325] OpKernel ('op: "UnwrapDatasetVariant" device_type: "GPU" host_memory_arg: "input_handle" host_memory_arg: "output_handle"') for unknown op: UnwrapDatasetVariant

2020-05-16 17:48:30.916110: I tensorflow/lite/toco/import_tensorflow.cc:1373] Unable to determine output type for op: FusedBatchNormV3

2020-05-16 17:48:30.916375: I tensorflow/lite/toco/import_tensorflow.cc:1324] Converting unsupported operation: FusedBatchNormV3

2020-05-16 17:48:30.916600: I tensorflow/lite/toco/import_tensorflow.cc:1373] Unable to determine output type for op: FusedBatchNormV3

2020-05-16 17:48:30.916858: I tensorflow/lite/toco/import_tensorflow.cc:1324] Converting unsupported operation: FusedBatchNormV3

2020-05-16 17:48:30.917086: I tensorflow/lite/toco/import_tensorflow.cc:1373] Unable to determine output type for op: FusedBatchNormV3

2020-05-16 17:48:30.917327: I tensorflow/lite/toco/import_tensorflow.cc:1324] Converting unsupported operation: FusedBatchNormV3

2020-05-16 17:48:30.917546: I tensorflow/lite/toco/import_tensorflow.cc:1373] Unable to determine output type for op: FusedBatchNormV3

2020-05-16 17:48:30.917845: F tensorflow/lite/toco/tooling_util.cc:627] Check failed: dim >= 1 (-1 vs. 1)

Any method to solve this error?
