::: {#classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerRequestLogger\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger"}

Inheritance diagram for
tensorflow::serving::test\_util::MockServerRequestLogger:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger__inherit__graph.pdf){width="246pt"}

Collaboration diagram for
tensorflow::serving::test\_util::MockServerRequestLogger:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger__coll__graph.pdf){width="246pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerRequestLogger\_a94be098880647ddcbbd65e52c8a0157f\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger_a94be098880647ddcbbd65e52c8a0157f
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger_a94be098880647ddcbbd65e52c8a0157f"}
**MOCK\_METHOD** (Status, Update,((const std::map$<$ string,
std::vector$<$ LoggingConfig $>$$>$ &logging\_config\_map)),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerRequestLogger\_ad74af5f8cdd064938d95ea33b599dcec\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger_ad74af5f8cdd064938d95ea33b599dcec
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger_ad74af5f8cdd064938d95ea33b599dcec"}
**MOCK\_METHOD** (Status, Log,(const google::protobuf::Message &request,
const google::protobuf::Message &response, const LogMetadata
&log\_metadata),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/core/test\_util/mock\_server\_request\_logger.h
