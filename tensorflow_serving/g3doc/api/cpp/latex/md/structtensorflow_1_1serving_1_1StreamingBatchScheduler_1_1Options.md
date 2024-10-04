::: {#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options"}

Collaboration diagram for
tensorflow::serving::StreamingBatchScheduler$<$ TaskType $>$::Options:

![image](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options__coll__graph.pdf){width="229pt"}

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_a8b8b4798d06b0b5d035a230d9fe4b10e\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a8b8b4798d06b0b5d035a230d9fe4b10e
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a8b8b4798d06b0b5d035a230d9fe4b10e"}
size\_t **max\_batch\_size** = 1000

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_ad8b4e6a1dcd8e60b0c2dbe5c2a19ae7d\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_ad8b4e6a1dcd8e60b0c2dbe5c2a19ae7d
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_ad8b4e6a1dcd8e60b0c2dbe5c2a19ae7d"}
int64\_t **batch\_timeout\_micros** = 0

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_a638bed8d2a962ff4fa4f18e25c3408b7\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a638bed8d2a962ff4fa4f18e25c3408b7
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a638bed8d2a962ff4fa4f18e25c3408b7"}
string **thread\_pool\_name** = '̈batch\_threads'̈

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_a9281576636cf09ce9dc817b1bbdaee4b\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a9281576636cf09ce9dc817b1bbdaee4b
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_a9281576636cf09ce9dc817b1bbdaee4b"}
int **num\_batch\_threads** = port::MaxParallelism()

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_ae8dc0bcfc47c0d41f390204300eb9d9b\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_ae8dc0bcfc47c0d41f390204300eb9d9b
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_ae8dc0bcfc47c0d41f390204300eb9d9b"}
Env $\ast$ **env** = Env::Default()

[\[structtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_1\_1Options\_abb67771f119bc99872bc427283d8f769\]]{#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_abb67771f119bc99872bc427283d8f769
label="structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_abb67771f119bc99872bc427283d8f769"}
uint64\_t **no\_tasks\_wait\_time\_micros** = 1000

The documentation for this struct was generated from the following file:

tensorflow\_serving/batching/streaming\_batch\_scheduler.h
