::: {#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl"}

Inheritance diagram for tensorflow::serving::TfrtPredictionServiceImpl:

![image](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl__inherit__graph.pdf){width="226pt"}

Collaboration diagram for
tensorflow::serving::TfrtPredictionServiceImpl:

![image](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl__coll__graph.pdf){width="226pt"}

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_a7e1a167614401fe656667217db641681\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a7e1a167614401fe656667217db641681
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a7e1a167614401fe656667217db641681"}
**TfrtPredictionServiceImpl** (const
[PredictionServiceOptions](#structtensorflow_1_1serving_1_1PredictionServiceOptions)
&options)

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_ad2b086077b6ef4b933e6f8c2d0aba923\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_ad2b086077b6ef4b933e6f8c2d0aba923
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_ad2b086077b6ef4b933e6f8c2d0aba923"}
::grpc::Status **Predict** (::grpc::ServerContext $\ast$context, const
PredictRequest $\ast$request, PredictResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_a8efab43ea3a17e4916c714092f76c746\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a8efab43ea3a17e4916c714092f76c746
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a8efab43ea3a17e4916c714092f76c746"}
::grpc::Status **GetModelMetadata** (::grpc::ServerContext
$\ast$context, const GetModelMetadataRequest $\ast$request,
GetModelMetadataResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_a2547ab8ff4f2496124b2295321498a0a\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a2547ab8ff4f2496124b2295321498a0a
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a2547ab8ff4f2496124b2295321498a0a"}
::grpc::Status **Classify** (::grpc::ServerContext $\ast$context, const
ClassificationRequest $\ast$request, ClassificationResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_ad52f5963c5d72af1014593ec46873c70\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_ad52f5963c5d72af1014593ec46873c70
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_ad52f5963c5d72af1014593ec46873c70"}
::grpc::Status **Regress** (::grpc::ServerContext $\ast$context, const
RegressionRequest $\ast$request, RegressionResponse $\ast$response)
override

[\[classtensorflow\_1\_1serving\_1\_1TfrtPredictionServiceImpl\_a7c88b08994b556677c1f57c6339e7fe6\]]{#classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a7c88b08994b556677c1f57c6339e7fe6
label="classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl_a7c88b08994b556677c1f57c6339e7fe6"}
::grpc::Status **MultiInference** (::grpc::ServerContext $\ast$context,
const MultiInferenceRequest $\ast$request, MultiInferenceResponse
$\ast$response) override

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/tfrt\_prediction\_service\_impl.h

tensorflow\_serving/model\_servers/tfrt\_prediction\_service\_impl.cc
