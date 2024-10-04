::: {#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory"}

Inheritance diagram for
tensorflow::serving::test\_util::FakeThreadPoolFactory:

![image](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory__inherit__graph.pdf){width="225pt"}

Collaboration diagram for
tensorflow::serving::test\_util::FakeThreadPoolFactory:

![image](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory__coll__graph.pdf){width="225pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\_aec279b70cd3261955f5150be2bb0c000\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_aec279b70cd3261955f5150be2bb0c000
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_aec279b70cd3261955f5150be2bb0c000"}
**FakeThreadPoolFactory** (const FakeThreadPoolFactoryConfig &config)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\_a20292aa01e485137cdc428b5d5fafa8f\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a20292aa01e485137cdc428b5d5fafa8f
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a20292aa01e485137cdc428b5d5fafa8f"}
virtual
[ScopedThreadPools](#classtensorflow_1_1serving_1_1ScopedThreadPools)
**GetThreadPools** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\_a90b13ea7cb01772270a25ab0a0681ff8\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a90b13ea7cb01772270a25ab0a0681ff8
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a90b13ea7cb01772270a25ab0a0681ff8"}
void **SetInterOpThreadPool** (std::shared\_ptr$<$
thread::ThreadPoolInterface $>$ thread\_pool)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\_a7f57b101134ede1d335d25caa92f7253\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a7f57b101134ede1d335d25caa92f7253
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a7f57b101134ede1d335d25caa92f7253"}
void **SetIntraOpThreadPool** (std::shared\_ptr$<$
thread::ThreadPoolInterface $>$ thread\_pool)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeThreadPoolFactory\_a1bf71b5a00da80091d74d770a288748e\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a1bf71b5a00da80091d74d770a288748e
label="classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_a1bf71b5a00da80091d74d770a288748e"}
static Status **Create** (const FakeThreadPoolFactoryConfig &config,
std::unique\_ptr$<$
[ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$>$ $\ast$result)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/test\_util/fake\_thread\_pool\_factory.h

tensorflow\_serving/servables/tensorflow/test\_util/fake\_thread\_pool\_factory.cc
