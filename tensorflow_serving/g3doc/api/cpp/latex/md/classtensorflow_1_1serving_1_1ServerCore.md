::: {#classtensorflow_1_1serving_1_1ServerCore}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\]]{#classtensorflow_1_1serving_1_1ServerCore
label="classtensorflow_1_1serving_1_1ServerCore"}

\#include $<$server\_core.h$>$

Inheritance diagram for tensorflow::serving::ServerCore:

![image](classtensorflow_1_1serving_1_1ServerCore__inherit__graph.pdf){width="229pt"}

Collaboration diagram for tensorflow::serving::ServerCore:

![image](classtensorflow_1_1serving_1_1ServerCore__coll__graph.pdf){width="189pt"}

struct [Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)

*[Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options) for
configuring a [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
object.*

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_adc911d936d998cde571247e65bf79e27\]]{#classtensorflow_1_1serving_1_1ServerCore_adc911d936d998cde571247e65bf79e27
label="classtensorflow_1_1serving_1_1ServerCore_adc911d936d998cde571247e65bf79e27"}
using **PreLoadHook** = AspiredVersionsManager::PreLoadHook

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a575a761b6ad37bbae6230cfb6e2b3df9\]]{#classtensorflow_1_1serving_1_1ServerCore_a575a761b6ad37bbae6230cfb6e2b3df9
label="classtensorflow_1_1serving_1_1ServerCore_a575a761b6ad37bbae6230cfb6e2b3df9"}
using **ServableStateMonitorCreator** = std::function$<$
Status([EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$event\_bus, std::unique\_ptr$<$
[ServableStateMonitor](#classtensorflow_1_1serving_1_1ServableStateMonitor)
$>$ $\ast$monitor)$>$

using
[CustomModelConfigLoader](#classtensorflow_1_1serving_1_1ServerCore_aded4a259be715e96c76f6d239ea68a80)
= std::function$<$ Status(const ::google::protobuf::Any &any,
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$event\_bus,
[UniquePtrWithDeps](#classtensorflow_1_1serving_1_1UniquePtrWithDeps)$<$
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
$>$ $\ast$manager)$>$

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a1112df0a65160902633dcc7590aa5a7c\]]{#classtensorflow_1_1serving_1_1ServerCore_a1112df0a65160902633dcc7590aa5a7c
label="classtensorflow_1_1serving_1_1ServerCore_a1112df0a65160902633dcc7590aa5a7c"}
using
[ServerRequestLoggerUpdater](#classtensorflow_1_1serving_1_1ServerCore_a1112df0a65160902633dcc7590aa5a7c)
= std::function$<$ Status(const ModelServerConfig &,
[ServerRequestLogger](#classtensorflow_1_1serving_1_1ServerRequestLogger)
$\ast$)$>$

*Function signature used to update the server\_request\_logger.*

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1ServerCore_ac88da0268e401fa99bcd074e692ee709)
() const override

virtual Status
[ReloadConfig](#classtensorflow_1_1serving_1_1ServerCore_ac3fbf30a022d978159532c2c68384669)
(const ModelServerConfig &config) TF\_LOCKS\_EXCLUDED(config\_mu\_)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_ac435225d6ad57889e29d524b32b84c46\]]{#classtensorflow_1_1serving_1_1ServerCore_ac435225d6ad57889e29d524b32b84c46
label="classtensorflow_1_1serving_1_1ServerCore_ac435225d6ad57889e29d524b32b84c46"}
virtual
[ServableStateMonitor](#classtensorflow_1_1serving_1_1ServableStateMonitor)
$\ast$
[servable\_state\_monitor](#classtensorflow_1_1serving_1_1ServerCore_ac435225d6ad57889e29d524b32b84c46)
() const

*Returns
[ServableStateMonitor](#classtensorflow_1_1serving_1_1ServableStateMonitor)
that can be used to query servable states.*

template$<$typename T $>$ \
Status
[GetServableHandle](#classtensorflow_1_1serving_1_1ServerCore_adbe7fed540950b47bf889d3414239dbf)
(const ModelSpec &model\_spec,
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$\ast$const handle)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a45edb843833ce1749ec31b85c720a2fb\]]{#classtensorflow_1_1serving_1_1ServerCore_a45edb843833ce1749ec31b85c720a2fb
label="classtensorflow_1_1serving_1_1ServerCore_a45edb843833ce1749ec31b85c720a2fb"}
virtual Status **GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$
[Servable](#classtensorflow_1_1serving_1_1Servable) $>$ $\ast$const
handle)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a465cb07e1990fdd55f6fff9e94edd438\]]{#classtensorflow_1_1serving_1_1ServerCore_a465cb07e1990fdd55f6fff9e94edd438
label="classtensorflow_1_1serving_1_1ServerCore_a465cb07e1990fdd55f6fff9e94edd438"}
template$<$typename T $>$ \
std::map$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId),
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$>$ **GetAvailableServableHandles** () const

virtual Status
[Log](#classtensorflow_1_1serving_1_1ServerCore_a7eec47dca427a8fcf5e345572bf818e4)
(const google::protobuf::Message &request, const
google::protobuf::Message &response, const LogMetadata &log\_metadata)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a7117d3815ed866ba365f6965986aa946\]]{#classtensorflow_1_1serving_1_1ServerCore_a7117d3815ed866ba365f6965986aa946
label="classtensorflow_1_1serving_1_1ServerCore_a7117d3815ed866ba365f6965986aa946"}
template$<$typename Request , typename Response $>$ \
std::unique\_ptr$<$
[StreamLogger](#classtensorflow_1_1serving_1_1StreamLogger)$<$ Request,
Response $>$ $>$ **StartLoggingStream** (const LogMetadata
&log\_metadata, ServerRequestLogger::CreateStreamLoggerFn$<$ Request,
Response $>$ create\_stream\_logger\_fn)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_ad18258c28bba9e3b6dc4f90d061bf78e\]]{#classtensorflow_1_1serving_1_1ServerCore_ad18258c28bba9e3b6dc4f90d061bf78e
label="classtensorflow_1_1serving_1_1ServerCore_ad18258c28bba9e3b6dc4f90d061bf78e"}
internal::PredictResponseTensorSerializationOption
**predict\_response\_tensor\_serialization\_option** () const

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a05a1bde7b9c8bcb8800fd4917c9232f4\]]{#classtensorflow_1_1serving_1_1ServerCore_a05a1bde7b9c8bcb8800fd4917c9232f4
label="classtensorflow_1_1serving_1_1ServerCore_a05a1bde7b9c8bcb8800fd4917c9232f4"}
bool **enable\_cors\_support** () const

