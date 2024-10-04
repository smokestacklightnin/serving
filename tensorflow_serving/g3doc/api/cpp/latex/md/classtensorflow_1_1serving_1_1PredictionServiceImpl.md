::: {#classtensorflow_1_1serving_1_1PredictionServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl
label="classtensorflow_1_1serving_1_1PredictionServiceImpl"}

Inheritance diagram for tensorflow::serving::PredictionServiceImpl:

![image](classtensorflow_1_1serving_1_1PredictionServiceImpl__inherit__graph.pdf){width="209pt"}

Collaboration diagram for tensorflow::serving::PredictionServiceImpl:

![image](classtensorflow_1_1serving_1_1PredictionServiceImpl__coll__graph.pdf){width="209pt"}

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_a80a560406e326bdafd821e52a0cc10b9\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_a80a560406e326bdafd821e52a0cc10b9
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_a80a560406e326bdafd821e52a0cc10b9"}
**PredictionServiceImpl** (const
[PredictionServiceOptions](#structtensorflow_1_1serving_1_1PredictionServiceOptions)
&options)

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_a5f42cc7a78ecfcdd0adfde9fc8ff0e13\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_a5f42cc7a78ecfcdd0adfde9fc8ff0e13
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_a5f42cc7a78ecfcdd0adfde9fc8ff0e13"}
::grpc::Status **Predict** (::grpc::ServerContext $\ast$context, const
PredictRequest $\ast$request, PredictResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_a1de18c0f5e4f65fcf4d236b0ee44ece2\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_a1de18c0f5e4f65fcf4d236b0ee44ece2
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_a1de18c0f5e4f65fcf4d236b0ee44ece2"}
::grpc::Status **GetModelMetadata** (::grpc::ServerContext
$\ast$context, const GetModelMetadataRequest $\ast$request,
GetModelMetadataResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_a4b59a040d19d47f04011ab3da3e2ba0d\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_a4b59a040d19d47f04011ab3da3e2ba0d
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_a4b59a040d19d47f04011ab3da3e2ba0d"}
::grpc::Status **Classify** (::grpc::ServerContext $\ast$context, const
ClassificationRequest $\ast$request, ClassificationResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_a43b957bb4eaa38fc7dc4e79ac6a72ba2\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_a43b957bb4eaa38fc7dc4e79ac6a72ba2
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_a43b957bb4eaa38fc7dc4e79ac6a72ba2"}
::grpc::Status **Regress** (::grpc::ServerContext $\ast$context, const
RegressionRequest $\ast$request, RegressionResponse $\ast$response)
override

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceImpl\_ab23e8b28c0226491da8f9e3ef82f0c3f\]]{#classtensorflow_1_1serving_1_1PredictionServiceImpl_ab23e8b28c0226491da8f9e3ef82f0c3f
label="classtensorflow_1_1serving_1_1PredictionServiceImpl_ab23e8b28c0226491da8f9e3ef82f0c3f"}
::grpc::Status **MultiInference** (::grpc::ServerContext $\ast$context,
const MultiInferenceRequest $\ast$request, MultiInferenceResponse
$\ast$response) override

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/prediction\_service\_impl.h

tensorflow\_serving/model\_servers/prediction\_service\_impl.cc
