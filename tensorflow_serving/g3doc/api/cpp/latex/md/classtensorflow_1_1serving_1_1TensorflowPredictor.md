::: {#classtensorflow_1_1serving_1_1TensorflowPredictor}
:::

[\[classtensorflow\_1\_1serving\_1\_1TensorflowPredictor\]]{#classtensorflow_1_1serving_1_1TensorflowPredictor
label="classtensorflow_1_1serving_1_1TensorflowPredictor"}

[\[classtensorflow\_1\_1serving\_1\_1TensorflowPredictor\_a0ef1a5159d52238b14aacd46de937ebf\]]{#classtensorflow_1_1serving_1_1TensorflowPredictor_a0ef1a5159d52238b14aacd46de937ebf
label="classtensorflow_1_1serving_1_1TensorflowPredictor_a0ef1a5159d52238b14aacd46de937ebf"}
**TensorflowPredictor**
([ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$\ast$thread\_pool\_factory)

[\[classtensorflow\_1\_1serving\_1\_1TensorflowPredictor\_a8d4880786475287d66c8539141f40973\]]{#classtensorflow_1_1serving_1_1TensorflowPredictor_a8d4880786475287d66c8539141f40973
label="classtensorflow_1_1serving_1_1TensorflowPredictor_a8d4880786475287d66c8539141f40973"}
Status **Predict** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const PredictRequest &request, PredictResponse $\ast$response)

[\[classtensorflow\_1\_1serving\_1\_1TensorflowPredictor\_aeb7ad69d66a041ffb1fe4f3f309d0ae2\]]{#classtensorflow_1_1serving_1_1TensorflowPredictor_aeb7ad69d66a041ffb1fe4f3f309d0ae2
label="classtensorflow_1_1serving_1_1TensorflowPredictor_aeb7ad69d66a041ffb1fe4f3f309d0ae2"}
Status **PredictWithModelSpec** (const RunOptions &run\_options,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core,
const ModelSpec &model\_spec, const PredictRequest &request,
PredictResponse $\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/predict\_impl.h

tensorflow\_serving/servables/tensorflow/predict\_impl.cc
