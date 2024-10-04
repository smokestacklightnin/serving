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
-   **test\_util**
-   [MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [Public Attributes](#pub-attribs) \|
[List of all
members](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockServerCore Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::test\_util::MockServerCore:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::test\_util::MockServerCore:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#a33becc39760f50098c9f365cbc4bcdda}  

**MockServerCore** (const PlatformConfigMap &platform\_config\_map)

 

[]{#a043ca5495fa7bb7546c2453a588866fb}  

**MockServerCore** (const PlatformConfigMap &platform\_config\_map,
std::unique\_ptr\<
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}
\> server\_request\_logger)

 

[]{#ac2af259c15a3bb1f32566a81eeea7c89}  

**MOCK\_METHOD**
([ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
\*,
[servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.el},(),(const,
override))

 

[]{#a5ae092143b6fd95ce2dd73564bcdc968}  

**MOCK\_METHOD** (Status,
[ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669){.el},(const
ModelServerConfig &),(override))

 

[]{#a04847a27f7568bb183caed1e5202557c}  

**MOCK\_METHOD** (Status,
[Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.el},(const
google::protobuf::Message &request, const google::protobuf::Message
&response, const LogMetadata &log\_metadata),(override))

 

[]{#a74591619216a14cea593d97778aff02b} void 

**SetServable** (std::unique\_ptr\<
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} \>
servable)

 

[]{#a6b5219b50d505b1c667aceeeb2d9cf5a} template\<typename T \>

Status 

**GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \*const handle)

 

[]{#aa6c6d866f4cc2a9c21f00b5f55eb3cdc} virtual Status 

**GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} \> \*const
handle) override

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}

std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709){.el}
() const override

 

virtual Status 

[ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669){.el}
(const ModelServerConfig &config) TF\_LOCKS\_EXCLUDED(config\_mu\_)

 

[]{#ac435225d6ad57889e29d524b32b84c46} virtual
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
\* 

[servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.el}
() const

 

Returns
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
that can be used to query servable states.\

 

template\<typename T \>

Status 

[GetServableHandle](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf){.el}
(const ModelSpec &model\_spec,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \*const handle)

 

[]{#a465cb07e1990fdd55f6fff9e94edd438} template\<typename T \>

std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \> 

**GetAvailableServableHandles** () const

 

virtual Status 

[Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.el}
(const google::protobuf::Message &request, const
google::protobuf::Message &response, const LogMetadata &log\_metadata)

 

[]{#a7117d3815ed866ba365f6965986aa946} template\<typename Request ,
typename Response \>

std::unique\_ptr\<
[StreamLogger](classtensorflow_1_1serving_1_1StreamLogger.html){.el}\<
Request, Response \> \> 

**StartLoggingStream** (const LogMetadata &log\_metadata,
ServerRequestLogger::CreateStreamLoggerFn\< Request, Response \>
create\_stream\_logger\_fn)

 

[]{#ad18258c28bba9e3b6dc4f90d061bf78e}
internal::PredictResponseTensorSerializationOption 

**predict\_response\_tensor\_serialization\_option** () const

 

[]{#a05a1bde7b9c8bcb8800fd4917c9232f4} bool 

**enable\_cors\_support** () const

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}

template\<typename T \>

std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \> 

[GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.el}
() const

 

template\<typename T \>

Status 

[GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.el}
(const
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
&request,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \*const handle)

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a3165ea9fb42d1d4498c05b07b5499843} static PlatformConfigMap 

**CreateFakeLoaderPlatformConfigMap** ()

 

[]{#a69ccfeff13ec7ec305075590e22d3a73} static
[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el} 

**GetOptions** (const PlatformConfigMap &platform\_config\_map,
std::unique\_ptr\<
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}
\> server\_request\_logger)

 

![-](closed.png) Static Public Member Functions inherited from
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}

static Status 

[Create](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642){.el}
([Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}
options, std::unique\_ptr\<
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} \>
\*core)

 

[]{#pub-attribs} Public Attributes {#public-attributes .groupheader}
----------------------------------

[]{#a74da9d55e1b71da0ad57bf2764918caf} std::unique\_ptr\<
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} \> 

**servable\_**

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}

[]{#adc911d936d998cde571247e65bf79e27} using 

**PreLoadHook** = AspiredVersionsManager::PreLoadHook

 

[]{#a575a761b6ad37bbae6230cfb6e2b3df9} using 

**ServableStateMonitorCreator** = std::function\<
Status([EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
\> \*event\_bus, std::unique\_ptr\<
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
\> \*monitor)\>

 

using 

[CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.el}
= std::function\< Status(const ::google::protobuf::Any &any,
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
\> \*event\_bus,
[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.el}\<
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
\> \*manager)\>

 

[]{#a1112df0a65160902633dcc7590aa5a7c} using 

[ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.el}
= std::function\< Status(const ModelServerConfig &,
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}
\*)\>

 

Function signature used to update the server\_request\_logger.\

 

![-](closed.png) Protected Member Functions inherited from
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}

[]{#ab86e66bc7a17c1c836b45b1878b19d4e}  

**ServerCore**
([Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}
options)

 

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/model\_servers/test\_util/[mock\_server\_core.h](mock__server__core_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
