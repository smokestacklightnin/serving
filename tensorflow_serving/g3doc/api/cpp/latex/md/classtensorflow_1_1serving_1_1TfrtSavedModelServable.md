::: {#classtensorflow_1_1serving_1_1TfrtSavedModelServable}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable"}

Inheritance diagram for tensorflow::serving::TfrtSavedModelServable:

![image](classtensorflow_1_1serving_1_1TfrtSavedModelServable__inherit__graph.pdf){width="223pt"}

Collaboration diagram for tensorflow::serving::TfrtSavedModelServable:

![image](classtensorflow_1_1serving_1_1TfrtSavedModelServable__coll__graph.pdf){width="223pt"}

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a45a5da4983f5fe6b862697fbce9350b4\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a45a5da4983f5fe6b862697fbce9350b4
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a45a5da4983f5fe6b862697fbce9350b4"}
**TfrtSavedModelServable** (absl::string\_view name, int64\_t version,
const TfrtSavedModelConfig &config, const SavedModelConfig
&model\_config, std::unique\_ptr$<$ tfrt\_stub::SavedModel $>$
saved\_model,
[ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$\ast$thread\_pool\_factory)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a1c030cd2189aff8a4efe44d9a028d0c4\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a1c030cd2189aff8a4efe44d9a028d0c4
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a1c030cd2189aff8a4efe44d9a028d0c4"}
**TfrtSavedModelServable** (absl::string\_view name, int64\_t version,
const TfrtSavedModelConfig &config, const SavedModelConfig
&model\_config, std::unique\_ptr$<$ tfrt\_stub::SavedModel $>$
saved\_model,
[ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$\ast$thread\_pool\_factory, std::function$<$ std::unique\_ptr$<$
[RequestRecorder](#classtensorflow_1_1serving_1_1RequestRecorder)
$>$([TfrtSavedModelServable](#classtensorflow_1_1serving_1_1TfrtSavedModelServable)
&)$>$ recorder\_creator)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a2145a828680d89213120ee5b40ecef7a\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a2145a828680d89213120ee5b40ecef7a
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a2145a828680d89213120ee5b40ecef7a"}
absl::Status **Classify** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const ClassificationRequest &request,
ClassificationResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a19543571e73874c4a49383795429a40f\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a19543571e73874c4a49383795429a40f
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a19543571e73874c4a49383795429a40f"}
absl::Status **Regress** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const RegressionRequest &request, RegressionResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a6009af9816f87208564f9e6aa9c20d25\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a6009af9816f87208564f9e6aa9c20d25
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a6009af9816f87208564f9e6aa9c20d25"}
absl::Status **Predict** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const PredictRequest &request, PredictResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_aab502e05af33a4cd61407c524090f8ea\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_aab502e05af33a4cd61407c524090f8ea
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_aab502e05af33a4cd61407c524090f8ea"}
absl::StatusOr$<$ std::unique\_ptr$<$
[PredictStreamedContext](#classtensorflow_1_1serving_1_1PredictStreamedContext)
$>$ $>$ **PredictStreamed** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, absl::AnyInvocable$<$ void(absl::StatusOr$<$
PredictResponse $>$)$>$ response\_callback) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_ac0ab6a2ac24d6f51903a9db4fd4a1bc2\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_ac0ab6a2ac24d6f51903a9db4fd4a1bc2
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_ac0ab6a2ac24d6f51903a9db4fd4a1bc2"}
absl::Status **MultiInference** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const MultiInferenceRequest &request,
MultiInferenceResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a4c444df2d52ea82108599685d07bf715\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a4c444df2d52ea82108599685d07bf715
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a4c444df2d52ea82108599685d07bf715"}
absl::Status **GetModelMetadata** (const GetModelMetadataRequest
&request, GetModelMetadataResponse $\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a264c963eaf59e0509f9fab620fd45c0c\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a264c963eaf59e0509f9fab620fd45c0c
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a264c963eaf59e0509f9fab620fd45c0c"}
bool **SupportsPaging** () const override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a9d654d28c40e514d38bef198edc230dc\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a9d654d28c40e514d38bef198edc230dc
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a9d654d28c40e514d38bef198edc230dc"}
absl::Status **Suspend** () override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_ae5fb11c47ab58187638b1af63753f133\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_ae5fb11c47ab58187638b1af63753f133
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_ae5fb11c47ab58187638b1af63753f133"}
absl::Status **Resume** () override

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a39d0e1fb10328be68f36f33a2f2fb678\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a39d0e1fb10328be68f36f33a2f2fb678
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a39d0e1fb10328be68f36f33a2f2fb678"}
tfrt\_stub::SavedModel & **saved\_model** () const

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a41c731f83584e3625a5c0a1e97a2ffcd\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a41c731f83584e3625a5c0a1e97a2ffcd
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a41c731f83584e3625a5c0a1e97a2ffcd"}
void **set\_resume\_fn** (absl::AnyInvocable$<$
absl::Status([TfrtSavedModelServable](#classtensorflow_1_1serving_1_1TfrtSavedModelServable)
$\ast$)$>$ resume\_fn)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelServable\_a7f27383faefb9a7dcc1f9122b323513a\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelServable_a7f27383faefb9a7dcc1f9122b323513a
label="classtensorflow_1_1serving_1_1TfrtSavedModelServable_a7f27383faefb9a7dcc1f9122b323513a"}
void **set\_suspend\_fn** (absl::AnyInvocable$<$
absl::Status([TfrtSavedModelServable](#classtensorflow_1_1serving_1_1TfrtSavedModelServable)
$\ast$)$>$ suspend\_fn)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tfrt\_servable.h

tensorflow\_serving/servables/tensorflow/tfrt\_servable.cc
