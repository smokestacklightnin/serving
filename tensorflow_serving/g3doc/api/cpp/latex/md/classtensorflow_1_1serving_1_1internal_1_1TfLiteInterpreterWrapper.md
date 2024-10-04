::: {#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper}
:::

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper"}

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a4be98685ce72350ae0326ebe9357c6a2\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a4be98685ce72350ae0326ebe9357c6a2
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a4be98685ce72350ae0326ebe9357c6a2"}
**TfLiteInterpreterWrapper** (std::unique\_ptr$<$
tflite::ExternalCpuBackendContext $>$ external\_context,
std::unique\_ptr$<$ tflite::Interpreter $>$ interpreter)

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a681eaebc33180c587ca03dcc7650688e\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a681eaebc33180c587ca03dcc7650688e
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a681eaebc33180c587ca03dcc7650688e"}
**TfLiteInterpreterWrapper** (std::unique\_ptr$<$ tflite::Interpreter
$>$ interpreter)

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a0da04cb0d6d38f50d77218479b0b9d54\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a0da04cb0d6d38f50d77218479b0b9d54
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a0da04cb0d6d38f50d77218479b0b9d54"}
tflite::Interpreter $\ast$ **Get** ()

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a918142342b72c7c7c45c1e2abf62003d\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a918142342b72c7c7c45c1e2abf62003d
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a918142342b72c7c7c45c1e2abf62003d"}
int **GetBatchSize** ()

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a3d06c7a667fa47ab74431c8ce0b66a0b\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a3d06c7a667fa47ab74431c8ce0b66a0b
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a3d06c7a667fa47ab74431c8ce0b66a0b"}
void **SetBatchSize** (int batch\_size)

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a724e07fa4fd2a56cef1737606dbf3e60\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a724e07fa4fd2a56cef1737606dbf3e60
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a724e07fa4fd2a56cef1737606dbf3e60"}
TfLiteStatus **Invoke** ()

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_ae7a013f5891ef98a42b1e2221912fae4\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_ae7a013f5891ef98a42b1e2221912fae4
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_ae7a013f5891ef98a42b1e2221912fae4"}
tensorflow::Status **SetStringData** (const std::vector$<$ const Tensor
$\ast$ $>$ &tensors, TfLiteTensor $\ast$tflite\_tensor, int
tensor\_index, int batch\_size)

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterWrapper\_a0408604d32d848e883e78a6bee52f2f8\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a0408604d32d848e883e78a6bee52f2f8
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_a0408604d32d848e883e78a6bee52f2f8"}
static Status **CreateTfLiteInterpreterWrapper** (const
tflite::FlatBufferModel &model, const tensorflow::SessionOptions
&options, std::unique\_ptr$<$
[TfLiteInterpreterWrapper](#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper)
$>$ &wrapper)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tflite\_interpreter\_pool.h

tensorflow\_serving/servables/tensorflow/tflite\_interpreter\_pool.cc