static Status
[Create](#classtensorflow_1_1serving_1_1ServerCore_a538a0253233bd77da1051a985e3c2642)
([Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)
options, std::unique\_ptr$<$
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $>$ $\ast$core)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_ab86e66bc7a17c1c836b45b1878b19d4e\]]{#classtensorflow_1_1serving_1_1ServerCore_ab86e66bc7a17c1c836b45b1878b19d4e
label="classtensorflow_1_1serving_1_1ServerCore_ab86e66bc7a17c1c836b45b1878b19d4e"}
**ServerCore**
([Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)
options)

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a608b87376662e2a6459a4078681313a6\]]{#classtensorflow_1_1serving_1_1ServerCore_a608b87376662e2a6459a4078681313a6
label="classtensorflow_1_1serving_1_1ServerCore_a608b87376662e2a6459a4078681313a6"}
class **test\_util::ServerCoreTestAccess**

[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) contains state
and helper methods enabling the building of ModelServers that support
multiple interfaces. All functionality in
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) is independent
of any domain specific APIs and independent of platforms.

In terms of state,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) is initialized
with and retains a static ModelServerConfig, from which it bootstraps an
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
and auxiliary data structures to support efficient serving.

Interfaces built above
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore), e.g. RPC
service implementations, will remain stateless and will perform all
lookups of servables (models) via
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore).

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_aded4a259be715e96c76f6d239ea68a80\]]{#classtensorflow_1_1serving_1_1ServerCore_aded4a259be715e96c76f6d239ea68a80
label="classtensorflow_1_1serving_1_1ServerCore_aded4a259be715e96c76f6d239ea68a80"}
using
[tensorflow::serving::ServerCore::CustomModelConfigLoader](#classtensorflow_1_1serving_1_1ServerCore_aded4a259be715e96c76f6d239ea68a80)
= std::function$<$Status( const ::google::protobuf::Any& any,
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$[ServableState](#structtensorflow_1_1serving_1_1ServableState)$>$$\ast$
event\_bus,
[UniquePtrWithDeps](#classtensorflow_1_1serving_1_1UniquePtrWithDeps)$<$[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)$>$$\ast$
manager)$>$

A function thats responsible for instantiating and connecting the
necessary custom sources and source adapters to the manager based on a
passed in config (any). The expected pattern is that ownership of the
created sources/source adapters can be transferred to the manager.

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a538a0253233bd77da1051a985e3c2642\]]{#classtensorflow_1_1serving_1_1ServerCore_a538a0253233bd77da1051a985e3c2642
label="classtensorflow_1_1serving_1_1ServerCore_a538a0253233bd77da1051a985e3c2642"}

Status tensorflow::serving::ServerCore::Create (

options,

core

)

Creates a [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
instance with all the models and sources per the ModelServerConfig.

For models statically configured with ModelConfigList, waits for them to
be made available (or hit an error) for serving before returning.
Returns an error status if any such model fails to load.
[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_adbe7fed540950b47bf889d3414239dbf\]]{#classtensorflow_1_1serving_1_1ServerCore_adbe7fed540950b47bf889d3414239dbf
label="classtensorflow_1_1serving_1_1ServerCore_adbe7fed540950b47bf889d3414239dbf"}

template$<$typename T $>$\
Status tensorflow::serving::ServerCore::GetServableHandle (

model\_spec,

handle

)

Returns a
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle) given a
ModelSpec. Returns error if no such
[Servable](#classtensorflow_1_1serving_1_1Servable) is available -- e.g.
not yet loaded, has been quiesced/unloaded, etc. Callers may assume that
an OK status indicates a non-null handle.

IMPORTANT: The caller should only hold on to a handle for a short time,
for example for the duration of a single request. Holding a handle for a
long period of time will prevent servable loading and unloading.

If options\_.allow\_version\_labels==true, recognizes two specific model
version labels -- '̈stable'̈ and '̈canary'̈ -- and resolves them to the
smallest and largest available version, respectively.
[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_ac88da0268e401fa99bcd074e692ee709\]]{#classtensorflow_1_1serving_1_1ServerCore_ac88da0268e401fa99bcd074e692ee709
label="classtensorflow_1_1serving_1_1ServerCore_ac88da0268e401fa99bcd074e692ee709"}

