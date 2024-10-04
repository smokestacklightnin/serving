::: {#classtensorflow_1_1serving_1_1PredictionServiceGrpc}
:::

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceGrpc\]]{#classtensorflow_1_1serving_1_1PredictionServiceGrpc
label="classtensorflow_1_1serving_1_1PredictionServiceGrpc"}

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceGrpc\_a64456282d24cca677a36e3e955a0a735\]]{#classtensorflow_1_1serving_1_1PredictionServiceGrpc_a64456282d24cca677a36e3e955a0a735
label="classtensorflow_1_1serving_1_1PredictionServiceGrpc_a64456282d24cca677a36e3e955a0a735"}
StatusOr$<$::grpc::ClientContext $\ast$ $>$ **CreateRpc**
(absl::Duration max\_rpc\_deadline)

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceGrpc\_a7648ec0315fe5b99335a054529a2cdc5\]]{#classtensorflow_1_1serving_1_1PredictionServiceGrpc_a7648ec0315fe5b99335a054529a2cdc5
label="classtensorflow_1_1serving_1_1PredictionServiceGrpc_a7648ec0315fe5b99335a054529a2cdc5"}
void **Predict** (::grpc::ClientContext $\ast$rpc, PredictRequest
$\ast$request, PredictResponse $\ast$response, std::function$<$
void(absl::Status status)$>$ callback)

[\[classtensorflow\_1\_1serving\_1\_1PredictionServiceGrpc\_a4b5501563eba75a4d6b24ba657ac45cf\]]{#classtensorflow_1_1serving_1_1PredictionServiceGrpc_a4b5501563eba75a4d6b24ba657ac45cf
label="classtensorflow_1_1serving_1_1PredictionServiceGrpc_a4b5501563eba75a4d6b24ba657ac45cf"}
static absl::Status **Create** (const std::string &target\_address,
std::unique\_ptr$<$
[PredictionServiceGrpc](#classtensorflow_1_1serving_1_1PredictionServiceGrpc)
$>$ $\ast$service)

The documentation for this class was generated from the following files:

tensorflow\_serving/experimental/tensorflow/ops/remote\_predict/kernels/prediction\_service\_grpc.h

tensorflow\_serving/experimental/tensorflow/ops/remote\_predict/kernels/prediction\_service\_grpc.cc
