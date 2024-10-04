::: {#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockFileProbingEnv\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv
label="classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv"}

Inheritance diagram for
tensorflow::serving::test\_util::MockFileProbingEnv:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv__inherit__graph.pdf){width="247pt"}

Collaboration diagram for
tensorflow::serving::test\_util::MockFileProbingEnv:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv__coll__graph.pdf){width="247pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockFileProbingEnv\_a1bde0ebce29978c22f2df4e97e34eb2a\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_a1bde0ebce29978c22f2df4e97e34eb2a
label="classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_a1bde0ebce29978c22f2df4e97e34eb2a"}
**MOCK\_METHOD** (Status, FileExists,(const string &fname),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockFileProbingEnv\_abc1401180626c2eb9d185694a658f28d\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_abc1401180626c2eb9d185694a658f28d
label="classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_abc1401180626c2eb9d185694a658f28d"}
**MOCK\_METHOD** (Status, GetChildren,(const string &fname,
std::vector$<$ string $>$ $\ast$children),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockFileProbingEnv\_af4e14763926016992aec557a7625d634\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_af4e14763926016992aec557a7625d634
label="classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_af4e14763926016992aec557a7625d634"}
**MOCK\_METHOD** (Status, IsDirectory,(const string &fname),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockFileProbingEnv\_a55b9896905dbb2d09cda26780ac9a380\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_a55b9896905dbb2d09cda26780ac9a380
label="classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv_a55b9896905dbb2d09cda26780ac9a380"}
**MOCK\_METHOD** (Status, GetFileSize,(const string &fname, uint64\_t
$\ast$file\_size),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/util/test\_util/mock\_file\_probing\_env.h
