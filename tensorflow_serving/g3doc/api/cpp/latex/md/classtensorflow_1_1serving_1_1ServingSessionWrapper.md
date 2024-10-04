::: {#classtensorflow_1_1serving_1_1ServingSessionWrapper}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper
label="classtensorflow_1_1serving_1_1ServingSessionWrapper"}

\#include $<$serving\_session.h$>$

Inheritance diagram for tensorflow::serving::ServingSessionWrapper:

![image](classtensorflow_1_1serving_1_1ServingSessionWrapper__inherit__graph.pdf){width="246pt"}

Collaboration diagram for tensorflow::serving::ServingSessionWrapper:

![image](classtensorflow_1_1serving_1_1ServingSessionWrapper__coll__graph.pdf){width="218pt"}

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\_ad111ab802638515a20fd51cadc8a48af\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper_ad111ab802638515a20fd51cadc8a48af
label="classtensorflow_1_1serving_1_1ServingSessionWrapper_ad111ab802638515a20fd51cadc8a48af"}
**ServingSessionWrapper** (std::unique\_ptr$<$ Session $>$ wrapped)

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\_a09fae4571d96964ac0340e2aaf03f5de\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper_a09fae4571d96964ac0340e2aaf03f5de
label="classtensorflow_1_1serving_1_1ServingSessionWrapper_a09fae4571d96964ac0340e2aaf03f5de"}
Status **Run** (const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs, const std::vector$<$ string $>$ &output\_tensor\_names, const
std::vector$<$ string $>$ &target\_node\_names, std::vector$<$ Tensor
$>$ $\ast$outputs) override

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\_a4197a44975180c105c6766208712bec4\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper_a4197a44975180c105c6766208712bec4
label="classtensorflow_1_1serving_1_1ServingSessionWrapper_a4197a44975180c105c6766208712bec4"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata) override

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\_a357c8d5be187514b042f9f20fdfa657e\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper_a357c8d5be187514b042f9f20fdfa657e
label="classtensorflow_1_1serving_1_1ServingSessionWrapper_a357c8d5be187514b042f9f20fdfa657e"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata, const thread::ThreadPoolOptions
&thread\_pool\_options) override

[\[classtensorflow\_1\_1serving\_1\_1ServingSessionWrapper\_a33d7ad5de8156afa0563a21e25963d17\]]{#classtensorflow_1_1serving_1_1ServingSessionWrapper_a33d7ad5de8156afa0563a21e25963d17
label="classtensorflow_1_1serving_1_1ServingSessionWrapper_a33d7ad5de8156afa0563a21e25963d17"}
Status **ListDevices** (std::vector$<$ DeviceAttributes $>$
$\ast$response) override

A [ServingSession](#classtensorflow_1_1serving_1_1ServingSession) that
wraps a given Session, and blocks all calls other than Run().

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/serving\_session.h
