::: {#classtensorflow_1_1serving_1_1ServableStateMonitor}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor
label="classtensorflow_1_1serving_1_1ServableStateMonitor"}

\#include $<$servable\_state\_monitor.h$>$

struct
[Options](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options)

struct
[ServableStateAndTime](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime)

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a5ef18d6969478a087530f5b77e0bd2f1\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a5ef18d6969478a087530f5b77e0bd2f1
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a5ef18d6969478a087530f5b77e0bd2f1"}
using **ServableName** = string

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_aacd5912de4ba934c46ad82db1c525ce3\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_aacd5912de4ba934c46ad82db1c525ce3
label="classtensorflow_1_1serving_1_1ServableStateMonitor_aacd5912de4ba934c46ad82db1c525ce3"}
using **Version** = int64

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a8010e4b3453ae200256f3d56dd8f755e\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a8010e4b3453ae200256f3d56dd8f755e
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a8010e4b3453ae200256f3d56dd8f755e"}
using **VersionMap** = std::map$<$ Version,
[ServableStateAndTime](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime),
std::greater$<$ Version $>$ $>$

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a61d0ee57a6dcd59e82e460c0d17a2604\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a61d0ee57a6dcd59e82e460c0d17a2604
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a61d0ee57a6dcd59e82e460c0d17a2604"}
using **ServableMap** = std::map$<$ ServableName, VersionMap $>$

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a58d43d766bb8316983316896f258498e\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a58d43d766bb8316983316896f258498e
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a58d43d766bb8316983316896f258498e"}
using **ServableSet** = std::set$<$ ServableName $>$

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a6dbb131b4d7c6f036da6e3ebed3b6ad1\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a6dbb131b4d7c6f036da6e3ebed3b6ad1
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a6dbb131b4d7c6f036da6e3ebed3b6ad1"}
using **BoundedLog** = std::deque$<$
[ServableStateAndTime](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime)
$>$

