::: {#classtensorflow_1_1serving_1_1ServableHandle}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\]]{#classtensorflow_1_1serving_1_1ServableHandle
label="classtensorflow_1_1serving_1_1ServableHandle"}

\#include $<$servable\_handle.h$>$

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_afa693e4f7cf135262c7f0babfc4d42ec\]]{#classtensorflow_1_1serving_1_1ServableHandle_afa693e4f7cf135262c7f0babfc4d42ec
label="classtensorflow_1_1serving_1_1ServableHandle_afa693e4f7cf135262c7f0babfc4d42ec"}
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle_afa693e4f7cf135262c7f0babfc4d42ec)
()=default

*[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle) is null
by default.*

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_a0aaec0c528e775316387d8265fb7badf\]]{#classtensorflow_1_1serving_1_1ServableHandle_a0aaec0c528e775316387d8265fb7badf
label="classtensorflow_1_1serving_1_1ServableHandle_a0aaec0c528e775316387d8265fb7badf"}
const [ServableId](#structtensorflow_1_1serving_1_1ServableId) & **id**
() const

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_a9ef846b5c9d09b1d02f9d5bebffbb661\]]{#classtensorflow_1_1serving_1_1ServableHandle_a9ef846b5c9d09b1d02f9d5bebffbb661
label="classtensorflow_1_1serving_1_1ServableHandle_a9ef846b5c9d09b1d02f9d5bebffbb661"}
T & **operator$\ast$** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_aabd3a483afc416f8ba57aec5d1357b01\]]{#classtensorflow_1_1serving_1_1ServableHandle_aabd3a483afc416f8ba57aec5d1357b01
label="classtensorflow_1_1serving_1_1ServableHandle_aabd3a483afc416f8ba57aec5d1357b01"}
T $\ast$ **operator-$>$** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_aefc9d99be0d24dbb02668578fa2fdef6\]]{#classtensorflow_1_1serving_1_1ServableHandle_aefc9d99be0d24dbb02668578fa2fdef6
label="classtensorflow_1_1serving_1_1ServableHandle_aefc9d99be0d24dbb02668578fa2fdef6"}
T $\ast$ **get** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_abf4d73c357efead08b91e31583e9c718\]]{#classtensorflow_1_1serving_1_1ServableHandle_abf4d73c357efead08b91e31583e9c718
label="classtensorflow_1_1serving_1_1ServableHandle_abf4d73c357efead08b91e31583e9c718"}
**operator bool** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableHandle\_adddd5c43ff870a047aa66db4edf82a7e\]]{#classtensorflow_1_1serving_1_1ServableHandle_adddd5c43ff870a047aa66db4edf82a7e
label="classtensorflow_1_1serving_1_1ServableHandle_adddd5c43ff870a047aa66db4edf82a7e"}
class **Manager**

### template$<$typename T$>$ class tensorflow::serving::ServableHandle$<$ T $>$ {#templatetypename-t-class-tensorflowservingservablehandle-t .unnumbered}

A smart pointer to the underlying servable object T retrieved from the
[Loader](#classtensorflow_1_1serving_1_1Loader). Frontend code gets
these handles from the ServableManager. The handle keeps the underlying
object alive as long as the handle is alive. The frontend should not
hold onto it for a long time, because holding it can delay servable
reloading.

The T returned from the handle is generally shared among multiple
requests, which means any mutating changes made to T must preserve
correctness vis-a-vis the application logic. Moreover, in the presence
of multiple request threads, thread-safe usage of T must be ensured.

T is expected to be a value type, and is internally stored as a pointer.
Using a pointer type for T will fail to compile, since it would be a
mistake to do so in most situations.

Example use:

The documentation for this class was generated from the following file:

tensorflow\_serving/core/servable\_handle.h
