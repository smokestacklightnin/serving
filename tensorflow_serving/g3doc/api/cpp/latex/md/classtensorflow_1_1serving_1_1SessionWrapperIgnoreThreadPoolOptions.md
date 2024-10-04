::: {#classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions}
:::

[\[classtensorflow\_1\_1serving\_1\_1SessionWrapperIgnoreThreadPoolOptions\]]{#classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions
label="classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions"}

Inheritance diagram for
tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions:

![image](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions__inherit__graph.pdf){width="246pt"}

Collaboration diagram for
tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions:

![image](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions__coll__graph.pdf){width="246pt"}

[\[classtensorflow\_1\_1serving\_1\_1SessionWrapperIgnoreThreadPoolOptions\_a0a8e378dcb31a61587dcb5fa4d5a8bcb\]]{#classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions_a0a8e378dcb31a61587dcb5fa4d5a8bcb
label="classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions_a0a8e378dcb31a61587dcb5fa4d5a8bcb"}
**SessionWrapperIgnoreThreadPoolOptions** (std::unique\_ptr$<$ Session
$>$ wrapped)

[\[classtensorflow\_1\_1serving\_1\_1SessionWrapperIgnoreThreadPoolOptions\_a209882ca7297ac45cf5b53389bbd2408\]]{#classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions_a209882ca7297ac45cf5b53389bbd2408
label="classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions_a209882ca7297ac45cf5b53389bbd2408"}
Status **Run** (const RunOptions &run\_options, const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs, const std::vector$<$ string
$>$ &output\_tensor\_names, const std::vector$<$ string $>$
&target\_node\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
RunMetadata $\ast$run\_metadata, const thread::ThreadPoolOptions
&thread\_pool\_options) override

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/serving\_session.h
