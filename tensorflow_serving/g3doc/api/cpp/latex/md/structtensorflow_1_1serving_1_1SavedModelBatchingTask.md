::: {#structtensorflow_1_1serving_1_1SavedModelBatchingTask}
:::

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask"}

Inheritance diagram for tensorflow::serving::SavedModelBatchingTask:

![image](structtensorflow_1_1serving_1_1SavedModelBatchingTask__inherit__graph.pdf){width="227pt"}

Collaboration diagram for tensorflow::serving::SavedModelBatchingTask:

![image](structtensorflow_1_1serving_1_1SavedModelBatchingTask__coll__graph.pdf){width="340pt"}

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_a60c23eb53ef4ab7a30a69602d0d10ea9\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_a60c23eb53ef4ab7a30a69602d0d10ea9
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_a60c23eb53ef4ab7a30a69602d0d10ea9"}
static std::string **Name** ()

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_a79ac19875c5f78cd1d7e0fd63fa244da\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_a79ac19875c5f78cd1d7e0fd63fa244da
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_a79ac19875c5f78cd1d7e0fd63fa244da"}
tfrt::HostContext $\ast$ **host\_context**

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_a5087e35e5ed7939780218b382f4f8167\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_a5087e35e5ed7939780218b382f4f8167
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_a5087e35e5ed7939780218b382f4f8167"}
absl::Span$<$ const Tensor $>$ **tfrt\_inputs**

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_a7fb4fee88d15c2ff7a855a87fd423576\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_a7fb4fee88d15c2ff7a855a87fd423576
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_a7fb4fee88d15c2ff7a855a87fd423576"}
std::vector$<$ Tensor $>$ $\ast$ **tfrt\_outputs**

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_ab03be8a4e4e48d07330973dcc058af6b\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_ab03be8a4e4e48d07330973dcc058af6b
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_ab03be8a4e4e48d07330973dcc058af6b"}
tfrt::SavedModel::RunOptions **run\_options**

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_ae0228a6efe304eb381fc9fef01daa916\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_ae0228a6efe304eb381fc9fef01daa916
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_ae0228a6efe304eb381fc9fef01daa916"}
std::vector$<$ Tensor $>$ **tfrt\_partial\_inputs**

[\[structtensorflow\_1\_1serving\_1\_1SavedModelBatchingTask\_a4e5d503873a12620500b3a4bc2a804bf\]]{#structtensorflow_1_1serving_1_1SavedModelBatchingTask_a4e5d503873a12620500b3a4bc2a804bf
label="structtensorflow_1_1serving_1_1SavedModelBatchingTask_a4e5d503873a12620500b3a4bc2a804bf"}
[ThreadSafeStatus](#classtensorflow_1_1serving_1_1ThreadSafeStatus)
$\ast$ **partial\_status** = nullptr

The documentation for this struct was generated from the following file:

tensorflow\_serving/batching/tfrt\_saved\_model\_with\_batching.h
