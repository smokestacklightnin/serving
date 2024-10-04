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
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [Protected Member
Functions](#pro-methods) \| [Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1ServerCore-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ServerCore Class Reference
:::
:::
:::

::: {.contents}
`#include <server_core.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::ServerCore:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1ServerCore__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::ServerCore:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1ServerCore__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}

 

[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html "Options for configuring a ServerCore object."){.el}
for configuring a
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} object.
[More\...](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html#details)\

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

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

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

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

 

[]{#a45edb843833ce1749ec31b85c720a2fb} virtual Status 

**GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} \> \*const
handle)

 

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

static Status 

[Create](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642){.el}
([Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}
options, std::unique\_ptr\<
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} \>
\*core)

 

[]{#pro-methods} Protected Member Functions {#protected-member-functions .groupheader}
-------------------------------------------

[]{#ab86e66bc7a17c1c836b45b1878b19d4e}  

**ServerCore**
([Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.el}
options)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a608b87376662e2a6459a4078681313a6} class 

**test\_util::ServerCoreTestAccess**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}
contains state and helper methods enabling the building of ModelServers
that support multiple interfaces. All functionality in
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} is
independent of any domain specific APIs and independent of platforms.

In terms of state,
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el} is
initialized with and retains a static ModelServerConfig, from which it
bootstraps an
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
and auxiliary data structures to support efficient serving.

Interfaces built above
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}, e.g.
RPC service implementations, will remain stateless and will perform all
lookups of servables (models) via
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}.
:::

Member Typedef Documentation {#member-typedef-documentation .groupheader}
----------------------------

[]{#aded4a259be715e96c76f6d239ea68a80}

[[◆ ](#aded4a259be715e96c76f6d239ea68a80)]{.permalink}CustomModelConfigLoader {#custommodelconfigloader .memtitle}
-----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  using [tensorflow::serving::ServerCore::CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.el} = std::function\<Status( const ::google::protobuf::Any& any, [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}\>\* event\_bus, [UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.el}\<[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}\>\* manager)\>
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
A function that\'s responsible for instantiating and connecting the
necessary custom sources and source adapters to the manager based on a
passed in config (any). The expected pattern is that ownership of the
created sources/source adapters can be transferred to the manager.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a538a0253233bd77da1051a985e3c2642}

[[◆ ](#a538a0253233bd77da1051a985e3c2642)]{.permalink}Create() {#create .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   --------------------------      | [[static]{.mlabel}]{.mlabels}     |
| ---------------------- --- ------ |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
|   Status tensorflow::servi        |                                   |
| ng::ServerCore::Create   (   [Opt |                                   |
| ions](structtensorflow_1_1serving |                                   |
| _1_1ServerCore_1_1Options.html){. |                                   |
| el}                    *options*, |                                   |
|                                   |                                   |
|                                 s |                                   |
| td::unique\_ptr\< [ServerCore](cl |                                   |
| asstensorflow_1_1serving_1_1Serve |                                   |
| rCore.html){.el} \> \*    *core*  |                                   |
|                                   |                                   |
|                                   |                                   |
|   )                               |                                   |
|                                   |                                   |
|                                   |                                   |
|   --------------------------      |                                   |
| ---------------------- --- ------ |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Creates a
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}
instance with all the models and sources per the ModelServerConfig.

For models statically configured with ModelConfigList, waits for them to
be made available (or hit an error) for serving before returning.
Returns an error status if any such model fails to load.
:::
:::

[]{#adbe7fed540950b47bf889d3414239dbf}

[[◆ ](#adbe7fed540950b47bf889d3414239dbf)]{.permalink}GetServableHandle() {#getservablehandle .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

+-----------------------------------+-----------------------------------+
|   ------                          | [[inline]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| -------------------- --- -------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ---------------- ---------------- |                                   |
|   Stat                            |                                   |
| us tensorflow::serving::ServerCor |                                   |
| e::GetServableHandle   (   const  |                                   |
| ModelSpec &                       |                                   |
|                                   |                                   |
|                    *model\_spec*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                 [ |                                   |
| ServableHandle](classtensorflow_1 |                                   |
| _1serving_1_1ServableHandle.html) |                                   |
| {.el}\< T \> \*const    *handle*  |                                   |
|                                   |                                   |
|                                   |                                   |
|     )                             |                                   |
|                                   |                                   |
|                                   |                                   |
|   ------                          |                                   |
| --------------------------------- |                                   |
| -------------------- --- -------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ---------------- ---------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns a
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}
given a ModelSpec. Returns error if no such
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} is
available -- e.g. not yet loaded, has been quiesced/unloaded, etc.
Callers may assume that an OK status indicates a non-null handle.

IMPORTANT: The caller should only hold on to a handle for a short time,
for example for the duration of a single request. Holding a handle for a
long period of time will prevent servable loading and unloading.

If \'options\_.allow\_version\_labels==true\', recognizes two specific
model version labels -- \"stable\" and \"canary\" -- and resolves them
to the smallest and largest available version, respectively.
:::
:::

[]{#ac88da0268e401fa99bcd074e692ee709}

[[◆ ](#ac88da0268e401fa99bcd074e692ee709)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
--------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ---------------------------     | [[inline]{.mlabel}[override]{.mla |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   std::vector\<[ServableId]       |                                   |
| (structtensorflow_1_1serving_1_1S |                                   |
| ervableId.html){.el}\> tensorflow |                                   |
| ::serving::ServerCore::ListAvaila |                                   |
| bleServableIds   (      )   const |                                   |
|   ---------------------------     |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef){.el}.
:::
:::

[]{#a7eec47dca427a8fcf5e345572bf818e4}

[[◆ ](#a7eec47dca427a8fcf5e345572bf818e4)]{.permalink}Log() {#log .memtitle}
-----------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   --------------                  | [[inline]{.mla                    |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| ------ --- ---------------------- |                                   |
| -------------- ------------------ |                                   |
|   virtua                          |                                   |
| l Status tensorflow::serving::Ser |                                   |
| verCore::Log   (   const google:: |                                   |
| protobuf::Message &    *request*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                   const google::p |                                   |
| rotobuf::Message &    *response*, |                                   |
|                                   |                                   |
|                                   |                                   |
|              const LogMetadata &  |                                   |
|                  *log\_metadata*  |                                   |
|                                   |                                   |
|                          )        |                                   |
|                                   |                                   |
|   --------------                  |                                   |
| --------------------------------- |                                   |
| ------ --- ---------------------- |                                   |
| -------------- ------------------ |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Writes the log for the particular request, response and metadata, if we
decide to sample it and if request-logging was configured for the
particular model.
:::
:::

[]{#ac3fbf30a022d978159532c2c68384669}

[[◆ ](#ac3fbf30a022d978159532c2c68384669)]{.permalink}ReloadConfig() {#reloadconfig .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------                          | [[virtual]{.mlabel}]{.mlabels}    |
| --------------------------------- |                                   |
| --------------- --- ------------- |                                   |
| --------------- ---------- --- -- |                                   |
|   Stat                            |                                   |
| us tensorflow::serving::ServerCor |                                   |
| e::ReloadConfig   (   const Model |                                   |
| ServerConfig &    *config*   )    |                                   |
|   ------                          |                                   |
| --------------------------------- |                                   |
| --------------- --- ------------- |                                   |
| --------------- ---------- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Updates the server core with all the models and sources per the
ModelServerConfig. Like
[Create()](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642){.el},
waits for all statically configured servables to be made available
before returning, and returns an error if any such model fails to load.
(Does not necessarily wait for models removed from the config to finish
unloading; that may occur asynchronously.)

IMPORTANT: It is only legal to call this method more than once if using
ModelConfigList (versus custom model config).
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/model\_servers/[server\_core.h](server__core_8h_source.html){.el}
-   tensorflow\_serving/model\_servers/server\_core.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
