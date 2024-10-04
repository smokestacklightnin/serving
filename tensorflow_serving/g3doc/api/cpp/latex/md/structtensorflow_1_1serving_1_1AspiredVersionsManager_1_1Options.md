::: {#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options"}

\#include $<$aspired\_versions\_manager.h$>$

Collaboration diagram for
tensorflow::serving::AspiredVersionsManager::Options:

![image](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options__coll__graph.pdf){width="310pt"}

std::unique\_ptr$<$
[ResourceTracker](#classtensorflow_1_1serving_1_1ResourceTracker) $>$
[resource\_tracker](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68571485293a22013658ecaff027b0a1)

int64\_t
[manage\_state\_interval\_micros](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a60e52c6ea540f1a1bfad9a8987699684)
= 100 $\ast$ 1000

[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$
[servable\_event\_bus](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac021adf80573b8c2e0c61688b43f6130)
= nullptr

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a921d700e38f7e4f6add9288beb0506e5\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a921d700e38f7e4f6add9288beb0506e5
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a921d700e38f7e4f6add9288beb0506e5"}
std::unique\_ptr$<$
[AspiredVersionPolicy](#classtensorflow_1_1serving_1_1AspiredVersionPolicy)
$>$
[aspired\_version\_policy](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a921d700e38f7e4f6add9288beb0506e5)

*The
[AspiredVersionPolicy](#classtensorflow_1_1serving_1_1AspiredVersionPolicy)
to use for the manager. Must be non-null.*

CustomSortActionsFn
[custom\_sort\_actions](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68dce64ddf3bec5995ad7161c03efdb9)

uint32
[num\_load\_threads](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aae4c93fdb83f2538e44df55f3669d38e)
= 0

uint32
[num\_unload\_threads](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a6c54dcb0499ef952eca4fdb364aa4859)
= 0

uint32
[max\_num\_load\_retries](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a2d3ca06a39d39b03efd513250ce1cf89)
= 5

int64\_t
[load\_retry\_interval\_micros](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ad44f1e8c79d9b60cc87bd616b2f02169)
= 1LL $\ast$ 60 $\ast$ 1000 $\ast$ 1000

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a0784e23b8eebd22ea3663794fb32b692\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a0784e23b8eebd22ea3663794fb32b692
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a0784e23b8eebd22ea3663794fb32b692"}
std::function$<$ bool(absl::Status)$>$ **should\_retry\_model\_load**

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_aa0667eb3976a0aafc2e18973051c5831\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aa0667eb3976a0aafc2e18973051c5831
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aa0667eb3976a0aafc2e18973051c5831"}
bool **flush\_filesystem\_caches** = false

Env $\ast$
[env](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a8f08cac3875a829ae408727f852269e7)
= Env::Default()

PreLoadHook
[pre\_load\_hook](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac16d5d89359873e7004b4a64c2c54a4f)

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_aa6a0217f4d0b8837e78a1b603a9accd2\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aa6a0217f4d0b8837e78a1b603a9accd2
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aa6a0217f4d0b8837e78a1b603a9accd2"}
bool **enable\_reload\_servables\_with\_error** = false

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_ac660188e05ac8415d3881e3d5a292ccc\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac660188e05ac8415d3881e3d5a292ccc
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac660188e05ac8415d3881e3d5a292ccc"}
bool **with\_current\_context** = false

Config options and pluggable objects that will be used by the
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager).

[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a68dce64ddf3bec5995ad7161c03efdb9\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68dce64ddf3bec5995ad7161c03efdb9
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68dce64ddf3bec5995ad7161c03efdb9"}
CustomSortActionsFn
tensorflow::serving::AspiredVersionsManager::Options::custom\_sort\_actions

Given a list of ServableAction, each ServableAction representing the
chosen version for that servable, this provides a custom sort order on
which action to take first. Useful when certain servable needs to be
loaded or unloaded before some other servable
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a8f08cac3875a829ae408727f852269e7\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a8f08cac3875a829ae408727f852269e7
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a8f08cac3875a829ae408727f852269e7"}
Env$\ast$ tensorflow::serving::AspiredVersionsManager::Options::env =
Env::Default()

The environment to use for starting threads in the thread-pool or for
sleeping.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_ad44f1e8c79d9b60cc87bd616b2f02169\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ad44f1e8c79d9b60cc87bd616b2f02169
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ad44f1e8c79d9b60cc87bd616b2f02169"}
int64\_t
tensorflow::serving::AspiredVersionsManager::Options::load\_retry\_interval\_micros
= 1LL $\ast$ 60 $\ast$ 1000 $\ast$ 1000

The interval, in microseconds, between each servable load retry. If set
negative, we dont wait. Default: 1 minute.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a60e52c6ea540f1a1bfad9a8987699684\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a60e52c6ea540f1a1bfad9a8987699684
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a60e52c6ea540f1a1bfad9a8987699684"}
int64\_t
tensorflow::serving::AspiredVersionsManager::Options::manage\_state\_interval\_micros
= 100 $\ast$ 1000

The periodicity, in microseconds, of the thread which manages the state
of the servables. Default: 100 milliseconds. If this is set less than or
equal to 0, we dont run this thread at all.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a2d3ca06a39d39b03efd513250ce1cf89\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a2d3ca06a39d39b03efd513250ce1cf89
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a2d3ca06a39d39b03efd513250ce1cf89"}
uint32
tensorflow::serving::AspiredVersionsManager::Options::max\_num\_load\_retries
= 5

Maximum number of times we retry loading a servable, after the first
failure, before we give up.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_aae4c93fdb83f2538e44df55f3669d38e\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aae4c93fdb83f2538e44df55f3669d38e
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_aae4c93fdb83f2538e44df55f3669d38e"}
uint32
tensorflow::serving::AspiredVersionsManager::Options::num\_load\_threads
= 0

The number of threads in the thread-pool used to load servables.

If set as 0, we dont use a thread-pool, and servable loads are performed
serially in the managers main work loop.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a6c54dcb0499ef952eca4fdb364aa4859\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a6c54dcb0499ef952eca4fdb364aa4859
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a6c54dcb0499ef952eca4fdb364aa4859"}
uint32
tensorflow::serving::AspiredVersionsManager::Options::num\_unload\_threads
= 0

The number of threads in the thread-pool used to unload servables.

If set as 0, we dont use a thread-pool, and servable unloads are
performed serially in the managers main work loop.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_ac16d5d89359873e7004b4a64c2c54a4f\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac16d5d89359873e7004b4a64c2c54a4f
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac16d5d89359873e7004b4a64c2c54a4f"}
PreLoadHook
tensorflow::serving::AspiredVersionsManager::Options::pre\_load\_hook

Callback to be called just before a servable is to be loaded. This will
called on the same manager load thread which starts the load.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_a68571485293a22013658ecaff027b0a1\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68571485293a22013658ecaff027b0a1
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_a68571485293a22013658ecaff027b0a1"}
std::unique\_ptr$<$[ResourceTracker](#classtensorflow_1_1serving_1_1ResourceTracker)$>$
tensorflow::serving::AspiredVersionsManager::Options::resource\_tracker

The resource tracker to use while managing servable resources. Optional.
If left as nullptr, we do not validate servable resource usage.
[\[structtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_1\_1Options\_ac021adf80573b8c2e0c61688b43f6130\]]{#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac021adf80573b8c2e0c61688b43f6130
label="structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_ac021adf80573b8c2e0c61688b43f6130"}
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$[ServableState](#structtensorflow_1_1serving_1_1ServableState)$>$$\ast$
tensorflow::serving::AspiredVersionsManager::Options::servable\_event\_bus
= nullptr

[EventBus](#classtensorflow_1_1serving_1_1EventBus) to publish servable
state changes. This is optional, if unset, we dont publish.

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/aspired\_versions\_manager.h
