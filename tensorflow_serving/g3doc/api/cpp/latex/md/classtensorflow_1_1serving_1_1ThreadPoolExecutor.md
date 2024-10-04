::: {#classtensorflow_1_1serving_1_1ThreadPoolExecutor}
:::

[\[classtensorflow\_1\_1serving\_1\_1ThreadPoolExecutor\]]{#classtensorflow_1_1serving_1_1ThreadPoolExecutor
label="classtensorflow_1_1serving_1_1ThreadPoolExecutor"}

Inheritance diagram for tensorflow::serving::ThreadPoolExecutor:

![image](classtensorflow_1_1serving_1_1ThreadPoolExecutor__inherit__graph.pdf){width="199pt"}

Collaboration diagram for tensorflow::serving::ThreadPoolExecutor:

![image](classtensorflow_1_1serving_1_1ThreadPoolExecutor__coll__graph.pdf){width="199pt"}

[\[classtensorflow\_1\_1serving\_1\_1ThreadPoolExecutor\_a77b2368009576fdbf09012b7f17a5925\]]{#classtensorflow_1_1serving_1_1ThreadPoolExecutor_a77b2368009576fdbf09012b7f17a5925
label="classtensorflow_1_1serving_1_1ThreadPoolExecutor_a77b2368009576fdbf09012b7f17a5925"}
**ThreadPoolExecutor** (Env $\ast$env, const string &thread\_pool\_name,
int num\_threads)

void
[Schedule](#classtensorflow_1_1serving_1_1ThreadPoolExecutor_a5d81e166c32207d3ce4c378927e0f131)
(std::function$<$ void()$>$ fn) override

[\[classtensorflow\_1\_1serving\_1\_1ThreadPoolExecutor\_a5d81e166c32207d3ce4c378927e0f131\]]{#classtensorflow_1_1serving_1_1ThreadPoolExecutor_a5d81e166c32207d3ce4c378927e0f131
label="classtensorflow_1_1serving_1_1ThreadPoolExecutor_a5d81e166c32207d3ce4c378927e0f131"}

void tensorflow::serving::ThreadPoolExecutor::Schedule (

fn

),

Schedule the specified fn for execution in this executor. Depending on
the subclass implementation, this may block in some situations.

Implements
[tensorflow::serving::Executor](#classtensorflow_1_1serving_1_1Executor_af2826585d706a46e3e91e8f40f277dcc).

The documentation for this class was generated from the following files:

tensorflow\_serving/util/threadpool\_executor.h

tensorflow\_serving/util/threadpool\_executor.cc
