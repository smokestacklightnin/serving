::: {#classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner}
:::

[\[classtensorflow\_1\_1serving\_1\_1TensorFlowMultiInferenceRunner\]]{#classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner
label="classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner"}

[\[classtensorflow\_1\_1serving\_1\_1TensorFlowMultiInferenceRunner\_af6dc0a8024a45ea4705403a0e9c45edc\]]{#classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_af6dc0a8024a45ea4705403a0e9c45edc
label="classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_af6dc0a8024a45ea4705403a0e9c45edc"}
**TensorFlowMultiInferenceRunner** (Session $\ast$session, const
MetaGraphDef $\ast$meta\_graph\_def)

[\[classtensorflow\_1\_1serving\_1\_1TensorFlowMultiInferenceRunner\_a8a39e31cd3012405ebc38a714ec35ce7\]]{#classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_a8a39e31cd3012405ebc38a714ec35ce7
label="classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_a8a39e31cd3012405ebc38a714ec35ce7"}
**TensorFlowMultiInferenceRunner** (Session $\ast$session, const
MetaGraphDef $\ast$meta\_graph\_def, absl::optional$<$ int64\_t $>$
servable\_version, const thread::ThreadPoolOptions
&thread\_pool\_options=thread::ThreadPoolOptions())

[\[classtensorflow\_1\_1serving\_1\_1TensorFlowMultiInferenceRunner\_acd77005f53ee1ad2575f08abdd52eff0\]]{#classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_acd77005f53ee1ad2575f08abdd52eff0
label="classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_acd77005f53ee1ad2575f08abdd52eff0"}
Status **Infer** (const RunOptions &run\_options, const
MultiInferenceRequest &request, MultiInferenceResponse $\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/multi\_inference.h

tensorflow\_serving/servables/tensorflow/multi\_inference.cc
