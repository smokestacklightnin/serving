::: {#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv}
:::

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv"}

Inheritance diagram for tensorflow::serving::TensorflowFileProbingEnv:

![image](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv__inherit__graph.pdf){width="226pt"}

Collaboration diagram for tensorflow::serving::TensorflowFileProbingEnv:

![image](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv__coll__graph.pdf){width="226pt"}

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\_a12bba3f6c90a6679ade80344107dae58\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a12bba3f6c90a6679ade80344107dae58
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a12bba3f6c90a6679ade80344107dae58"}
**TensorflowFileProbingEnv** (tensorflow::Env $\ast$env)

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\_ad39cb1752839ed46d10dd60259ec6a6c\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_ad39cb1752839ed46d10dd60259ec6a6c
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_ad39cb1752839ed46d10dd60259ec6a6c"}
Status **FileExists** (const string &fname) override

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\_af6ffae9a28d159bec5ea5e03d5449da0\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_af6ffae9a28d159bec5ea5e03d5449da0
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_af6ffae9a28d159bec5ea5e03d5449da0"}
Status **GetChildren** (const string &dir, std::vector$<$ string $>$
$\ast$children) override

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\_a80b0fe08039c7a291de8d94aebb5e4a1\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a80b0fe08039c7a291de8d94aebb5e4a1
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a80b0fe08039c7a291de8d94aebb5e4a1"}
Status **IsDirectory** (const string &fname) override

[\[classtensorflow\_1\_1serving\_1\_1TensorflowFileProbingEnv\_a851d7039f6c0d33f3175cc5fa0f5b8a9\]]{#classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a851d7039f6c0d33f3175cc5fa0f5b8a9
label="classtensorflow_1_1serving_1_1TensorflowFileProbingEnv_a851d7039f6c0d33f3175cc5fa0f5b8a9"}
Status **GetFileSize** (const string &fname, uint64\_t $\ast$file\_size)
override

The documentation for this class was generated from the following files:

tensorflow\_serving/util/file\_probing\_env.h

tensorflow\_serving/util/file\_probing\_env.cc
