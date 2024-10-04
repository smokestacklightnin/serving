::: {#classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockPredictionStreamLogger\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger
label="classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger"}

Inheritance diagram for
tensorflow::serving::test\_util::MockPredictionStreamLogger:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger__inherit__graph.pdf){width="259pt"}

Collaboration diagram for
tensorflow::serving::test\_util::MockPredictionStreamLogger:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger__coll__graph.pdf){width="259pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockPredictionStreamLogger\_a0011705174ca6143b7346909c4dffc34\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_a0011705174ca6143b7346909c4dffc34
label="classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_a0011705174ca6143b7346909c4dffc34"}
**MOCK\_METHOD** (void, LogStreamRequest,(PredictRequest),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockPredictionStreamLogger\_a0f5c029ae8d4d74157e5e37a760cfb7c\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_a0f5c029ae8d4d74157e5e37a760cfb7c
label="classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_a0f5c029ae8d4d74157e5e37a760cfb7c"}
**MOCK\_METHOD** (void, LogStreamResponse,(PredictResponse),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockPredictionStreamLogger\_acd4a556bbde2a9a2aa2ad49c03b0e3b4\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_acd4a556bbde2a9a2aa2ad49c03b0e3b4
label="classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger_acd4a556bbde2a9a2aa2ad49c03b0e3b4"}
**MOCK\_METHOD** (absl::Status, CreateLogMessage,(const LogMetadata &,
std::unique\_ptr$<$ google::protobuf::Message $>$ $\ast$),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/core/test\_util/mock\_prediction\_stream\_logger.h
