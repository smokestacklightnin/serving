::: {#classtensorflow_1_1serving_1_1ServerRequestLogger}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger
label="classtensorflow_1_1serving_1_1ServerRequestLogger"}

Inheritance diagram for tensorflow::serving::ServerRequestLogger:

![image](classtensorflow_1_1serving_1_1ServerRequestLogger__inherit__graph.pdf){width="246pt"}

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a6e1a5971a30dfc712a2567817f9b76e9\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a6e1a5971a30dfc712a2567817f9b76e9
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a6e1a5971a30dfc712a2567817f9b76e9"}
using **LoggerCreator** = std::function$<$ Status(const LoggingConfig
&logging\_config, std::shared\_ptr$<$
[RequestLogger](#classtensorflow_1_1serving_1_1RequestLogger) $>$
$\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a5ff117d28de0159ecc181f6bc85f7d24\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a5ff117d28de0159ecc181f6bc85f7d24
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a5ff117d28de0159ecc181f6bc85f7d24"}
template$<$typename Request , typename Response $>$ \
using **CreateStreamLoggerFn** = std::function$<$ std::unique\_ptr$<$
[StreamLogger](#classtensorflow_1_1serving_1_1StreamLogger)$<$ Request,
Response $>$ $>$()$>$

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a4ba87444abb14576034495c7106d4880\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a4ba87444abb14576034495c7106d4880
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a4ba87444abb14576034495c7106d4880"}
virtual Status **Update** (const std::map$<$ string, std::vector$<$
LoggingConfig $>$$>$ &logging\_config\_map)

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a5ee712900d7f9aa63ad6e31c1d84d257\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a5ee712900d7f9aa63ad6e31c1d84d257
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a5ee712900d7f9aa63ad6e31c1d84d257"}
virtual Status **Log** (const google::protobuf::Message &request, const
google::protobuf::Message &response, const LogMetadata &log\_metadata)

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a5a54da9c036e4115ac69bb5b22e5ed53\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a5a54da9c036e4115ac69bb5b22e5ed53
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a5a54da9c036e4115ac69bb5b22e5ed53"}
template$<$typename Request , typename Response $>$ \
std::unique\_ptr$<$
[StreamLogger](#classtensorflow_1_1serving_1_1StreamLogger)$<$ Request,
Response $>$ $>$ **StartLoggingStream** (const LogMetadata
&log\_metadata, CreateStreamLoggerFn$<$ Request, Response $>$
create\_stream\_logger\_fn)

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_a2de29105fb583ca1ac99d224efe2d322\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_a2de29105fb583ca1ac99d224efe2d322
label="classtensorflow_1_1serving_1_1ServerRequestLogger_a2de29105fb583ca1ac99d224efe2d322"}
static Status **Create** (LoggerCreator request\_logger\_creator,
std::unique\_ptr$<$
[ServerRequestLogger](#classtensorflow_1_1serving_1_1ServerRequestLogger)
$>$ $\ast$server\_request\_logger)

[\[classtensorflow\_1\_1serving\_1\_1ServerRequestLogger\_ab234ed5ecfb8f81b1d3ce1de2f2b8f33\]]{#classtensorflow_1_1serving_1_1ServerRequestLogger_ab234ed5ecfb8f81b1d3ce1de2f2b8f33
label="classtensorflow_1_1serving_1_1ServerRequestLogger_ab234ed5ecfb8f81b1d3ce1de2f2b8f33"}
**ServerRequestLogger** (LoggerCreator request\_logger\_creator)

The documentation for this class was generated from the following files:

tensorflow\_serving/core/server\_request\_logger.h

tensorflow\_serving/core/server\_request\_logger.cc
