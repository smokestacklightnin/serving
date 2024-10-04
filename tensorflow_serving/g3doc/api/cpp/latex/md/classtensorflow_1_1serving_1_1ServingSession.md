::: {#classtensorflow_1_1serving_1_1ServingSession}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServingSession\]]{#classtensorflow_1_1serving_1_1ServingSession
label="classtensorflow_1_1serving_1_1ServingSession"}

\#include $<$serving\_session.h$>$

Inheritance diagram for tensorflow::serving::ServingSession:

![image](classtensorflow_1_1serving_1_1ServingSession__inherit__graph.pdf){width="350pt"}

Collaboration diagram for tensorflow::serving::ServingSession:

![image](classtensorflow_1_1serving_1_1ServingSession__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1ServingSession\_a9bd35520578059d4c2e800fe35af269d\]]{#classtensorflow_1_1serving_1_1ServingSession_a9bd35520578059d4c2e800fe35af269d
label="classtensorflow_1_1serving_1_1ServingSession_a9bd35520578059d4c2e800fe35af269d"}
Status **Create** (const GraphDef &graph) final

[\[classtensorflow\_1\_1serving\_1\_1ServingSession\_a95aac4bd40b4d9c28df32e914cbce0df\]]{#classtensorflow_1_1serving_1_1ServingSession_a95aac4bd40b4d9c28df32e914cbce0df
label="classtensorflow_1_1serving_1_1ServingSession_a95aac4bd40b4d9c28df32e914cbce0df"}
Status **Extend** (const GraphDef &graph) final

[\[classtensorflow\_1\_1serving\_1\_1ServingSession\_a4033e3f5d34c27241effd523773aa556\]]{#classtensorflow_1_1serving_1_1ServingSession_a4033e3f5d34c27241effd523773aa556
label="classtensorflow_1_1serving_1_1ServingSession_a4033e3f5d34c27241effd523773aa556"}
Status **Close** () final

A Session that blocks state-changing methods such as Close(), while
allowing Run() for read-only access (not enforced). Useful for Session
implementations that intend to be read-only and only implement Run().

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/serving\_session.h

tensorflow\_serving/servables/tensorflow/serving\_session.cc
