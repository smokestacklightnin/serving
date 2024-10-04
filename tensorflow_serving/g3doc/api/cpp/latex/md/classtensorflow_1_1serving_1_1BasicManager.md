::: {#classtensorflow_1_1serving_1_1BasicManager}
:::

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\]]{#classtensorflow_1_1serving_1_1BasicManager
label="classtensorflow_1_1serving_1_1BasicManager"}

\#include $<$basic\_manager.h$>$

Inheritance diagram for tensorflow::serving::BasicManager:

![image](classtensorflow_1_1serving_1_1BasicManager__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::BasicManager:

![image](classtensorflow_1_1serving_1_1BasicManager__coll__graph.pdf){width="189pt"}

struct
[Options](#structtensorflow_1_1serving_1_1BasicManager_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_abeacf431a3e838da2b1602828f0c0eb2\]]{#classtensorflow_1_1serving_1_1BasicManager_abeacf431a3e838da2b1602828f0c0eb2
label="classtensorflow_1_1serving_1_1BasicManager_abeacf431a3e838da2b1602828f0c0eb2"}
using **PreLoadHook** = std::function$<$ void(const
[ServableId](#structtensorflow_1_1serving_1_1ServableId) &)$>$

using
[DoneCallback](#classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc)
= std::function$<$ void(const Status &status)$>$

[$\sim$BasicManager](#classtensorflow_1_1serving_1_1BasicManager_a492123b8bb97709184ddb57772e3ccf3)
() override

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1BasicManager_a3c004d32952596c1f5759b1cfcc3c639)
() const override

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_ad58907b2d551d693d13b6c979c4bd511\]]{#classtensorflow_1_1serving_1_1BasicManager_ad58907b2d551d693d13b6c979c4bd511
label="classtensorflow_1_1serving_1_1BasicManager_ad58907b2d551d693d13b6c979c4bd511"}
Status **GetUntypedServableHandle** (const
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
&request, std::unique\_ptr$<$
[UntypedServableHandle](#classtensorflow_1_1serving_1_1UntypedServableHandle)
$>$ $\ast$untyped\_handle) override

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a675a065bc2acf6229be899618e190b2b\]]{#classtensorflow_1_1serving_1_1BasicManager_a675a065bc2acf6229be899618e190b2b
label="classtensorflow_1_1serving_1_1BasicManager_a675a065bc2acf6229be899618e190b2b"}
std::map$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId),
std::unique\_ptr$<$
[UntypedServableHandle](#classtensorflow_1_1serving_1_1UntypedServableHandle)
$>$ $>$ **GetAvailableUntypedServableHandles** () const override

Status
[ManageServable](#classtensorflow_1_1serving_1_1BasicManager_ac2759caea67d3d37b9dba31589f9ef1d)
([ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader)
$>$$>$ servable)

template$<$typename T $>$ \
Status
[ManageServableWithAdditionalState](#classtensorflow_1_1serving_1_1BasicManager_a72406e3aedfa0084e24f2bd8ec7efdcc)
([ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader)
$>$$>$ servable, std::unique\_ptr$<$ T $>$ additional\_state)

Status
[StopManagingServable](#classtensorflow_1_1serving_1_1BasicManager_a3209cd82cbb5eac79bc3238b3c6bec43)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)

std::vector$<$ string $>$
[GetManagedServableNames](#classtensorflow_1_1serving_1_1BasicManager_afbdc3d0ed83559c7d8b3b0092194ead6)
() const

template$<$typename T = std::nullptr\_t$>$ \
std::vector$<$
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
T $>$ $>$
[GetManagedServableStateSnapshots](#classtensorflow_1_1serving_1_1BasicManager_a31716665d8df8451d379363309dac826)
(const string &servable\_name) const

template$<$typename T = std::nullptr\_t$>$ \
absl::optional$<$
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
T $>$ $>$
[GetManagedServableStateSnapshot](#classtensorflow_1_1serving_1_1BasicManager_af681f56bbef07ab201f25c0097f73e75)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)

template$<$typename T $>$ \
T $\ast$
[GetAdditionalServableState](#classtensorflow_1_1serving_1_1BasicManager_a99dbea960f6d47461dbfca5bfa149335)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)

void
[LoadServable](#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id,
[DoneCallback](#classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc)
done\_callback)

void
[CancelLoadServableRetry](#classtensorflow_1_1serving_1_1BasicManager_a84dca5ec1ecc28421d5ab020beac2ee3)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)

void
[UnloadServable](#classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id,
[DoneCallback](#classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc)
done\_callback)

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_af8f89ab0900a43b12cfbd9b2185fbfde\]]{#classtensorflow_1_1serving_1_1BasicManager_af8f89ab0900a43b12cfbd9b2185fbfde
label="classtensorflow_1_1serving_1_1BasicManager_af8f89ab0900a43b12cfbd9b2185fbfde"}
static Status **Create**
([Options](#structtensorflow_1_1serving_1_1BasicManager_1_1Options)
options, std::unique\_ptr$<$
[BasicManager](#classtensorflow_1_1serving_1_1BasicManager) $>$
$\ast$manager)

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a2158193bbefd406c1206927ce42fb865\]]{#classtensorflow_1_1serving_1_1BasicManager_a2158193bbefd406c1206927ce42fb865
label="classtensorflow_1_1serving_1_1BasicManager_a2158193bbefd406c1206927ce42fb865"}
class **AspiredVersionsManager**

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_aa40648d98e6ee77b0bc8b0a272b54410\]]{#classtensorflow_1_1serving_1_1BasicManager_aa40648d98e6ee77b0bc8b0a272b54410
label="classtensorflow_1_1serving_1_1BasicManager_aa40648d98e6ee77b0bc8b0a272b54410"}
class **test\_util::BasicManagerTestAccess**

Helps manage the lifecycle of servables including loading, serving and
unloading them. The manager accepts servables in the form of Loaders.

We start managing a servable through one of the ManageServable$\ast$
methods. You can go on to load the servable after this by calling
[LoadServable()](#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb).
Loading will also make the servable available to serve. Once you decide
to unload it, you can call
[UnloadServable()](#classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408)
on it, which will make it unavailable to serve, then unload the
servable.

Servables are retained until
[StopManagingServable()](#classtensorflow_1_1serving_1_1BasicManager_a3209cd82cbb5eac79bc3238b3c6bec43)
is called. This allows a higher level manager with more information to
decide when its safe to forget about a servable.

[BasicManager](#classtensorflow_1_1serving_1_1BasicManager) tracks the
resources (e.g. RAM) used by loaded servables, and only allows loading
new servables that fit within the overall resource pool.

[BasicManager](#classtensorflow_1_1serving_1_1BasicManager) can be
configured to use a thread-pool to do its load and unloads. This makes
the
[LoadServable()](#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb)
and
[UnloadServable()](#classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408)
methods schedule the load/unloads rather than executing them
synchronously. If there are more pending load/unloads than threads in
the thread pool, they are processed in FIFO order.

In the presence of loaders that over-estimate their servables resource
needs and/or only bind their servables resources to device instances,
load/unload concurrency can be reduced below the thread-pool size. That
is because we may have to wait for one servables load/unload to finish
to pin down the resource availability for loading another servable.

REQUIRES:

Order of method calls -
[ManageServable()](#classtensorflow_1_1serving_1_1BasicManager_ac2759caea67d3d37b9dba31589f9ef1d)
(and variants) -$>$
[LoadServable()](#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb)
-$>$
[UnloadServable()](#classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408)
-$>$
[StopManagingServable()](#classtensorflow_1_1serving_1_1BasicManager_a3209cd82cbb5eac79bc3238b3c6bec43).

Do not schedule concurrent load and unloads of the same servable.

Do not call load or unload multiple times on the same servable.

This class is thread-safe.

Example usage:

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a8ee7a19d059b362c0702686d981bf5fc\]]{#classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc
label="classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc"}
using
[tensorflow::serving::BasicManager::DoneCallback](#classtensorflow_1_1serving_1_1BasicManager_a8ee7a19d059b362c0702686d981bf5fc)
= std::function$<$void(const Status& status)$>$

Callback called at the end of {Load,Unload}Servable(). We pass in the
status of the operation to the callback.

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a492123b8bb97709184ddb57772e3ccf3\]]{#classtensorflow_1_1serving_1_1BasicManager_a492123b8bb97709184ddb57772e3ccf3
label="classtensorflow_1_1serving_1_1BasicManager_a492123b8bb97709184ddb57772e3ccf3"}

tensorflow::serving::BasicManager::$\sim$BasicManager (

)

If configured to use a load/unload thread-pool, waits until all
scheduled loads and unloads have finished and then destroys the set of
threads.

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a84dca5ec1ecc28421d5ab020beac2ee3\]]{#classtensorflow_1_1serving_1_1BasicManager_a84dca5ec1ecc28421d5ab020beac2ee3
label="classtensorflow_1_1serving_1_1BasicManager_a84dca5ec1ecc28421d5ab020beac2ee3"}

void tensorflow::serving::BasicManager::CancelLoadServableRetry (

id

)

Cancels retrying the servable load during
[LoadServable()](#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb)
by replacing the
[LoaderHarness::should\_retry](#classtensorflow_1_1serving_1_1LoaderHarness_ae344a05f0ae81c0f589daaa737223435)
with a function that always returns false. Does nothing if the servable
isnt managed.

If the retries are cancelled, the servable goes into a state dependent
on the last Load() called on it. If the last Load() was successful, it
will be in state kReady, else in kError.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a99dbea960f6d47461dbfca5bfa149335\]]{#classtensorflow_1_1serving_1_1BasicManager_a99dbea960f6d47461dbfca5bfa149335
label="classtensorflow_1_1serving_1_1BasicManager_a99dbea960f6d47461dbfca5bfa149335"}

template$<$typename T $>$\
T $\ast$ tensorflow::serving::BasicManager::GetAdditionalServableState (

id

)

Returns the additional state for the servable. Returns nullptr if there
is no additional state setup or if there is a type mismatch between what
was setup and what is being asked for.

REQUIRES: This manager should have been managing this servable already,
else we return nullptr.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_afbdc3d0ed83559c7d8b3b0092194ead6\]]{#classtensorflow_1_1serving_1_1BasicManager_afbdc3d0ed83559c7d8b3b0092194ead6
label="classtensorflow_1_1serving_1_1BasicManager_afbdc3d0ed83559c7d8b3b0092194ead6"}

std::vector$<$ string $>$
tensorflow::serving::BasicManager::GetManagedServableNames (

) const

Returns the names of all the servables managed by this manager. The
names will be duplicate-free and not in any particular order.

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_af681f56bbef07ab201f25c0097f73e75\]]{#classtensorflow_1_1serving_1_1BasicManager_af681f56bbef07ab201f25c0097f73e75
label="classtensorflow_1_1serving_1_1BasicManager_af681f56bbef07ab201f25c0097f73e75"}

template$<$typename T $>$\
absl::optional$<$
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
T $>$ $>$
tensorflow::serving::BasicManager::GetManagedServableStateSnapshot (

id

)

Returns the state snapshot of a particular servable-id managed by this
manager if available.

REQUIRES: This manager should have been managing this servable already,
else we return nullopt.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a31716665d8df8451d379363309dac826\]]{#classtensorflow_1_1serving_1_1BasicManager_a31716665d8df8451d379363309dac826
label="classtensorflow_1_1serving_1_1BasicManager_a31716665d8df8451d379363309dac826"}

template$<$typename T $>$\
std::vector$<$
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
T $>$ $>$
tensorflow::serving::BasicManager::GetManagedServableStateSnapshots (

servable\_name

) const

Returns the state snapshots of all the servables of a particular stream,
managed by this manager.

T is the additional-state type, if any.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a3c004d32952596c1f5759b1cfcc3c639\]]{#classtensorflow_1_1serving_1_1BasicManager_a3c004d32952596c1f5759b1cfcc3c639
label="classtensorflow_1_1serving_1_1BasicManager_a3c004d32952596c1f5759b1cfcc3c639"}

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$ tensorflow::serving::BasicManager::ListAvailableServableIds (

) const,

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef).

[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a09e87e3b0bc3410a78db3439ff0fb9bb\]]{#classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb
label="classtensorflow_1_1serving_1_1BasicManager_a09e87e3b0bc3410a78db3439ff0fb9bb"}

void tensorflow::serving::BasicManager::LoadServable (

id,

done\_callback

)

Loads the servable with this id, and updates the serving map too. Calls
*done\_callback* with ok iff the servable was loaded successfully, else
returns an error status.

If using a thread-pool, this method transitions the servable harness to
kLoading state, schedules the load and returns, otherwise it completes
the load before returning.

REQUIRES: This manager should have been managing this servable already,
for it to be loaded, else we call *done\_callback* with an error status.
Do not call this multiple times on the same servable. Only one of those
will succeed and the rest will fail with an error status.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_ac2759caea67d3d37b9dba31589f9ef1d\]]{#classtensorflow_1_1serving_1_1BasicManager_ac2759caea67d3d37b9dba31589f9ef1d
label="classtensorflow_1_1serving_1_1BasicManager_ac2759caea67d3d37b9dba31589f9ef1d"}

Status tensorflow::serving::BasicManager::ManageServable (

servable

)

Starts managing the servable.

Returns an error if given a servable that is already being managed.

If *servable* is in an error state, this method does **not** return an
error. Instead, the manager accepts the servable, puts it in state
kError (with a notification sent to the event bus), and then immediately
stops managing it. This behavior facilitates uniform handling of errors
that occur in sources (e.g. invalid file path to servable data) and ones
that occur in the manager (e.g. insufficient resources to load
servable).
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a72406e3aedfa0084e24f2bd8ec7efdcc\]]{#classtensorflow_1_1serving_1_1BasicManager_a72406e3aedfa0084e24f2bd8ec7efdcc
label="classtensorflow_1_1serving_1_1BasicManager_a72406e3aedfa0084e24f2bd8ec7efdcc"}

