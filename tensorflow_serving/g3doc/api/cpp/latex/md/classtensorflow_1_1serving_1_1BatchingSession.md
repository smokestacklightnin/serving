::: {#classtensorflow_1_1serving_1_1BatchingSession}
:::

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\]]{#classtensorflow_1_1serving_1_1BatchingSession
label="classtensorflow_1_1serving_1_1BatchingSession"}

Inheritance diagram for tensorflow::serving::BatchingSession:

![image](classtensorflow_1_1serving_1_1BatchingSession__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::BatchingSession:

![image](classtensorflow_1_1serving_1_1BatchingSession__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_ac226e7586884f57ec81ee346f8342eb2\]]{#classtensorflow_1_1serving_1_1BatchingSession_ac226e7586884f57ec81ee346f8342eb2
label="classtensorflow_1_1serving_1_1BatchingSession_ac226e7586884f57ec81ee346f8342eb2"}
Status **Run** (const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs, const std::vector$<$ string $>$ &output\_tensor\_names, const
std::vector$<$ string $>$ &target\_node\_names, std::vector$<$ Tensor
$>$ $\ast$outputs) override

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_afe8ed5493bda24f823bff4684e2b3039\]]{#classtensorflow_1_1serving_1_1BatchingSession_afe8ed5493bda24f823bff4684e2b3039
label="classtensorflow_1_1serving_1_1BatchingSession_afe8ed5493bda24f823bff4684e2b3039"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata) override

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_abb57b98a930c1bbd131c8b9b57619b23\]]{#classtensorflow_1_1serving_1_1BatchingSession_abb57b98a930c1bbd131c8b9b57619b23
label="classtensorflow_1_1serving_1_1BatchingSession_abb57b98a930c1bbd131c8b9b57619b23"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata, const thread::ThreadPoolOptions
&thread\_pool\_options) override

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_a3a8028fd4b8098d3065e5fa0fbb7620e\]]{#classtensorflow_1_1serving_1_1BatchingSession_a3a8028fd4b8098d3065e5fa0fbb7620e
label="classtensorflow_1_1serving_1_1BatchingSession_a3a8028fd4b8098d3065e5fa0fbb7620e"}
Status **ListDevices** (std::vector$<$ DeviceAttributes $>$
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_a5fe13d33b2144aa27782caaea1527e13\]]{#classtensorflow_1_1serving_1_1BatchingSession_a5fe13d33b2144aa27782caaea1527e13
label="classtensorflow_1_1serving_1_1BatchingSession_a5fe13d33b2144aa27782caaea1527e13"}
static Status **Create** (const
[BatchingSessionOptions](#structtensorflow_1_1serving_1_1BatchingOptions)
&options, std::unique\_ptr$<$ Session $>$ wrapped, const std::vector$<$
[SignatureWithBatchingSessionSchedulerCreator](#structtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator)
$>$ &signatures\_with\_scheduler\_creators, const std::string
&thread\_pool\_name, std::unique\_ptr$<$
[BatchingSession](#classtensorflow_1_1serving_1_1BatchingSession) $>$
$\ast$result)

[\[classtensorflow\_1\_1serving\_1\_1BatchingSession\_a601e5e5c631648662e5c5a1c180a5a4f\]]{#classtensorflow_1_1serving_1_1BatchingSession_a601e5e5c631648662e5c5a1c180a5a4f
label="classtensorflow_1_1serving_1_1BatchingSession_a601e5e5c631648662e5c5a1c180a5a4f"}
static Status **Create** (const
[BatchingSessionOptions](#structtensorflow_1_1serving_1_1BatchingOptions)
&options, std::unique\_ptr$<$ Session $>$ wrapped, const std::vector$<$
[SignatureWithBatchingSessionSchedulerCreator](#structtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator)
$>$ &signatures\_with\_scheduler\_creators,
BatchingSessionSchedulerCreator default\_creator, const std::string
&thread\_pool\_name, std::unique\_ptr$<$
[BatchingSession](#classtensorflow_1_1serving_1_1BatchingSession) $>$
$\ast$result)

The documentation for this class was generated from the following file:

tensorflow\_serving/batching/batching\_session.cc