std::vector$<$[ServableId](#structtensorflow_1_1serving_1_1ServableId)$>$
tensorflow::serving::ServerCore::ListAvailableServableIds (

) const, ,

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef).

[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_a7eec47dca427a8fcf5e345572bf818e4\]]{#classtensorflow_1_1serving_1_1ServerCore_a7eec47dca427a8fcf5e345572bf818e4
label="classtensorflow_1_1serving_1_1ServerCore_a7eec47dca427a8fcf5e345572bf818e4"}

virtual Status tensorflow::serving::ServerCore::Log (

request,

response,

log\_metadata

),

Writes the log for the particular request, response and metadata, if we
decide to sample it and if request-logging was configured for the
particular model.
[\[classtensorflow\_1\_1serving\_1\_1ServerCore\_ac3fbf30a022d978159532c2c68384669\]]{#classtensorflow_1_1serving_1_1ServerCore_ac3fbf30a022d978159532c2c68384669
label="classtensorflow_1_1serving_1_1ServerCore_ac3fbf30a022d978159532c2c68384669"}

Status tensorflow::serving::ServerCore::ReloadConfig (

config

)

Updates the server core with all the models and sources per the
ModelServerConfig. Like
[Create()](#classtensorflow_1_1serving_1_1ServerCore_a538a0253233bd77da1051a985e3c2642),
waits for all statically configured servables to be made available
before returning, and returns an error if any such model fails to load.
(Does not necessarily wait for models removed from the config to finish
unloading; that may occur asynchronously.)

IMPORTANT: It is only legal to call this method more than once if using
ModelConfigList (versus custom model config).

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/server\_core.h

tensorflow\_serving/model\_servers/server\_core.cc
