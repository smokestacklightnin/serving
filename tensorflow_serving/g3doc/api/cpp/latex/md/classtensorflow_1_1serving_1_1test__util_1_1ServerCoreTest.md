::: {#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest"}

Inheritance diagram for tensorflow::serving::test\_util::ServerCoreTest:

![image](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest__inherit__graph.pdf){width="227pt"}

Collaboration diagram for
tensorflow::serving::test\_util::ServerCoreTest:

![image](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest__coll__graph.pdf){width="227pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_ad043644032ac1c76131d50a185ec9b91\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_ad043644032ac1c76131d50a185ec9b91
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_ad043644032ac1c76131d50a185ec9b91"}
enum **TestType** { **SAVED\_MODEL\_BACKWARD\_COMPATIBILITY** ,
**SAVED\_MODEL** , **NUM\_TEST\_TYPES** }

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a3f97399480c8dbdf4d5daa2844286667\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a3f97399480c8dbdf4d5daa2844286667
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a3f97399480c8dbdf4d5daa2844286667"}
static string **GetNameOfTestType** (int test\_type)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a299fc0b10ce6804775938d464b9432fa\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a299fc0b10ce6804775938d464b9432fa
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a299fc0b10ce6804775938d464b9432fa"}
static
[ServerCore::Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)
**GetDefaultOptions** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a7113fe06f410476e8fc56b20b28a70ca\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a7113fe06f410476e8fc56b20b28a70ca
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a7113fe06f410476e8fc56b20b28a70ca"}
ModelServerConfig **GetTestModelServerConfigForFakePlatform** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a060a714bd169caf5111893cad93f4491\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a060a714bd169caf5111893cad93f4491
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a060a714bd169caf5111893cad93f4491"}
ModelServerConfig **GetTestModelServerConfigForTensorflowPlatform** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a37ddd9efa2e87ed457a53ea7b279873c\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a37ddd9efa2e87ed457a53ea7b279873c
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a37ddd9efa2e87ed457a53ea7b279873c"}
void **SwitchToHalfPlusTwoWith2Versions** (ModelServerConfig
$\ast$config)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_aee210d40a079b3ea69caf9ae412970a0\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_aee210d40a079b3ea69caf9ae412970a0
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_aee210d40a079b3ea69caf9ae412970a0"}
Status **CreateServerCore** (const ModelServerConfig &config,
[ServerCore::Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)
options, std::unique\_ptr$<$
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $>$
$\ast$server\_core)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_ac1f23e405bdd8c8e0e960af15adca70b\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_ac1f23e405bdd8c8e0e960af15adca70b
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_ac1f23e405bdd8c8e0e960af15adca70b"}
Status **CreateServerCore** (const ModelServerConfig &config,
std::unique\_ptr$<$
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $>$
$\ast$server\_core)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_acaeed909d03bcb2e17318d7afbb2e9a7\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_acaeed909d03bcb2e17318d7afbb2e9a7
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_acaeed909d03bcb2e17318d7afbb2e9a7"}
TestType **GetTestType** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_aa98292d73341783cb2b2ef0ebf4996d0\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_aa98292d73341783cb2b2ef0ebf4996d0
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_aa98292d73341783cb2b2ef0ebf4996d0"}
bool **PrefixPathsWithURIScheme** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1ServerCoreTest\_a64ec82721334676ec8be3b4d825b6b52\]]{#classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a64ec82721334676ec8be3b4d825b6b52
label="classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_a64ec82721334676ec8be3b4d825b6b52"}
string **GetNameForTestCase** ()

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/test\_util/server\_core\_test\_util.h

tensorflow\_serving/model\_servers/test\_util/server\_core\_test\_util.cc
