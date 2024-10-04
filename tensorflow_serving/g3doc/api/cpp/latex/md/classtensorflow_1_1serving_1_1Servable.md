::: {#classtensorflow_1_1serving_1_1Servable}
:::

[\[classtensorflow\_1\_1serving\_1\_1Servable\]]{#classtensorflow_1_1serving_1_1Servable
label="classtensorflow_1_1serving_1_1Servable"}

Inheritance diagram for tensorflow::serving::Servable:

![image](classtensorflow_1_1serving_1_1Servable__inherit__graph.pdf){width="350pt"}

[\[classtensorflow\_1\_1serving\_1\_1Servable\_aae1542327fc78499507b9a4f2fa75571\]]{#classtensorflow_1_1serving_1_1Servable_aae1542327fc78499507b9a4f2fa75571
label="classtensorflow_1_1serving_1_1Servable_aae1542327fc78499507b9a4f2fa75571"}
using **RunOptions** =
[tensorflow::serving::servables::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a38b7c413e4c12e95fdc9680b2888b8a0\]]{#classtensorflow_1_1serving_1_1Servable_a38b7c413e4c12e95fdc9680b2888b8a0
label="classtensorflow_1_1serving_1_1Servable_a38b7c413e4c12e95fdc9680b2888b8a0"}
**Servable** (absl::string\_view name, int64\_t version, bool
is\_critical=false)

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a393737a4803a6ba744f9eedd132ddb65\]]{#classtensorflow_1_1serving_1_1Servable_a393737a4803a6ba744f9eedd132ddb65
label="classtensorflow_1_1serving_1_1Servable_a393737a4803a6ba744f9eedd132ddb65"}
absl::string\_view **name** () const

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a6f4b30e48d3a5ad24899492f88ec4e1a\]]{#classtensorflow_1_1serving_1_1Servable_a6f4b30e48d3a5ad24899492f88ec4e1a
label="classtensorflow_1_1serving_1_1Servable_a6f4b30e48d3a5ad24899492f88ec4e1a"}
int64\_t **version** () const

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a64816027ce86cefe5a07649c40b8f235\]]{#classtensorflow_1_1serving_1_1Servable_a64816027ce86cefe5a07649c40b8f235
label="classtensorflow_1_1serving_1_1Servable_a64816027ce86cefe5a07649c40b8f235"}
bool **IsCritical** () const

[\[classtensorflow\_1\_1serving\_1\_1Servable\_aa3aaf988243ae1a3ea994609aefc2cf3\]]{#classtensorflow_1_1serving_1_1Servable_aa3aaf988243ae1a3ea994609aefc2cf3
label="classtensorflow_1_1serving_1_1Servable_aa3aaf988243ae1a3ea994609aefc2cf3"}
virtual absl::Status **Classify** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const ClassificationRequest &request,
ClassificationResponse $\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a9d377f74c29f65fb94f3220350aebf94\]]{#classtensorflow_1_1serving_1_1Servable_a9d377f74c29f65fb94f3220350aebf94
label="classtensorflow_1_1serving_1_1Servable_a9d377f74c29f65fb94f3220350aebf94"}
virtual absl::Status **Regress** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const RegressionRequest &request, RegressionResponse
$\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a56da3044f582c699b457cbe53f4880ff\]]{#classtensorflow_1_1serving_1_1Servable_a56da3044f582c699b457cbe53f4880ff
label="classtensorflow_1_1serving_1_1Servable_a56da3044f582c699b457cbe53f4880ff"}
virtual absl::Status **Predict** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const PredictRequest &request, PredictResponse
$\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a6d2e1d7315e0016e745a9ddc49ab60df\]]{#classtensorflow_1_1serving_1_1Servable_a6d2e1d7315e0016e745a9ddc49ab60df
label="classtensorflow_1_1serving_1_1Servable_a6d2e1d7315e0016e745a9ddc49ab60df"}
virtual absl::StatusOr$<$ std::unique\_ptr$<$
[PredictStreamedContext](#classtensorflow_1_1serving_1_1PredictStreamedContext)
$>$ $>$ **PredictStreamed** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, absl::AnyInvocable$<$ void(absl::StatusOr$<$
PredictResponse $>$)$>$ response\_callback)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a0a40bd468c4b10f28000f806f66ab321\]]{#classtensorflow_1_1serving_1_1Servable_a0a40bd468c4b10f28000f806f66ab321
label="classtensorflow_1_1serving_1_1Servable_a0a40bd468c4b10f28000f806f66ab321"}
virtual absl::Status **MultiInference** (const
[RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, const MultiInferenceRequest &request,
MultiInferenceResponse $\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a157d7274afc086fa899e8b179c110fcd\]]{#classtensorflow_1_1serving_1_1Servable_a157d7274afc086fa899e8b179c110fcd
label="classtensorflow_1_1serving_1_1Servable_a157d7274afc086fa899e8b179c110fcd"}
virtual absl::Status **GetModelMetadata** (const GetModelMetadataRequest
&request, GetModelMetadataResponse $\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a09a3e5a158832c0d0abf4a837e4e250c\]]{#classtensorflow_1_1serving_1_1Servable_a09a3e5a158832c0d0abf4a837e4e250c
label="classtensorflow_1_1serving_1_1Servable_a09a3e5a158832c0d0abf4a837e4e250c"}
virtual bool **SupportsPaging** () const

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a0f14477ac47c94af784ef19410b5637d\]]{#classtensorflow_1_1serving_1_1Servable_a0f14477ac47c94af784ef19410b5637d
label="classtensorflow_1_1serving_1_1Servable_a0f14477ac47c94af784ef19410b5637d"}
virtual absl::Status **Suspend** ()

[\[classtensorflow\_1\_1serving\_1\_1Servable\_a5714db8d9e57bef3af74926977677b78\]]{#classtensorflow_1_1serving_1_1Servable_a5714db8d9e57bef3af74926977677b78
label="classtensorflow_1_1serving_1_1Servable_a5714db8d9e57bef3af74926977677b78"}
virtual absl::Status **Resume** ()

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/servable.h

tensorflow\_serving/servables/tensorflow/servable.cc
