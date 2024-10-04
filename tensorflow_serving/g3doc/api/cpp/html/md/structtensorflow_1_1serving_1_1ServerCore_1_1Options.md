::: {#top}
::: {#titlearea}
+-----------------------------------------------------------------------+
| ::: {#projectname}                                                    |
| My Project                                                            |
| :::                                                                   |
+-----------------------------------------------------------------------+
:::

::: {#main-nav}
:::

::: {#MSearchSelectWindow onmouseover="return searchBox.OnSearchSelectShow()" onmouseout="return searchBox.OnSearchSelectHide()" onkeydown="return searchBox.OnSearchSelectKey(event)"}
:::

::: {#MSearchResultsWindow}
:::

::: {#nav-path .navpath}
-   **tensorflow**
-   **serving**
-   [ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}
-   [Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Attributes](#pub-attribs) \| [List of all
members](structtensorflow_1_1serving_1_1ServerCore_1_1Options-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ServerCore::Options Struct Reference
:::
:::
:::

::: {.contents}
[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html "Options for configuring a ServerCore object."){.el}
for configuring a
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} object.
[More\...](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html#details)

`#include <server_core.h>`

[]{#pub-attribs} Public Attributes {#public-attributes .groupheader}
----------------------------------
:::

[]{#ad366c96f7630e820abb86c20b452a7f8} ModelServerConfig 

**model\_server\_config**

 

[]{#a0dd3e3317ac7c2ce207749769697547f} absl::optional\< string \> 

**model\_config\_list\_root\_dir**

 

[]{#ac6533eedc1e06d29eb635a077c15d976} std::unique\_ptr\<
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}
\> 

**aspired\_version\_policy**

 

[]{#abb352b42ab835dc229aeccc2a3dece90}
AspiredVersionsManager::CustomSortActionsFn 

**custom\_sort\_actions**

 

[]{#ad724243e1f5ec5a3e20341228b315f62} int32 

**num\_load\_threads** = 0

 

[]{#ae0b1856f3fd34dde6af198c6cbf56024} int32 

**num\_initial\_load\_threads** = 4.0 \* port::NumSchedulableCPUs()

 

[]{#a421c6e8b868f1039e4d86d0f23f87968} int32 

**num\_unload\_threads** = 0

 

uint64\_t 

**total\_model\_memory\_limit\_bytes**

 

[]{#ac5c3555e5cc20c36e57c087d53b1a5b5} int32 

**max\_num\_load\_retries** = 5

 

[]{#a5ed92dd908011d9fff126978792755c8} int64\_t 

**load\_retry\_interval\_micros** = 1LL \* 60 \* 1000 \* 1000

 

[]{#a8eb09a3c3c12121842a2aed8ae946202} int32 

**file\_system\_poll\_wait\_seconds** = 30

 

[]{#af888f5067ae8179c922e4303272b1a87} bool 

**flush\_filesystem\_caches** = false

 

[]{#a88ba921bf5f48526e1b78d2404f61d38} PlatformConfigMap 

**platform\_config\_map**

 

[]{#aba6790373826e505649c600ba8320d5e} ServableStateMonitorCreator 

**servable\_state\_monitor\_creator**

 

[]{#a471a3195c4ec2ca55eebb986f9545176}
[CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.el} 

**custom\_model\_config\_loader**

 

[]{#a5867807b889e98c0d6cc4c049a94723c} bool 

**allow\_version\_labels** = true

 

[]{#a6ed934357fc0f5a3ecc383f30334bba2} bool 

**fail\_if\_no\_model\_versions\_found** = false

 

[]{#a74f7765baa95ca75e610b1035eab88cb} bool 

**enable\_reload\_servables\_with\_error** = false

 

[]{#ab16b2ca9eb8941bb5c6ae0be1cf32f52} bool 

**servable\_versions\_always\_present** = false

 

[]{#a7a2cfc9d07af5571a22e19b40ee5b276} std::unique\_ptr\<
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}
\> 

**server\_request\_logger**

 

[]{#a729c70e808a2b90523aab03044c9bf82}
[ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.el} 

**server\_request\_logger\_updater**

 

[]{#a9a6dba3e2bd30c676bdeaa3902d52c89} PreLoadHook 

**pre\_load\_hook**

 

[]{#ab55e6f5f379b35b6b2dc1872b465cbc0} bool 

**allow\_version\_labels\_for\_unavailable\_models** = false

 

[]{#a023e379ad3a55507147f1a398491f370} bool 

**force\_allow\_any\_version\_labels\_for\_unavailable\_models** = false

 

internal::PredictResponseTensorSerializationOption 

**predict\_response\_tensor\_serialization\_option**

 

[]{#a624e7b595d61051ca967d1a51a6f71fe} std::string 

**storage\_path\_prefix**

 

[]{#a7a6ae4145ac5884afc9fc2295177651d} bool 

**enable\_cors\_support** = false

 

[]{#a377076613e0d13be46015f7c22d3f5c8} bool 

**with\_current\_context** = false

 

[]{#a76c2a460ff8525a5124f6460c9350c4e} absl::Duration 

**servable\_state\_waiter\_timeout** = absl::InfiniteDuration()

 

[]{#a4352846fb2a71e32ae912db161c815ba} std::function\<
bool(absl::Status)\> 

**should\_retry\_model\_load**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html "Options for configuring a ServerCore object."){.el}
for configuring a
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} object.
:::

Member Data Documentation {#member-data-documentation .groupheader}
-------------------------

[]{#a2aad8f04ac32a8a34651acf0cbff4533}

[[◆ ](#a2aad8f04ac32a8a34651acf0cbff4533)]{.permalink}predict\_response\_tensor\_serialization\_option {#predict_response_tensor_serialization_option .memtitle}
------------------------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -----------------------------------------------------------------------------------------------------------------------------------------------
  internal::PredictResponseTensorSerializationOption tensorflow::serving::ServerCore::Options::predict\_response\_tensor\_serialization\_option
  -----------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
**Initial value:**

::: {.fragment}
::: {.line}
=
:::

::: {.line}
internal::PredictResponseTensorSerializationOption::kAsProtoField
:::
:::
:::
:::

[]{#a91d7528c90124b297887b5949146d3e0}

[[◆ ](#a91d7528c90124b297887b5949146d3e0)]{.permalink}total\_model\_memory\_limit\_bytes {#total_model_memory_limit_bytes .memtitle}
----------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------------------------
  uint64\_t tensorflow::serving::ServerCore::Options::total\_model\_memory\_limit\_bytes
  ----------------------------------------------------------------------------------------
:::

::: {.memdoc}
**Initial value:**

::: {.fragment}
::: {.line}
=
:::

::: {.line}
std::numeric\_limits\<uint64\_t\>::max()
:::
:::
:::
:::

------------------------------------------------------------------------

The documentation for this struct was generated from the following file:

-   tensorflow\_serving/model\_servers/[server\_core.h](server__core_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
