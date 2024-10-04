::: {#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool}
:::

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterPool\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool"}

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterPool\_a9611292a3d5cceda68b0477adc6a44ae\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_a9611292a3d5cceda68b0477adc6a44ae
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_a9611292a3d5cceda68b0477adc6a44ae"}
std::unique\_ptr$<$
[TfLiteInterpreterWrapper](#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper)
$>$ **GetInterpreter** ()

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterPool\_ad6d1d1b1c5eaf490cc8e59248c319632\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_ad6d1d1b1c5eaf490cc8e59248c319632
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_ad6d1d1b1c5eaf490cc8e59248c319632"}
void **ReturnInterpreter** (std::unique\_ptr$<$
[TfLiteInterpreterWrapper](#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper)
$>$ interpreter)

[\[classtensorflow\_1\_1serving\_1\_1internal\_1\_1TfLiteInterpreterPool\_a1de40a0fa915827e4975128031b765bb\]]{#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_a1de40a0fa915827e4975128031b765bb
label="classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_a1de40a0fa915827e4975128031b765bb"}
static tensorflow::Status **CreateTfLiteInterpreterPool** (const
tflite::FlatBufferModel $\ast$model, const tensorflow::SessionOptions
&options, int pool\_size, std::unique\_ptr$<$
[TfLiteInterpreterPool](#classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool)
$>$ &interpreter\_pool)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tflite\_interpreter\_pool.h

tensorflow\_serving/servables/tensorflow/tflite\_interpreter\_pool.cc
