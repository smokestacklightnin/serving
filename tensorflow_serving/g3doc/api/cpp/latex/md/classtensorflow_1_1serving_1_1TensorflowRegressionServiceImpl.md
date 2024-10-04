::: {#classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1TensorflowRegressionServiceImpl\]]{#classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl
label="classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl"}

[\[classtensorflow\_1\_1serving\_1\_1TensorflowRegressionServiceImpl\_a4c388d0c52e3f15aad76a180d503c5a2\]]{#classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl_a4c388d0c52e3f15aad76a180d503c5a2
label="classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl_a4c388d0c52e3f15aad76a180d503c5a2"}
static Status **Regress** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const thread::ThreadPoolOptions &thread\_pool\_options, const
RegressionRequest &request, RegressionResponse $\ast$response)

[\[classtensorflow\_1\_1serving\_1\_1TensorflowRegressionServiceImpl\_a4d5d116709cab1eb41ebac5f5abaf783\]]{#classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl_a4d5d116709cab1eb41ebac5f5abaf783
label="classtensorflow_1_1serving_1_1TensorflowRegressionServiceImpl_a4d5d116709cab1eb41ebac5f5abaf783"}
static Status **RegressWithModelSpec** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const thread::ThreadPoolOptions &thread\_pool\_options, const ModelSpec
&model\_spec, const RegressionRequest &request, RegressionResponse
$\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/regression\_service.h

tensorflow\_serving/servables/tensorflow/regression\_service.cc
