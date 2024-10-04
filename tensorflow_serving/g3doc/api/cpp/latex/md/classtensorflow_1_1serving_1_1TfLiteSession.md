::: {#classtensorflow_1_1serving_1_1TfLiteSession}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\]]{#classtensorflow_1_1serving_1_1TfLiteSession
label="classtensorflow_1_1serving_1_1TfLiteSession"}

Inheritance diagram for tensorflow::serving::TfLiteSession:

![image](classtensorflow_1_1serving_1_1TfLiteSession__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::TfLiteSession:

![image](classtensorflow_1_1serving_1_1TfLiteSession__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_af56c4d888c6d9b14fa7f93c3ebf2aec9\]]{#classtensorflow_1_1serving_1_1TfLiteSession_af56c4d888c6d9b14fa7f93c3ebf2aec9
label="classtensorflow_1_1serving_1_1TfLiteSession_af56c4d888c6d9b14fa7f93c3ebf2aec9"}
Status **Run** (const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs, const std::vector$<$ string $>$ &output\_tensor\_names, const
std::vector$<$ string $>$ &target\_node\_names, std::vector$<$ Tensor
$>$ $\ast$outputs) override

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_ad2a1c5664ab495ba320e2517b4d09ff2\]]{#classtensorflow_1_1serving_1_1TfLiteSession_ad2a1c5664ab495ba320e2517b4d09ff2
label="classtensorflow_1_1serving_1_1TfLiteSession_ad2a1c5664ab495ba320e2517b4d09ff2"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata) override

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_a5fa1a7c147c933e0316a54789cc513d3\]]{#classtensorflow_1_1serving_1_1TfLiteSession_a5fa1a7c147c933e0316a54789cc513d3
label="classtensorflow_1_1serving_1_1TfLiteSession_a5fa1a7c147c933e0316a54789cc513d3"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata, const thread::ThreadPoolOptions
&thread\_pool\_options) override

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_ad869ad828216829a1eb6dfd95b8ddbff\]]{#classtensorflow_1_1serving_1_1TfLiteSession_ad869ad828216829a1eb6dfd95b8ddbff
label="classtensorflow_1_1serving_1_1TfLiteSession_ad869ad828216829a1eb6dfd95b8ddbff"}
Status **ListDevices** (std::vector$<$ DeviceAttributes $>$
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_aac1155c582aa38320c71b822fa3bad7c\]]{#classtensorflow_1_1serving_1_1TfLiteSession_aac1155c582aa38320c71b822fa3bad7c
label="classtensorflow_1_1serving_1_1TfLiteSession_aac1155c582aa38320c71b822fa3bad7c"}
Status **SetScheduler** (const SchedulerCreator &scheduler\_creator,
const BasicBatchScheduler$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
$>$::Options &options)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_aabe9a6b7e0aa93a3eb265f098f5ac2b8\]]{#classtensorflow_1_1serving_1_1TfLiteSession_aabe9a6b7e0aa93a3eb265f098f5ac2b8
label="classtensorflow_1_1serving_1_1TfLiteSession_aabe9a6b7e0aa93a3eb265f098f5ac2b8"}
BasicBatchScheduler$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
$>$::Options **GetSchedulerOptions** ()

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_a15f669ebbee48bd099d5ef6cf848c75c\]]{#classtensorflow_1_1serving_1_1TfLiteSession_a15f669ebbee48bd099d5ef6cf848c75c
label="classtensorflow_1_1serving_1_1TfLiteSession_a15f669ebbee48bd099d5ef6cf848c75c"}
static Status **Create** (string &&buffer, const SessionOptions
&options, int num\_pools, int num\_interpreters\_per\_pool,
std::unique\_ptr$<$
[TfLiteSession](#classtensorflow_1_1serving_1_1TfLiteSession) $>$
$\ast$tflite\_session, ::google::protobuf::Map$<$ string, SignatureDef
$>$ $\ast$signatures)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_a691ec11977b3a1b5cb325ca2f771f9eb\]]{#classtensorflow_1_1serving_1_1TfLiteSession_a691ec11977b3a1b5cb325ca2f771f9eb
label="classtensorflow_1_1serving_1_1TfLiteSession_a691ec11977b3a1b5cb325ca2f771f9eb"}
static Status **CreateDefaultBasicBatchScheduler** (const
BasicBatchScheduler$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
$>$::Options &options, std::function$<$ void(std::unique\_ptr$<$
Batch$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
$>$$>$)$>$ process\_batch\_callback, std::unique\_ptr$<$
BasicBatchScheduler$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) $>$$>$
$\ast$batch\_scheduler)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteSession\_ae296cc32dbee906cc35d78e5ebf280ff\]]{#classtensorflow_1_1serving_1_1TfLiteSession_ae296cc32dbee906cc35d78e5ebf280ff
label="classtensorflow_1_1serving_1_1TfLiteSession_ae296cc32dbee906cc35d78e5ebf280ff"}
static Status **SplitTfLiteInputTask** (std::unique\_ptr$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) $>$
$\ast$input\_task\_ptr, int open\_batch\_remaining\_slot, int
max\_batch\_size, std::vector$<$ std::unique\_ptr$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) $>$$>$
$\ast$output\_tasks)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tflite\_session.h

tensorflow\_serving/servables/tensorflow/tflite\_session.cc
