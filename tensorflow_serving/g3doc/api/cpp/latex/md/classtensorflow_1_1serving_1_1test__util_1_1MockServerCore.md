::: {#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore"}

Inheritance diagram for tensorflow::serving::test\_util::MockServerCore:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore__inherit__graph.pdf){width="229pt"}

Collaboration diagram for
tensorflow::serving::test\_util::MockServerCore:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore__coll__graph.pdf){width="229pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a33becc39760f50098c9f365cbc4bcdda\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a33becc39760f50098c9f365cbc4bcdda
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a33becc39760f50098c9f365cbc4bcdda"}
**MockServerCore** (const PlatformConfigMap &platform\_config\_map)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a043ca5495fa7bb7546c2453a588866fb\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a043ca5495fa7bb7546c2453a588866fb
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a043ca5495fa7bb7546c2453a588866fb"}
**MockServerCore** (const PlatformConfigMap &platform\_config\_map,
std::unique\_ptr$<$
[ServerRequestLogger](#classtensorflow_1_1serving_1_1ServerRequestLogger)
$>$ server\_request\_logger)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_ac2af259c15a3bb1f32566a81eeea7c89\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_ac2af259c15a3bb1f32566a81eeea7c89
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_ac2af259c15a3bb1f32566a81eeea7c89"}
**MOCK\_METHOD**
([ServableStateMonitor](#classtensorflow_1_1serving_1_1ServableStateMonitor)
$\ast$,
[servable\_state\_monitor](#classtensorflow_1_1serving_1_1ServerCore_ac435225d6ad57889e29d524b32b84c46),(),(const,
override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a5ae092143b6fd95ce2dd73564bcdc968\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a5ae092143b6fd95ce2dd73564bcdc968
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a5ae092143b6fd95ce2dd73564bcdc968"}
**MOCK\_METHOD** (Status,
[ReloadConfig](#classtensorflow_1_1serving_1_1ServerCore_ac3fbf30a022d978159532c2c68384669),(const
ModelServerConfig &),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a04847a27f7568bb183caed1e5202557c\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a04847a27f7568bb183caed1e5202557c
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a04847a27f7568bb183caed1e5202557c"}
**MOCK\_METHOD** (Status,
[Log](#classtensorflow_1_1serving_1_1ServerCore_a7eec47dca427a8fcf5e345572bf818e4),(const
google::protobuf::Message &request, const google::protobuf::Message
&response, const LogMetadata &log\_metadata),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a74591619216a14cea593d97778aff02b\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a74591619216a14cea593d97778aff02b
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a74591619216a14cea593d97778aff02b"}
void **SetServable** (std::unique\_ptr$<$
[Servable](#classtensorflow_1_1serving_1_1Servable) $>$ servable)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a6b5219b50d505b1c667aceeeb2d9cf5a\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a6b5219b50d505b1c667aceeeb2d9cf5a
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a6b5219b50d505b1c667aceeeb2d9cf5a"}
template$<$typename T $>$ \
Status **GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$\ast$const handle)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_aa6c6d866f4cc2a9c21f00b5f55eb3cdc\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_aa6c6d866f4cc2a9c21f00b5f55eb3cdc
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_aa6c6d866f4cc2a9c21f00b5f55eb3cdc"}
virtual Status **GetServableHandle** (const ModelSpec &model\_spec,
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$
[Servable](#classtensorflow_1_1serving_1_1Servable) $>$ $\ast$const
handle) override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a3165ea9fb42d1d4498c05b07b5499843\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a3165ea9fb42d1d4498c05b07b5499843
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a3165ea9fb42d1d4498c05b07b5499843"}
static PlatformConfigMap **CreateFakeLoaderPlatformConfigMap** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a69ccfeff13ec7ec305075590e22d3a73\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a69ccfeff13ec7ec305075590e22d3a73
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a69ccfeff13ec7ec305075590e22d3a73"}
static [Options](#structtensorflow_1_1serving_1_1ServerCore_1_1Options)
**GetOptions** (const PlatformConfigMap &platform\_config\_map,
std::unique\_ptr$<$
[ServerRequestLogger](#classtensorflow_1_1serving_1_1ServerRequestLogger)
$>$ server\_request\_logger)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockServerCore\_a74da9d55e1b71da0ad57bf2764918caf\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a74da9d55e1b71da0ad57bf2764918caf
label="classtensorflow_1_1serving_1_1test__util_1_1MockServerCore_a74da9d55e1b71da0ad57bf2764918caf"}
std::unique\_ptr$<$ [Servable](#classtensorflow_1_1serving_1_1Servable)
$>$ **servable\_**

The documentation for this class was generated from the following file:

tensorflow\_serving/model\_servers/test\_util/mock\_server\_core.h