using
[ServableStateNotifierFn](#classtensorflow_1_1serving_1_1ServableStateMonitor_a6b64d18d981941012439766e57bd8d66)
= std::function$<$ void(bool reached\_goal\_state, const std::map$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId),
ServableState::ManagerState $>$ &states\_reached)$>$

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a4c97d1fd2318e71b83eac646e27599c9\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a4c97d1fd2318e71b83eac646e27599c9
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a4c97d1fd2318e71b83eac646e27599c9"}
using **NotifyFn** = std::function$<$ void(const
[ServableState](#structtensorflow_1_1serving_1_1ServableState) &)$>$

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a85cf3611dfc401b031f92c0cfa353bfd\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a85cf3611dfc401b031f92c0cfa353bfd
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a85cf3611dfc401b031f92c0cfa353bfd"}
**ServableStateMonitor**
([EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$bus, const
[Options](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options)
&options=[Options](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options)())

absl::optional$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
[GetState](#classtensorflow_1_1serving_1_1ServableStateMonitor_a8fa6dd1536bbb85a55b3e41c1d2577d1)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId)
&servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)

absl::optional$<$
[ServableStateAndTime](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime)
$>$
[GetStateAndTime](#classtensorflow_1_1serving_1_1ServableStateMonitor_a8ff54ab2471885168dba0b1a05be7bea)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId)
&servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)

VersionMap
[GetVersionStates](#classtensorflow_1_1serving_1_1ServableStateMonitor_a501ef561e30709fe17f10c913d34bb1e)
(const string &servable\_name) const TF\_LOCKS\_EXCLUDED(mu\_)

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_abc3c1c27b6b7c0e8ef9a42039ede74cc\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_abc3c1c27b6b7c0e8ef9a42039ede74cc
label="classtensorflow_1_1serving_1_1ServableStateMonitor_abc3c1c27b6b7c0e8ef9a42039ede74cc"}
ServableMap
[GetAllServableStates](#classtensorflow_1_1serving_1_1ServableStateMonitor_abc3c1c27b6b7c0e8ef9a42039ede74cc)
() const TF\_LOCKS\_EXCLUDED(mu\_)

*Returns the current states of all tracked versions of all servables.*

ServableMap
[GetLiveServableStates](#classtensorflow_1_1serving_1_1ServableStateMonitor_a522166e0255c93e87a6d63c3d17e3f38)
() const TF\_LOCKS\_EXCLUDED(mu\_)

void
[ForgetUnloadedServableStates](#classtensorflow_1_1serving_1_1ServableStateMonitor_ae3ad2a50b7fa7b695885fe913b70b029)
() TF\_LOCKS\_EXCLUDED(mu\_)

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_af4623ec7d0e8c756bfe0603d879304c7\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_af4623ec7d0e8c756bfe0603d879304c7
label="classtensorflow_1_1serving_1_1ServableStateMonitor_af4623ec7d0e8c756bfe0603d879304c7"}
ServableSet **GetAvailableServableStates** () const
TF\_LOCKS\_EXCLUDED(mu\_)

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a2afc57f0eb671a3c3342c7dd71a9d6a7\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a2afc57f0eb671a3c3342c7dd71a9d6a7
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a2afc57f0eb671a3c3342c7dd71a9d6a7"}
BoundedLog
[GetBoundedLog](#classtensorflow_1_1serving_1_1ServableStateMonitor_a2afc57f0eb671a3c3342c7dd71a9d6a7)
() const TF\_LOCKS\_EXCLUDED(mu\_)

*Returns the current bounded log of handled servable state events.*

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a06b073bf82b07c224227e1efa5d44603\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a06b073bf82b07c224227e1efa5d44603
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a06b073bf82b07c224227e1efa5d44603"}
void **NotifyWhenServablesReachState** (const std::vector$<$
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest) $>$
&servables, ServableState::ManagerState goal\_state, const
[ServableStateNotifierFn](#classtensorflow_1_1serving_1_1ServableStateMonitor_a6b64d18d981941012439766e57bd8d66)
&notifier\_fn) TF\_LOCKS\_EXCLUDED(mu\_)

bool
[WaitUntilServablesReachStateWithTimeout](#classtensorflow_1_1serving_1_1ServableStateMonitor_aa9579ee04bf76fa627d65d9cbbb7ccb7)
(const std::vector$<$
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest) $>$
&servables, ServableState::ManagerState goal\_state, absl::Duration
timeout, std::map$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId),
ServableState::ManagerState $>$ $\ast$states\_reached=nullptr)
TF\_LOCKS\_EXCLUDED(mu\_) TF\_MUST\_USE\_RESULT

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a3e01409c4f3d16789ae42ba9b5fd0b12\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a3e01409c4f3d16789ae42ba9b5fd0b12
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a3e01409c4f3d16789ae42ba9b5fd0b12"}
bool **WaitUntilServablesReachState** (const std::vector$<$
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest) $>$
&servables, ServableState::ManagerState goal\_state, std::map$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId),
ServableState::ManagerState $>$ $\ast$states\_reached=nullptr)
TF\_MUST\_USE\_RESULT

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a6d8b172f93c8e74937c4594dd332c154\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a6d8b172f93c8e74937c4594dd332c154
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a6d8b172f93c8e74937c4594dd332c154"}
void **Notify** (const NotifyFn &notify\_fn)
TF\_LOCKS\_EXCLUDED(notify\_mu\_)

A utility that listens to an
[EventBus](#classtensorflow_1_1serving_1_1EventBus)&lt;[ServableState](#structtensorflow_1_1serving_1_1ServableState)$>$,
and keeps track of the state of each servable mentioned on the bus. The
intended use case is to track the states of servables in a
[Manager](#classtensorflow_1_1serving_1_1Manager).

Offers an interface for querying the servable states. It may be useful
as the basis for dashboards, as well as for testing a manager.

IMPORTANT: You must create this monitor before arranging for events to
be published on the event bus, e.g. giving the event bus to a
[Manager](#classtensorflow_1_1serving_1_1Manager).

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a6b64d18d981941012439766e57bd8d66\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a6b64d18d981941012439766e57bd8d66
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a6b64d18d981941012439766e57bd8d66"}
using
[tensorflow::serving::ServableStateMonitor::ServableStateNotifierFn](#classtensorflow_1_1serving_1_1ServableStateMonitor_a6b64d18d981941012439766e57bd8d66)
= std::function$<$void( bool reached\_goal\_state, const
std::map$<$[ServableId](#structtensorflow_1_1serving_1_1ServableId),
ServableState::ManagerState$>$& states\_reached)$>$

Notifies when all of the servables have reached the goal\_state.

Servables can be specified in two ways:

As specific versions of a servable stream name. In this case, we check
whether the specific version has reached the goal\_state or kEnd.

As latest versions, in which case any version for a servable stream name
will be matched against the goal\_state or kEnd.

We call the notifier\_fn when both conditions are true -

All of the specific servable requests have either reached the
goal\_state or kEnd.

All of the latest servable requests have reached goal\_state or kEnd.
The notifier\_fn will be called only once, and not repeatedly.

The reached\_goal\_state argument is set as true iff all of the specific
servables have reached goal\_state. So callers should verify that
reached\_goal\_state is true in the notifier\_fn.

The states\_reached argument is populated with the servables id and the
state it reached. The state would be goal\_state if reached\_goal\_state
is true, else it will contain one or more servables in kEnd state. For
latest servable requests, the servable id will be the id of the servable
in the stream which reached the state.

[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_ae3ad2a50b7fa7b695885fe913b70b029\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_ae3ad2a50b7fa7b695885fe913b70b029
label="classtensorflow_1_1serving_1_1ServableStateMonitor_ae3ad2a50b7fa7b695885fe913b70b029"}

void
tensorflow::serving::ServableStateMonitor::ForgetUnloadedServableStates
(

)

Removes all servable versions from the ServableMap whose states have
transitioned to kEnd.
[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a522166e0255c93e87a6d63c3d17e3f38\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a522166e0255c93e87a6d63c3d17e3f38
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a522166e0255c93e87a6d63c3d17e3f38"}

ServableStateMonitor::ServableMap
tensorflow::serving::ServableStateMonitor::GetLiveServableStates (

) const

Returns the current states of all versions of all servables which have
not transitioned to state ServableState::ManagerState::kEnd.
[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a8fa6dd1536bbb85a55b3e41c1d2577d1\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a8fa6dd1536bbb85a55b3e41c1d2577d1
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a8fa6dd1536bbb85a55b3e41c1d2577d1"}

absl::optional$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
tensorflow::serving::ServableStateMonitor::GetState (

servable\_id

) const

Returns the current state of one servable, or nullopt if that servable
is not being tracked.
[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a8ff54ab2471885168dba0b1a05be7bea\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a8ff54ab2471885168dba0b1a05be7bea
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a8ff54ab2471885168dba0b1a05be7bea"}

absl::optional$<$
[ServableStateMonitor::ServableStateAndTime](#structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime)
$>$ tensorflow::serving::ServableStateMonitor::GetStateAndTime (

servable\_id

) const

Returns the current state and time of one servable, or nullopt if that
servable is not being tracked.
[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_a501ef561e30709fe17f10c913d34bb1e\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_a501ef561e30709fe17f10c913d34bb1e
label="classtensorflow_1_1serving_1_1ServableStateMonitor_a501ef561e30709fe17f10c913d34bb1e"}

ServableStateMonitor::VersionMap
tensorflow::serving::ServableStateMonitor::GetVersionStates (

servable\_name

) const

Returns the current states of all tracked versions of the given
servable, if any.
[\[classtensorflow\_1\_1serving\_1\_1ServableStateMonitor\_aa9579ee04bf76fa627d65d9cbbb7ccb7\]]{#classtensorflow_1_1serving_1_1ServableStateMonitor_aa9579ee04bf76fa627d65d9cbbb7ccb7
label="classtensorflow_1_1serving_1_1ServableStateMonitor_aa9579ee04bf76fa627d65d9cbbb7ccb7"}

bool
tensorflow::serving::ServableStateMonitor::WaitUntilServablesReachStateWithTimeout
(

servables,

goal\_state,

timeout,

states\_reached = nullptr

)

Similar to NotifyWhenServablesReachState(\...), but instead of
notifying, we wait until the goal\_state or kEnd is reached.

To understand the return value and the return parameter states\_reached,
please read the documentation on NotifyWhenServablesReachState(\...).
WaitUntilServablesReachStateWithTimeout and WaitUntilServablesReachState
perform the same function, but the former has a timeout while the latter
waits indefinitely.

The documentation for this class was generated from the following files:

tensorflow\_serving/core/servable\_state\_monitor.h

tensorflow\_serving/core/servable\_state\_monitor.cc
