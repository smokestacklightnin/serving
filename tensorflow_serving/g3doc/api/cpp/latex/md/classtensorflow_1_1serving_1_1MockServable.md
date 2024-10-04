::: {#classtensorflow_1_1serving_1_1MockServable}
:::

[\[classtensorflow\_1\_1serving\_1\_1MockServable\]]{#classtensorflow_1_1serving_1_1MockServable
label="classtensorflow_1_1serving_1_1MockServable"}

Inheritance diagram for tensorflow::serving::MockServable:

![image](classtensorflow_1_1serving_1_1MockServable__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::MockServable:

![image](classtensorflow_1_1serving_1_1MockServable__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_aa91aacc480ccc6263b74bf78ec199b51\]]{#classtensorflow_1_1serving_1_1MockServable_aa91aacc480ccc6263b74bf78ec199b51
label="classtensorflow_1_1serving_1_1MockServable_aa91aacc480ccc6263b74bf78ec199b51"}
**MOCK\_METHOD** (absl::Status, Classify,(const
[tensorflow::serving::Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const tensorflow::serving::ClassificationRequest
&request, tensorflow::serving::ClassificationResponse
$\ast$response),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_a16bbb72efd6149b5ae6e8bda0c2f8567\]]{#classtensorflow_1_1serving_1_1MockServable_a16bbb72efd6149b5ae6e8bda0c2f8567
label="classtensorflow_1_1serving_1_1MockServable_a16bbb72efd6149b5ae6e8bda0c2f8567"}
**MOCK\_METHOD** (absl::Status, Regress,(const
[tensorflow::serving::Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const tensorflow::serving::RegressionRequest &request,
tensorflow::serving::RegressionResponse $\ast$response),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_a679c3361f4c95fb547ba8f404819dbbb\]]{#classtensorflow_1_1serving_1_1MockServable_a679c3361f4c95fb547ba8f404819dbbb
label="classtensorflow_1_1serving_1_1MockServable_a679c3361f4c95fb547ba8f404819dbbb"}
**MOCK\_METHOD** (absl::Status, Predict,(const
[tensorflow::serving::Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const tensorflow::serving::PredictRequest &request,
tensorflow::serving::PredictResponse $\ast$response),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_a1e24702b948802e177f5c7bc8425d36c\]]{#classtensorflow_1_1serving_1_1MockServable_a1e24702b948802e177f5c7bc8425d36c
label="classtensorflow_1_1serving_1_1MockServable_a1e24702b948802e177f5c7bc8425d36c"}
**MOCK\_METHOD** (absl::StatusOr$<$ std::unique\_ptr$<$
[PredictStreamedContext](#classtensorflow_1_1serving_1_1PredictStreamedContext)
$>$$>$, PredictStreamed,(const
[tensorflow::serving::Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, absl::AnyInvocable$<$ void(absl::StatusOr$<$
tensorflow::serving::PredictResponse $>$)$>$
response\_callback),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_aeca0916ebcc135a7bcd29c7b761cdfdc\]]{#classtensorflow_1_1serving_1_1MockServable_aeca0916ebcc135a7bcd29c7b761cdfdc
label="classtensorflow_1_1serving_1_1MockServable_aeca0916ebcc135a7bcd29c7b761cdfdc"}
**MOCK\_METHOD** (absl::Status, MultiInference,(const
[tensorflow::serving::Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const tensorflow::serving::MultiInferenceRequest
&request, tensorflow::serving::MultiInferenceResponse
$\ast$response),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_a8c4d6a337dce912c30fbee2ca262958a\]]{#classtensorflow_1_1serving_1_1MockServable_a8c4d6a337dce912c30fbee2ca262958a
label="classtensorflow_1_1serving_1_1MockServable_a8c4d6a337dce912c30fbee2ca262958a"}
**MOCK\_METHOD** (absl::Status, GetModelMetadata,(const
tensorflow::serving::GetModelMetadataRequest &request,
tensorflow::serving::GetModelMetadataResponse $\ast$response),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_acecedf98762504ff1001c5f7fe7c6da8\]]{#classtensorflow_1_1serving_1_1MockServable_acecedf98762504ff1001c5f7fe7c6da8
label="classtensorflow_1_1serving_1_1MockServable_acecedf98762504ff1001c5f7fe7c6da8"}
**MOCK\_METHOD** (bool, SupportsPaging,(),(const, final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_aba68ccb4d8a13a49d9b9147615037fb5\]]{#classtensorflow_1_1serving_1_1MockServable_aba68ccb4d8a13a49d9b9147615037fb5
label="classtensorflow_1_1serving_1_1MockServable_aba68ccb4d8a13a49d9b9147615037fb5"}
**MOCK\_METHOD** (absl::Status, Suspend,(),(final))

[\[classtensorflow\_1\_1serving\_1\_1MockServable\_a54ff9f365143af108771de33c7d92f20\]]{#classtensorflow_1_1serving_1_1MockServable_a54ff9f365143af108771de33c7d92f20
label="classtensorflow_1_1serving_1_1MockServable_a54ff9f365143af108771de33c7d92f20"}
**MOCK\_METHOD** (absl::Status, Resume,(),(final))

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/mock\_servable.h
