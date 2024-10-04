::: {#classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1TensorflowClassificationServiceImpl\]]{#classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl
label="classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl"}

[\[classtensorflow\_1\_1serving\_1\_1TensorflowClassificationServiceImpl\_a151e5b9077e01507a5dd364aba771635\]]{#classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl_a151e5b9077e01507a5dd364aba771635
label="classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl_a151e5b9077e01507a5dd364aba771635"}
static Status **Classify** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const thread::ThreadPoolOptions &thread\_pool\_options, const
ClassificationRequest &request, ClassificationResponse $\ast$response)

[\[classtensorflow\_1\_1serving\_1\_1TensorflowClassificationServiceImpl\_a22d30d293df832173a67f3e5ec600bcb\]]{#classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl_a22d30d293df832173a67f3e5ec600bcb
label="classtensorflow_1_1serving_1_1TensorflowClassificationServiceImpl_a22d30d293df832173a67f3e5ec600bcb"}
static Status **ClassifyWithModelSpec** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const thread::ThreadPoolOptions &thread\_pool\_options, const ModelSpec
&model\_spec, const ClassificationRequest &request,
ClassificationResponse $\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/classification\_service.h

tensorflow\_serving/servables/tensorflow/classification\_service.cc
