::: {#structtensorflow_1_1serving_1_1ServerCore_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options"}

[Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options) for
configuring a [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
object.

\#include $<$server\_core.h$>$

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ad366c96f7630e820abb86c20b452a7f8\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ad366c96f7630e820abb86c20b452a7f8
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ad366c96f7630e820abb86c20b452a7f8"}
ModelServerConfig **model\_server\_config**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a0dd3e3317ac7c2ce207749769697547f\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a0dd3e3317ac7c2ce207749769697547f
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a0dd3e3317ac7c2ce207749769697547f"}
absl::optional$<$ string $>$ **model\_config\_list\_root\_dir**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ac6533eedc1e06d29eb635a077c15d976\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ac6533eedc1e06d29eb635a077c15d976
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ac6533eedc1e06d29eb635a077c15d976"}
std::unique\_ptr$<$
[AspiredVersionPolicy](#classtensorflow_1_1serving_1_1AspiredVersionPolicy)
$>$ **aspired\_version\_policy**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_abb352b42ab835dc229aeccc2a3dece90\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_abb352b42ab835dc229aeccc2a3dece90
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_abb352b42ab835dc229aeccc2a3dece90"}
AspiredVersionsManager::CustomSortActionsFn **custom\_sort\_actions**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ad724243e1f5ec5a3e20341228b315f62\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ad724243e1f5ec5a3e20341228b315f62
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ad724243e1f5ec5a3e20341228b315f62"}
int32 **num\_load\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ae0b1856f3fd34dde6af198c6cbf56024\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ae0b1856f3fd34dde6af198c6cbf56024
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ae0b1856f3fd34dde6af198c6cbf56024"}
int32 **num\_initial\_load\_threads** = 4. $\ast$
port::NumSchedulableCPUs()

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a421c6e8b868f1039e4d86d0f23f87968\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a421c6e8b868f1039e4d86d0f23f87968
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a421c6e8b868f1039e4d86d0f23f87968"}
int32 **num\_unload\_threads** = 0

uint64\_t **total\_model\_memory\_limit\_bytes**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ac5c3555e5cc20c36e57c087d53b1a5b5\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ac5c3555e5cc20c36e57c087d53b1a5b5
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ac5c3555e5cc20c36e57c087d53b1a5b5"}
int32 **max\_num\_load\_retries** = 5

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a5ed92dd908011d9fff126978792755c8\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a5ed92dd908011d9fff126978792755c8
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a5ed92dd908011d9fff126978792755c8"}
int64\_t **load\_retry\_interval\_micros** = 1LL $\ast$ 60 $\ast$ 1000
$\ast$ 1000

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a8eb09a3c3c12121842a2aed8ae946202\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a8eb09a3c3c12121842a2aed8ae946202
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a8eb09a3c3c12121842a2aed8ae946202"}
int32 **file\_system\_poll\_wait\_seconds** = 30

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_af888f5067ae8179c922e4303272b1a87\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_af888f5067ae8179c922e4303272b1a87
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_af888f5067ae8179c922e4303272b1a87"}
bool **flush\_filesystem\_caches** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a88ba921bf5f48526e1b78d2404f61d38\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a88ba921bf5f48526e1b78d2404f61d38
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a88ba921bf5f48526e1b78d2404f61d38"}
PlatformConfigMap **platform\_config\_map**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_aba6790373826e505649c600ba8320d5e\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_aba6790373826e505649c600ba8320d5e
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_aba6790373826e505649c600ba8320d5e"}
ServableStateMonitorCreator **servable\_state\_monitor\_creator**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a471a3195c4ec2ca55eebb986f9545176\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a471a3195c4ec2ca55eebb986f9545176
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a471a3195c4ec2ca55eebb986f9545176"}
[CustomModelConfigLoader](#classtensorflow_1_1serving_1_1ServerCore_aded4a259be715e96c76f6d239ea68a80)
**custom\_model\_config\_loader**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a5867807b889e98c0d6cc4c049a94723c\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a5867807b889e98c0d6cc4c049a94723c
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a5867807b889e98c0d6cc4c049a94723c"}
bool **allow\_version\_labels** = true

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a6ed934357fc0f5a3ecc383f30334bba2\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a6ed934357fc0f5a3ecc383f30334bba2
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a6ed934357fc0f5a3ecc383f30334bba2"}
bool **fail\_if\_no\_model\_versions\_found** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a74f7765baa95ca75e610b1035eab88cb\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a74f7765baa95ca75e610b1035eab88cb
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a74f7765baa95ca75e610b1035eab88cb"}
bool **enable\_reload\_servables\_with\_error** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ab16b2ca9eb8941bb5c6ae0be1cf32f52\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ab16b2ca9eb8941bb5c6ae0be1cf32f52
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ab16b2ca9eb8941bb5c6ae0be1cf32f52"}
bool **servable\_versions\_always\_present** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a7a2cfc9d07af5571a22e19b40ee5b276\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a7a2cfc9d07af5571a22e19b40ee5b276
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a7a2cfc9d07af5571a22e19b40ee5b276"}
std::unique\_ptr$<$
[ServerRequestLogger](#classtensorflow_1_1serving_1_1ServerRequestLogger)
$>$ **server\_request\_logger**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a729c70e808a2b90523aab03044c9bf82\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a729c70e808a2b90523aab03044c9bf82
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a729c70e808a2b90523aab03044c9bf82"}
[ServerRequestLoggerUpdater](#classtensorflow_1_1serving_1_1ServerCore_a1112df0a65160902633dcc7590aa5a7c)
**server\_request\_logger\_updater**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a9a6dba3e2bd30c676bdeaa3902d52c89\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a9a6dba3e2bd30c676bdeaa3902d52c89
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a9a6dba3e2bd30c676bdeaa3902d52c89"}
PreLoadHook **pre\_load\_hook**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_ab55e6f5f379b35b6b2dc1872b465cbc0\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_ab55e6f5f379b35b6b2dc1872b465cbc0
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_ab55e6f5f379b35b6b2dc1872b465cbc0"}
bool **allow\_version\_labels\_for\_unavailable\_models** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a023e379ad3a55507147f1a398491f370\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a023e379ad3a55507147f1a398491f370
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a023e379ad3a55507147f1a398491f370"}
bool **force\_allow\_any\_version\_labels\_for\_unavailable\_models** =
false

internal::PredictResponseTensorSerializationOption
**predict\_response\_tensor\_serialization\_option**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a624e7b595d61051ca967d1a51a6f71fe\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a624e7b595d61051ca967d1a51a6f71fe
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a624e7b595d61051ca967d1a51a6f71fe"}
std::string **storage\_path\_prefix**

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a7a6ae4145ac5884afc9fc2295177651d\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a7a6ae4145ac5884afc9fc2295177651d
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a7a6ae4145ac5884afc9fc2295177651d"}
bool **enable\_cors\_support** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a377076613e0d13be46015f7c22d3f5c8\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a377076613e0d13be46015f7c22d3f5c8
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a377076613e0d13be46015f7c22d3f5c8"}
bool **with\_current\_context** = false

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a76c2a460ff8525a5124f6460c9350c4e\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a76c2a460ff8525a5124f6460c9350c4e
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a76c2a460ff8525a5124f6460c9350c4e"}
absl::Duration **servable\_state\_waiter\_timeout** =
absl::InfiniteDuration()

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a4352846fb2a71e32ae912db161c815ba\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a4352846fb2a71e32ae912db161c815ba
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a4352846fb2a71e32ae912db161c815ba"}
std::function$<$ bool(absl::Status)$>$ **should\_retry\_model\_load**

[Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options) for
configuring a [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
object.

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a2aad8f04ac32a8a34651acf0cbff4533\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a2aad8f04ac32a8a34651acf0cbff4533
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a2aad8f04ac32a8a34651acf0cbff4533"}
internal::PredictResponseTensorSerializationOption
tensorflow::serving::ServerCore::Options::predict\_response\_tensor\_serialization\_option

**Initial value:**

0

[\[structtensorflow\_1\_1serving\_1\_1ServerCore\_1\_1Options\_a91d7528c90124b297887b5949146d3e0\]]{#structtensorflow_1_1serving_1_1ServerCore_1_1Options_a91d7528c90124b297887b5949146d3e0
label="structtensorflow_1_1serving_1_1ServerCore_1_1Options_a91d7528c90124b297887b5949146d3e0"}
uint64\_t
tensorflow::serving::ServerCore::Options::total\_model\_memory\_limit\_bytes

**Initial value:**

0

The documentation for this struct was generated from the following file:

tensorflow\_serving/model\_servers/server\_core.h
