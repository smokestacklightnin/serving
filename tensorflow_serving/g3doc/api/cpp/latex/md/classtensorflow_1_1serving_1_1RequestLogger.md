::: {#classtensorflow_1_1serving_1_1RequestLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\]]{#classtensorflow_1_1serving_1_1RequestLogger
label="classtensorflow_1_1serving_1_1RequestLogger"}

Inheritance diagram for tensorflow::serving::RequestLogger:

![image](classtensorflow_1_1serving_1_1RequestLogger__inherit__graph.pdf){width="244pt"}

Collaboration diagram for tensorflow::serving::RequestLogger:

![image](classtensorflow_1_1serving_1_1RequestLogger__coll__graph.pdf){width="244pt"}

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\_a04a7f5a2c33bd423a346074b2b35ba23\]]{#classtensorflow_1_1serving_1_1RequestLogger_a04a7f5a2c33bd423a346074b2b35ba23
label="classtensorflow_1_1serving_1_1RequestLogger_a04a7f5a2c33bd423a346074b2b35ba23"}
template$<$typename Request , typename Response $>$ \
using **GetStreamLoggerFn** = std::function$<$
[StreamLogger](#classtensorflow_1_1serving_1_1StreamLogger)$<$ Request,
Response $>$ $\ast$()$>$

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\_ad8ef1286602adae51e408c159b46879a\]]{#classtensorflow_1_1serving_1_1RequestLogger_ad8ef1286602adae51e408c159b46879a
label="classtensorflow_1_1serving_1_1RequestLogger_ad8ef1286602adae51e408c159b46879a"}
**RequestLogger** (const LoggingConfig &logging\_config, const
std::vector$<$ string $>$ &saved\_model\_tags, std::unique\_ptr$<$
[LogCollector](#classtensorflow_1_1serving_1_1LogCollector) $>$
log\_collector)

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\_a8b5584be6edc378d490209385cdc3686\]]{#classtensorflow_1_1serving_1_1RequestLogger_a8b5584be6edc378d490209385cdc3686
label="classtensorflow_1_1serving_1_1RequestLogger_a8b5584be6edc378d490209385cdc3686"}
Status **Log** (const google::protobuf::Message &request, const
google::protobuf::Message &response, const LogMetadata &log\_metadata)

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\_ad611f5044b2ada63755d3b1fc6c04d85\]]{#classtensorflow_1_1serving_1_1RequestLogger_ad611f5044b2ada63755d3b1fc6c04d85
label="classtensorflow_1_1serving_1_1RequestLogger_ad611f5044b2ada63755d3b1fc6c04d85"}
template$<$typename Request , typename Response $>$ \
void **MaybeStartLoggingStream** (const LogMetadata &log\_metadata,
GetStreamLoggerFn$<$ Request, Response $>$ get\_stream\_logger\_fn)

[\[classtensorflow\_1\_1serving\_1\_1RequestLogger\_a3ba14be0732fe75d64dac77aa0e05076\]]{#classtensorflow_1_1serving_1_1RequestLogger_a3ba14be0732fe75d64dac77aa0e05076
label="classtensorflow_1_1serving_1_1RequestLogger_a3ba14be0732fe75d64dac77aa0e05076"}
const LoggingConfig & **logging\_config** () const

The documentation for this class was generated from the following files:

tensorflow\_serving/core/request\_logger.h

tensorflow\_serving/core/request\_logger.cc