template$<$typename T $>$\
Status
tensorflow::serving::BasicManager::ManageServableWithAdditionalState (

servable,

additional\_state

)

Similar to the above method, but callers, usually other managers built
on top of this one, can associate additional state with the servable.
Additional state may be ACL or lifetime metadata for that servable. The
ownership of the state is transferred to this class.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a3209cd82cbb5eac79bc3238b3c6bec43\]]{#classtensorflow_1_1serving_1_1BasicManager_a3209cd82cbb5eac79bc3238b3c6bec43
label="classtensorflow_1_1serving_1_1BasicManager_a3209cd82cbb5eac79bc3238b3c6bec43"}

Status tensorflow::serving::BasicManager::StopManagingServable (

id

)

Tells the manager to stop managing this servable. Requires that the
servable is currently being managed and that its state is one of {kNew,
kError, kDisabled}.
[\[classtensorflow\_1\_1serving\_1\_1BasicManager\_a97af7156e38c29225534bacdeefe9408\]]{#classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408
label="classtensorflow_1_1serving_1_1BasicManager_a97af7156e38c29225534bacdeefe9408"}

void tensorflow::serving::BasicManager::UnloadServable (

id,

done\_callback

)

Unloads the servable with this id, and updates the serving map too.
Calls *done\_callback* with ok iff the servable was unloaded
successfully, else returns an error status.

If using a thread-pool, this method transitions the servable harness to
kQuiescing state, schedules the unload and returns, otherwise it
completes the unload before returning.

REQUIRES: This manager should have loaded and made this servable
available, for it to be unloaded, else calls *done\_callback* with an
error status. Do not call this multiple times on the same servable. Only
one of those will succeed and the rest will fail with an error status.

The documentation for this class was generated from the following files:

tensorflow\_serving/core/basic\_manager.h

tensorflow\_serving/core/basic\_manager.cc
