::: {#classtensorflow_1_1serving_1_1UntypedServableHandle}
:::

[\[classtensorflow\_1\_1serving\_1\_1UntypedServableHandle\]]{#classtensorflow_1_1serving_1_1UntypedServableHandle
label="classtensorflow_1_1serving_1_1UntypedServableHandle"}

\#include $<$servable\_handle.h$>$

Inheritance diagram for tensorflow::serving::UntypedServableHandle:

![image](classtensorflow_1_1serving_1_1UntypedServableHandle__inherit__graph.pdf){width="221pt"}

[\[classtensorflow\_1\_1serving\_1\_1UntypedServableHandle\_aefd30f4f1238347c8430045ee213435e\]]{#classtensorflow_1_1serving_1_1UntypedServableHandle_aefd30f4f1238347c8430045ee213435e
label="classtensorflow_1_1serving_1_1UntypedServableHandle_aefd30f4f1238347c8430045ee213435e"}
virtual const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &
**id** () const =0

[\[classtensorflow\_1\_1serving\_1\_1UntypedServableHandle\_a46ebf9122f94d6d26aa37db4c129fb02\]]{#classtensorflow_1_1serving_1_1UntypedServableHandle_a46ebf9122f94d6d26aa37db4c129fb02
label="classtensorflow_1_1serving_1_1UntypedServableHandle_a46ebf9122f94d6d26aa37db4c129fb02"}
virtual [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) **servable**
()=0

A non-templatized handle to a servable, used internally in the
[Manager](#classtensorflow_1_1serving_1_1Manager) to retrieve a
type-erased servable object from the
[Loader](#classtensorflow_1_1serving_1_1Loader). The handle keeps the
underlying object alive as long as the handle is alive. The frontend
should not hold onto it for a long time, because holding it can delay
servable reloading.

The documentation for this class was generated from the following file:

tensorflow\_serving/core/servable\_handle.h
