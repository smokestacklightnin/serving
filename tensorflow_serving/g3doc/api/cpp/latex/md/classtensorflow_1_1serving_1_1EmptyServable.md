::: {#classtensorflow_1_1serving_1_1EmptyServable}
:::

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\]]{#classtensorflow_1_1serving_1_1EmptyServable
label="classtensorflow_1_1serving_1_1EmptyServable"}

Inheritance diagram for tensorflow::serving::EmptyServable:

![image](classtensorflow_1_1serving_1_1EmptyServable__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::EmptyServable:

![image](classtensorflow_1_1serving_1_1EmptyServable__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_a9764b57ccc87454fb2da9f2c5d534da1\]]{#classtensorflow_1_1serving_1_1EmptyServable_a9764b57ccc87454fb2da9f2c5d534da1
label="classtensorflow_1_1serving_1_1EmptyServable_a9764b57ccc87454fb2da9f2c5d534da1"}
absl::Status **Classify** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const ClassificationRequest &request,
ClassificationResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_a0e65e9c5f00b91271a569aae7853bb4c\]]{#classtensorflow_1_1serving_1_1EmptyServable_a0e65e9c5f00b91271a569aae7853bb4c
label="classtensorflow_1_1serving_1_1EmptyServable_a0e65e9c5f00b91271a569aae7853bb4c"}
absl::Status **Regress** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const RegressionRequest &request, RegressionResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_a792585ec6c0c406d94a7012e6686bb6b\]]{#classtensorflow_1_1serving_1_1EmptyServable_a792585ec6c0c406d94a7012e6686bb6b
label="classtensorflow_1_1serving_1_1EmptyServable_a792585ec6c0c406d94a7012e6686bb6b"}
absl::Status **Predict** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const PredictRequest &request, PredictResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_a329dcd3d76a8fc14b5e0d769d8460bda\]]{#classtensorflow_1_1serving_1_1EmptyServable_a329dcd3d76a8fc14b5e0d769d8460bda
label="classtensorflow_1_1serving_1_1EmptyServable_a329dcd3d76a8fc14b5e0d769d8460bda"}
absl::StatusOr$<$ std::unique\_ptr$<$
[PredictStreamedContext](#classtensorflow_1_1serving_1_1PredictStreamedContext)
$>$ $>$ **PredictStreamed** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, absl::AnyInvocable$<$ void(absl::StatusOr$<$
PredictResponse $>$)$>$ response\_callback)

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_ae5ab51c82e79542dd5d6267de5210751\]]{#classtensorflow_1_1serving_1_1EmptyServable_ae5ab51c82e79542dd5d6267de5210751
label="classtensorflow_1_1serving_1_1EmptyServable_ae5ab51c82e79542dd5d6267de5210751"}
absl::Status **MultiInference** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const MultiInferenceRequest &request,
MultiInferenceResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1EmptyServable\_a67613065f15a837ed7bcad58cf5e7465\]]{#classtensorflow_1_1serving_1_1EmptyServable_a67613065f15a837ed7bcad58cf5e7465
label="classtensorflow_1_1serving_1_1EmptyServable_a67613065f15a837ed7bcad58cf5e7465"}
absl::Status **GetModelMetadata** (const GetModelMetadataRequest
&request, GetModelMetadataResponse $\ast$response) override

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/servable.h

tensorflow\_serving/servables/tensorflow/servable.cc
