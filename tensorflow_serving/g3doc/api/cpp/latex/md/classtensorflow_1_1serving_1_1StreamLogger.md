::: {#classtensorflow_1_1serving_1_1StreamLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\]]{#classtensorflow_1_1serving_1_1StreamLogger
label="classtensorflow_1_1serving_1_1StreamLogger"}

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\_a7befdae936105bf5c7067bfacb56d5c5\]]{#classtensorflow_1_1serving_1_1StreamLogger_a7befdae936105bf5c7067bfacb56d5c5
label="classtensorflow_1_1serving_1_1StreamLogger_a7befdae936105bf5c7067bfacb56d5c5"}
using **LogMessageFn** = std::function$<$ absl::Status(const
google::protobuf::Message &)$>$

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\_a8c2c225e20109c9e9e01ef44c27f14ef\]]{#classtensorflow_1_1serving_1_1StreamLogger_a8c2c225e20109c9e9e01ef44c27f14ef
label="classtensorflow_1_1serving_1_1StreamLogger_a8c2c225e20109c9e9e01ef44c27f14ef"}
virtual void **LogStreamRequest** (Request request)=0

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\_a1805308e6736793e5365245b89601153\]]{#classtensorflow_1_1serving_1_1StreamLogger_a1805308e6736793e5365245b89601153
label="classtensorflow_1_1serving_1_1StreamLogger_a1805308e6736793e5365245b89601153"}
virtual void **LogStreamResponse** (Response response)=0

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\_af44598e443cfa821c44f4a9b5cb145b0\]]{#classtensorflow_1_1serving_1_1StreamLogger_af44598e443cfa821c44f4a9b5cb145b0
label="classtensorflow_1_1serving_1_1StreamLogger_af44598e443cfa821c44f4a9b5cb145b0"}
void **AddLogCallback** (const LogMetadata &log\_metadata, LogMessageFn
log\_message\_fn)

[\[classtensorflow\_1\_1serving\_1\_1StreamLogger\_a9a856fc3f04791d758a26d8a9e9de7fb\]]{#classtensorflow_1_1serving_1_1StreamLogger_a9a856fc3f04791d758a26d8a9e9de7fb
label="classtensorflow_1_1serving_1_1StreamLogger_a9a856fc3f04791d758a26d8a9e9de7fb"}
absl::Status **LogMessage** ()

The documentation for this class was generated from the following file:

tensorflow\_serving/core/stream\_logger.h
