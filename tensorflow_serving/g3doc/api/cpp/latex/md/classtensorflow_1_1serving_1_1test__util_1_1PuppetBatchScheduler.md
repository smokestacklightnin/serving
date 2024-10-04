::: {#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler"}

Inheritance diagram for
tensorflow::serving::test\_util::PuppetBatchScheduler$<$ TaskType $>$:

![image](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler__inherit__graph.pdf){width="258pt"}

Collaboration diagram for
tensorflow::serving::test\_util::PuppetBatchScheduler$<$ TaskType $>$:

![image](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler__coll__graph.pdf){width="258pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_afdc34f609c98c5d4399ad7962252caa6\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_afdc34f609c98c5d4399ad7962252caa6
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_afdc34f609c98c5d4399ad7962252caa6"}
**PuppetBatchScheduler** (std::function$<$ void(std::unique\_ptr$<$
Batch$<$ TaskType $>$$>$)$>$ process\_batch\_callback)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_a496b42dc1d610e4500bf6077f14bc946\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a496b42dc1d610e4500bf6077f14bc946
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a496b42dc1d610e4500bf6077f14bc946"}
Status **Schedule** (std::unique\_ptr$<$ TaskType $>$ $\ast$task)
override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_ad52cbc70799aa5ab32164a8620212d2a\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_ad52cbc70799aa5ab32164a8620212d2a
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_ad52cbc70799aa5ab32164a8620212d2a"}
size\_t **NumEnqueuedTasks** () const override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_aaf8bdce648fcc63a0c7e8edd3275ca22\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_aaf8bdce648fcc63a0c7e8edd3275ca22
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_aaf8bdce648fcc63a0c7e8edd3275ca22"}
size\_t **SchedulingCapacity** () const override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_a014f73569bddd1e144cec43fa73f1a6c\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a014f73569bddd1e144cec43fa73f1a6c
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a014f73569bddd1e144cec43fa73f1a6c"}
void **ProcessTasks** (int num\_tasks)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_a7c64166506242611e6cd251323885fdf\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a7c64166506242611e6cd251323885fdf
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a7c64166506242611e6cd251323885fdf"}
void **ProcessAllTasks** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1PuppetBatchScheduler\_a79b8a280f13e616af38bc2d4f4874cc3\]]{#classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a79b8a280f13e616af38bc2d4f4874cc3
label="classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_a79b8a280f13e616af38bc2d4f4874cc3"}
size\_t **max\_task\_size** () const override

The documentation for this class was generated from the following file:

tensorflow\_serving/batching/test\_util/puppet\_batch\_scheduler.h
