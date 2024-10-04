::: {#classtensorflow_1_1serving_1_1test__util_1_1MockSession}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession"}

Inheritance diagram for tensorflow::serving::test\_util::MockSession:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockSession__inherit__graph.pdf){width="212pt"}

Collaboration diagram for tensorflow::serving::test\_util::MockSession:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockSession__coll__graph.pdf){width="212pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_af24dd478e2cd2db69cedafec93046880\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_af24dd478e2cd2db69cedafec93046880
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_af24dd478e2cd2db69cedafec93046880"}
**MOCK\_METHOD** (::tensorflow::Status, Create,(const GraphDef
&graph),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a069c5388d6f7fdf43dac22374c4e64bb\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a069c5388d6f7fdf43dac22374c4e64bb
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a069c5388d6f7fdf43dac22374c4e64bb"}
**MOCK\_METHOD** (::tensorflow::Status, Extend,(const GraphDef
&graph),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a1419776f4ff0354ab6780eaa8fcbaea6\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a1419776f4ff0354ab6780eaa8fcbaea6
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a1419776f4ff0354ab6780eaa8fcbaea6"}
**MOCK\_METHOD** (::tensorflow::Status, Run,((const std::vector$<$
std::pair$<$ string, Tensor $>$$>$ &inputs), const std::vector$<$ string
$>$ &output\_names, const std::vector$<$ string $>$ &target\_nodes,
std::vector$<$ Tensor $>$ $\ast$outputs),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_ac0792f2c3d7be0c0cc9046b3cfb76a33\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_ac0792f2c3d7be0c0cc9046b3cfb76a33
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_ac0792f2c3d7be0c0cc9046b3cfb76a33"}
**MOCK\_METHOD** (::tensorflow::Status, Run,(const RunOptions
&run\_options,(const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs), const std::vector$<$ string $>$ &output\_names, const
std::vector$<$ string $>$ &target\_nodes, std::vector$<$ Tensor $>$
$\ast$outputs, RunMetadata $\ast$run\_metadata),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a99a748dfb5b790e257822d611a72c60e\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a99a748dfb5b790e257822d611a72c60e
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a99a748dfb5b790e257822d611a72c60e"}
**MOCK\_METHOD** (::tensorflow::Status, Run,(const RunOptions
&run\_options,(const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs), const std::vector$<$ string $>$ &output\_names, const
std::vector$<$ string $>$ &target\_nodes, std::vector$<$ Tensor $>$
$\ast$outputs, RunMetadata $\ast$run\_metadata, const
tensorflow::thread::ThreadPoolOptions
&thread\_pool\_options),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a73a57196ed5ff0fb515c6ccc6baaa30c\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a73a57196ed5ff0fb515c6ccc6baaa30c
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a73a57196ed5ff0fb515c6ccc6baaa30c"}
**MOCK\_METHOD** (::tensorflow::Status, PRunSetup,(const std::vector$<$
string $>$ &input\_names, const std::vector$<$ string $>$
&output\_names, const std::vector$<$ string $>$ &target\_nodes, string
$\ast$handle),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a4588de5ec0fa0c06664b5122f07e9762\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a4588de5ec0fa0c06664b5122f07e9762
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a4588de5ec0fa0c06664b5122f07e9762"}
**MOCK\_METHOD** (::tensorflow::Status, PRun,(const string
&handle,(const std::vector$<$ std::pair$<$ string, Tensor $>$$>$
&inputs), const std::vector$<$ string $>$ &output\_names, std::vector$<$
Tensor $>$ $\ast$outputs),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_ad3fa6f11960f852a0fdd08c1bd18765d\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_ad3fa6f11960f852a0fdd08c1bd18765d
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_ad3fa6f11960f852a0fdd08c1bd18765d"}
**MOCK\_METHOD** (::tensorflow::Status,
ListDevices,(std::vector$<$::tensorflow::DeviceAttributes $>$
$\ast$response),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSession\_a3d28e12e0cc887feba31493ce0f9320b\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSession_a3d28e12e0cc887feba31493ce0f9320b
label="classtensorflow_1_1serving_1_1test__util_1_1MockSession_a3d28e12e0cc887feba31493ce0f9320b"}
**MOCK\_METHOD** (::tensorflow::Status, Close,(),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/core/test\_util/mock\_session.h
