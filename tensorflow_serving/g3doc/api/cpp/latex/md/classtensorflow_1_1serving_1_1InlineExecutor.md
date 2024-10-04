::: {#classtensorflow_1_1serving_1_1InlineExecutor}
:::

[\[classtensorflow\_1\_1serving\_1\_1InlineExecutor\]]{#classtensorflow_1_1serving_1_1InlineExecutor
label="classtensorflow_1_1serving_1_1InlineExecutor"}

Inheritance diagram for tensorflow::serving::InlineExecutor:

![image](classtensorflow_1_1serving_1_1InlineExecutor__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::InlineExecutor:

![image](classtensorflow_1_1serving_1_1InlineExecutor__coll__graph.pdf){width="189pt"}

void
[Schedule](#classtensorflow_1_1serving_1_1InlineExecutor_a4787bb65866f0b4746d65103cc17761a)
(std::function$<$ void()$>$ fn) override

[\[classtensorflow\_1\_1serving\_1\_1InlineExecutor\_a4787bb65866f0b4746d65103cc17761a\]]{#classtensorflow_1_1serving_1_1InlineExecutor_a4787bb65866f0b4746d65103cc17761a
label="classtensorflow_1_1serving_1_1InlineExecutor_a4787bb65866f0b4746d65103cc17761a"}

void tensorflow::serving::InlineExecutor::Schedule (

fn

),

Schedule the specified fn for execution in this executor. Depending on
the subclass implementation, this may block in some situations.

Implements
[tensorflow::serving::Executor](#classtensorflow_1_1serving_1_1Executor_af2826585d706a46e3e91e8f40f277dcc).

The documentation for this class was generated from the following files:

tensorflow\_serving/util/inline\_executor.h

tensorflow\_serving/util/inline\_executor.cc
