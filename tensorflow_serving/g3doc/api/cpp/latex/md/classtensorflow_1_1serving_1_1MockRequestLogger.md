::: {#classtensorflow_1_1serving_1_1MockRequestLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1MockRequestLogger\]]{#classtensorflow_1_1serving_1_1MockRequestLogger
label="classtensorflow_1_1serving_1_1MockRequestLogger"}

Inheritance diagram for tensorflow::serving::MockRequestLogger:

![image](classtensorflow_1_1serving_1_1MockRequestLogger__inherit__graph.pdf){width="244pt"}

Collaboration diagram for tensorflow::serving::MockRequestLogger:

![image](classtensorflow_1_1serving_1_1MockRequestLogger__coll__graph.pdf){width="244pt"}

[\[classtensorflow\_1\_1serving\_1\_1MockRequestLogger\_a15b40fbfe5393670dd37935962cfb7c6\]]{#classtensorflow_1_1serving_1_1MockRequestLogger_a15b40fbfe5393670dd37935962cfb7c6
label="classtensorflow_1_1serving_1_1MockRequestLogger_a15b40fbfe5393670dd37935962cfb7c6"}
**MockRequestLogger** (const LoggingConfig &logging\_config, const
std::vector$<$ string $>$ &saved\_model\_tags,
[LogCollector](#classtensorflow_1_1serving_1_1LogCollector)
$\ast$log\_collector, std::function$<$ void(void)$>$
notify\_destruction=std::function$<$ void(void)$>$())

[\[classtensorflow\_1\_1serving\_1\_1MockRequestLogger\_a620a487e76d43c4d59834be6ace37b3d\]]{#classtensorflow_1_1serving_1_1MockRequestLogger_a620a487e76d43c4d59834be6ace37b3d
label="classtensorflow_1_1serving_1_1MockRequestLogger_a620a487e76d43c4d59834be6ace37b3d"}
**MOCK\_METHOD** (Status, CreateLogMessage,(const
google::protobuf::Message &request, const google::protobuf::Message
&response, const LogMetadata &log\_metadata, std::unique\_ptr$<$
google::protobuf::Message $>$ $\ast$log),(override))

[\[classtensorflow\_1\_1serving\_1\_1MockRequestLogger\_a24cc08d3cec309d666ad05328950f555\]]{#classtensorflow_1_1serving_1_1MockRequestLogger_a24cc08d3cec309d666ad05328950f555
label="classtensorflow_1_1serving_1_1MockRequestLogger_a24cc08d3cec309d666ad05328950f555"}
**MOCK\_METHOD** (LogMetadata, FillLogMetadata,(const LogMetadata
&),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/core/test\_util/mock\_request\_logger.h
