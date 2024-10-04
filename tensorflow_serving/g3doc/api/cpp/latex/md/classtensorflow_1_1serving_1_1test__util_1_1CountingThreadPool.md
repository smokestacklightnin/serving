::: {#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool"}

Inheritance diagram for
tensorflow::serving::test\_util::CountingThreadPool:

![image](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool__inherit__graph.pdf){width="247pt"}

Collaboration diagram for
tensorflow::serving::test\_util::CountingThreadPool:

![image](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool__coll__graph.pdf){width="247pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\_a41f57e5dadb316595d6e3c0fb18ccbc5\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a41f57e5dadb316595d6e3c0fb18ccbc5
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a41f57e5dadb316595d6e3c0fb18ccbc5"}
**CountingThreadPool** (Env $\ast$env, const string &name, int
num\_threads)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\_a022b6532e6d0106919ebe4b9f806b219\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a022b6532e6d0106919ebe4b9f806b219
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a022b6532e6d0106919ebe4b9f806b219"}
void **Schedule** (std::function$<$ void()$>$ fn) override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\_aa43fe7f84c9ee51148b44a971073da5a\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_aa43fe7f84c9ee51148b44a971073da5a
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_aa43fe7f84c9ee51148b44a971073da5a"}
int **NumThreads** () const override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\_a2e0918dad394c89ba621a1335eb4782a\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a2e0918dad394c89ba621a1335eb4782a
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_a2e0918dad394c89ba621a1335eb4782a"}
int **CurrentThreadId** () const override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1CountingThreadPool\_ade2cd1cea4997c8d891d72f4ae2af6fb\]]{#classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_ade2cd1cea4997c8d891d72f4ae2af6fb
label="classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_ade2cd1cea4997c8d891d72f4ae2af6fb"}
int **NumScheduled** () const

The documentation for this class was generated from the following file:

tensorflow\_serving/test\_util/test\_util.h
