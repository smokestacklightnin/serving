::: {#classtensorflow_1_1serving_1_1RemotePredictOp}
:::

[\[classtensorflow\_1\_1serving\_1\_1RemotePredictOp\]]{#classtensorflow_1_1serving_1_1RemotePredictOp
label="classtensorflow_1_1serving_1_1RemotePredictOp"}

Inheritance diagram for tensorflow::serving::RemotePredictOp$<$
PredictionServiceStubType $>$:

![image](classtensorflow_1_1serving_1_1RemotePredictOp__inherit__graph.pdf){width="248pt"}

Collaboration diagram for tensorflow::serving::RemotePredictOp$<$
PredictionServiceStubType $>$:

![image](classtensorflow_1_1serving_1_1RemotePredictOp__coll__graph.pdf){width="248pt"}

[\[classtensorflow\_1\_1serving\_1\_1RemotePredictOp\_a1219bbca9f6cc6cd5cac8cd27c81f179\]]{#classtensorflow_1_1serving_1_1RemotePredictOp_a1219bbca9f6cc6cd5cac8cd27c81f179
label="classtensorflow_1_1serving_1_1RemotePredictOp_a1219bbca9f6cc6cd5cac8cd27c81f179"}
**RemotePredictOp** (OpKernelConstruction $\ast$context)

[\[classtensorflow\_1\_1serving\_1\_1RemotePredictOp\_abc1bdb8013d8224f00af14b0f386ebc6\]]{#classtensorflow_1_1serving_1_1RemotePredictOp_abc1bdb8013d8224f00af14b0f386ebc6
label="classtensorflow_1_1serving_1_1RemotePredictOp_abc1bdb8013d8224f00af14b0f386ebc6"}
void **ComputeAsync** (OpKernelContext $\ast$context, DoneCallback done)
override

[\[classtensorflow\_1\_1serving\_1\_1RemotePredictOp\_a54d416cab723016f2d05492dd72d6acd\]]{#classtensorflow_1_1serving_1_1RemotePredictOp_a54d416cab723016f2d05492dd72d6acd
label="classtensorflow_1_1serving_1_1RemotePredictOp_a54d416cab723016f2d05492dd72d6acd"}
void **PostProcessResponse** (OpKernelContext $\ast$context,
PredictResponse $\ast$response, const absl::Status &rpc\_status, bool
fail\_op\_on\_rpc\_error, TTypes$<$ const tstring $>$::Flat
output\_tensor\_aliases, DoneCallback rpc\_done)

The documentation for this class was generated from the following file:

tensorflow\_serving/experimental/tensorflow/ops/remote\_predict/kernels/remote\_predict\_op\_kernel.h
