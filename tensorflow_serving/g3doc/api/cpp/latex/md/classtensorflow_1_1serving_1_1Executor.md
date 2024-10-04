::: {#classtensorflow_1_1serving_1_1Executor}
:::

[\[classtensorflow\_1\_1serving\_1\_1Executor\]]{#classtensorflow_1_1serving_1_1Executor
label="classtensorflow_1_1serving_1_1Executor"}

\#include $<$executor.h$>$

Inheritance diagram for tensorflow::serving::Executor:

![image](classtensorflow_1_1serving_1_1Executor__inherit__graph.pdf){width="326pt"}

virtual void
[Schedule](#classtensorflow_1_1serving_1_1Executor_af2826585d706a46e3e91e8f40f277dcc)
(std::function$<$ void()$>$ fn)=0

An abstract object that can execute closures.

Implementations of executor must be thread-safe.

[\[classtensorflow\_1\_1serving\_1\_1Executor\_af2826585d706a46e3e91e8f40f277dcc\]]{#classtensorflow_1_1serving_1_1Executor_af2826585d706a46e3e91e8f40f277dcc
label="classtensorflow_1_1serving_1_1Executor_af2826585d706a46e3e91e8f40f277dcc"}

virtual void tensorflow::serving::Executor::Schedule (

fn

)

Schedule the specified fn for execution in this executor. Depending on
the subclass implementation, this may block in some situations.

Implemented in
[tensorflow::serving::ThreadPoolExecutor](#classtensorflow_1_1serving_1_1ThreadPoolExecutor_a5d81e166c32207d3ce4c378927e0f131),
and
[tensorflow::serving::InlineExecutor](#classtensorflow_1_1serving_1_1InlineExecutor_a4787bb65866f0b4746d65103cc17761a).

The documentation for this class was generated from the following file:

tensorflow\_serving/util/executor.h
