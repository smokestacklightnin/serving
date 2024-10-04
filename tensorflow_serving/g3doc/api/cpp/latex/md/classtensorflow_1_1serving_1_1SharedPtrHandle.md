::: {#classtensorflow_1_1serving_1_1SharedPtrHandle}
:::

[\[classtensorflow\_1\_1serving\_1\_1SharedPtrHandle\]]{#classtensorflow_1_1serving_1_1SharedPtrHandle
label="classtensorflow_1_1serving_1_1SharedPtrHandle"}

\#include $<$servable\_handle.h$>$

Inheritance diagram for tensorflow::serving::SharedPtrHandle:

![image](classtensorflow_1_1serving_1_1SharedPtrHandle__inherit__graph.pdf){width="221pt"}

Collaboration diagram for tensorflow::serving::SharedPtrHandle:

![image](classtensorflow_1_1serving_1_1SharedPtrHandle__coll__graph.pdf){width="221pt"}

[\[classtensorflow\_1\_1serving\_1\_1SharedPtrHandle\_aa0a25e00dc5ffd5a28d8739ab5b9f8e7\]]{#classtensorflow_1_1serving_1_1SharedPtrHandle_aa0a25e00dc5ffd5a28d8739ab5b9f8e7
label="classtensorflow_1_1serving_1_1SharedPtrHandle_aa0a25e00dc5ffd5a28d8739ab5b9f8e7"}
**SharedPtrHandle** (const
[ServableId](#structtensorflow_1_1serving_1_1ServableId) &id,
std::shared\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
loader)

[\[classtensorflow\_1\_1serving\_1\_1SharedPtrHandle\_aa885f8d3a28b5cedd37fea9c96c1b536\]]{#classtensorflow_1_1serving_1_1SharedPtrHandle_aa885f8d3a28b5cedd37fea9c96c1b536
label="classtensorflow_1_1serving_1_1SharedPtrHandle_aa885f8d3a28b5cedd37fea9c96c1b536"}
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) **servable** () override

[\[classtensorflow\_1\_1serving\_1\_1SharedPtrHandle\_af48bb8b27817208cf94de66c63193b59\]]{#classtensorflow_1_1serving_1_1SharedPtrHandle_af48bb8b27817208cf94de66c63193b59
label="classtensorflow_1_1serving_1_1SharedPtrHandle_af48bb8b27817208cf94de66c63193b59"}
const [ServableId](#structtensorflow_1_1serving_1_1ServableId) & **id**
() const override

An implementation of
[UntypedServableHandle](#classtensorflow_1_1serving_1_1UntypedServableHandle)
using shared\_ptr to do ref-counting on the
[Loader](#classtensorflow_1_1serving_1_1Loader) that owns the
[Servable](#classtensorflow_1_1serving_1_1Servable).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/servable\_handle.h
