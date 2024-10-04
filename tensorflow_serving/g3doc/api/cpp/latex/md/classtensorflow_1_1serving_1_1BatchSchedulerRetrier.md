::: {#classtensorflow_1_1serving_1_1BatchSchedulerRetrier}
:::

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier"}

Inheritance diagram for tensorflow::serving::BatchSchedulerRetrier$<$
TaskType $>$:

![image](classtensorflow_1_1serving_1_1BatchSchedulerRetrier__inherit__graph.pdf){width="239pt"}

Collaboration diagram for tensorflow::serving::BatchSchedulerRetrier$<$
TaskType $>$:

![image](classtensorflow_1_1serving_1_1BatchSchedulerRetrier__coll__graph.pdf){width="239pt"}

struct
[Options](#structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\_ad27178cade0a776955fba0239ba93157\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier_ad27178cade0a776955fba0239ba93157
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier_ad27178cade0a776955fba0239ba93157"}
Status **Schedule** (std::unique\_ptr$<$ TaskType $>$ $\ast$task)
override

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\_aabc14734a4e58f195a31034d6f374c9f\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier_aabc14734a4e58f195a31034d6f374c9f
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier_aabc14734a4e58f195a31034d6f374c9f"}
size\_t **NumEnqueuedTasks** () const override

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\_a47a8d2c6e34fc922246f628a899be8e5\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier_a47a8d2c6e34fc922246f628a899be8e5
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier_a47a8d2c6e34fc922246f628a899be8e5"}
size\_t **SchedulingCapacity** () const override

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\_afe77e410b0aeeda37b294d7d031d31f2\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier_afe77e410b0aeeda37b294d7d031d31f2
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier_afe77e410b0aeeda37b294d7d031d31f2"}
size\_t **max\_task\_size** () const override

[\[classtensorflow\_1\_1serving\_1\_1BatchSchedulerRetrier\_a26d04b1e853e5d422c30da9a31f97c50\]]{#classtensorflow_1_1serving_1_1BatchSchedulerRetrier_a26d04b1e853e5d422c30da9a31f97c50
label="classtensorflow_1_1serving_1_1BatchSchedulerRetrier_a26d04b1e853e5d422c30da9a31f97c50"}
static Status **Create** (const
[Options](#structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options)
&options, std::unique\_ptr$<$ BatchScheduler$<$ TaskType $>$$>$ wrapped,
std::unique\_ptr$<$
[BatchSchedulerRetrier](#classtensorflow_1_1serving_1_1BatchSchedulerRetrier)$<$
TaskType $>$$>$ $\ast$result)

The documentation for this class was generated from the following file:

tensorflow\_serving/batching/batch\_scheduler\_retrier.h
