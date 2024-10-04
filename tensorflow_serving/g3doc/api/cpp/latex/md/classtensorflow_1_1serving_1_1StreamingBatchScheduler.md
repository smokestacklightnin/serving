::: {#classtensorflow_1_1serving_1_1StreamingBatchScheduler}
:::

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler"}

Inheritance diagram for tensorflow::serving::StreamingBatchScheduler$<$
TaskType $>$:

![image](classtensorflow_1_1serving_1_1StreamingBatchScheduler__inherit__graph.pdf){width="239pt"}

Collaboration diagram for
tensorflow::serving::StreamingBatchScheduler$<$ TaskType $>$:

![image](classtensorflow_1_1serving_1_1StreamingBatchScheduler__coll__graph.pdf){width="239pt"}

struct
[Options](#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_a40142577908f6bc5b75b58e76bbf7d0c\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler_a40142577908f6bc5b75b58e76bbf7d0c
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler_a40142577908f6bc5b75b58e76bbf7d0c"}
Status **Schedule** (std::unique\_ptr$<$ TaskType $>$ $\ast$task)
override

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_a87486e2b584d077bd138181498a10fe9\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler_a87486e2b584d077bd138181498a10fe9
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler_a87486e2b584d077bd138181498a10fe9"}
size\_t **NumEnqueuedTasks** () const override

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_af39088302ce6cb4c97dcd0c7ec96f8ec\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler_af39088302ce6cb4c97dcd0c7ec96f8ec
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler_af39088302ce6cb4c97dcd0c7ec96f8ec"}
size\_t **SchedulingCapacity** () const override

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_a4560b96d82e2f32b126b32474329721d\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler_a4560b96d82e2f32b126b32474329721d
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler_a4560b96d82e2f32b126b32474329721d"}
size\_t **max\_task\_size** () const override

[\[classtensorflow\_1\_1serving\_1\_1StreamingBatchScheduler\_ac5de9bbb555f0618a4502ae800fa1f85\]]{#classtensorflow_1_1serving_1_1StreamingBatchScheduler_ac5de9bbb555f0618a4502ae800fa1f85
label="classtensorflow_1_1serving_1_1StreamingBatchScheduler_ac5de9bbb555f0618a4502ae800fa1f85"}
static Status **Create** (const
[Options](#structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options)
&options, std::function$<$ void(std::unique\_ptr$<$ Batch$<$ TaskType
$>$$>$)$>$ process\_batch\_callback, std::unique\_ptr$<$
[StreamingBatchScheduler](#classtensorflow_1_1serving_1_1StreamingBatchScheduler)$<$
TaskType $>$$>$ $\ast$scheduler)

The documentation for this class was generated from the following file:

tensorflow\_serving/batching/streaming\_batch\_scheduler.h
