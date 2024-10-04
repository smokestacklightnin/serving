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
-   [ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1ServableStateMonitor-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ServableStateMonitor Class Reference
:::
:::
:::

::: {.contents}
`#include <servable_state_monitor.h>`

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.el}

 

struct  

[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.el}

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

[]{#a5ef18d6969478a087530f5b77e0bd2f1} using 

**ServableName** = string

 

[]{#aacd5912de4ba934c46ad82db1c525ce3} using 

**Version** = int64

 

[]{#a8010e4b3453ae200256f3d56dd8f755e} using 

**VersionMap** = std::map\< Version,
[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.el},
std::greater\< Version \> \>

 

[]{#a61d0ee57a6dcd59e82e460c0d17a2604} using 

**ServableMap** = std::map\< ServableName, VersionMap \>

 

[]{#a58d43d766bb8316983316896f258498e} using 

**ServableSet** = std::set\< ServableName \>

 

[]{#a6dbb131b4d7c6f036da6e3ebed3b6ad1} using 

**BoundedLog** = std::deque\<
[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.el}
\>

 

using 

[ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.el}
= std::function\< void(bool reached\_goal\_state, const std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
ServableState::ManagerState \> &states\_reached)\>

 

[]{#a4c97d1fd2318e71b83eac646e27599c9} using 

**NotifyFn** = std::function\< void(const
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
&)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#a85cf3611dfc401b031f92c0cfa353bfd}  

**ServableStateMonitor**
([EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
\> \*bus, const
[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.el}
&options=[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.el}())

 

absl::optional\<
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
\> 

[GetState](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8fa6dd1536bbb85a55b3e41c1d2577d1){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)

 

absl::optional\<
[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.el}
\> 

[GetStateAndTime](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8ff54ab2471885168dba0b1a05be7bea){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)

 

VersionMap 

[GetVersionStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a501ef561e30709fe17f10c913d34bb1e){.el}
(const string &servable\_name) const TF\_LOCKS\_EXCLUDED(mu\_)

 

[]{#abc3c1c27b6b7c0e8ef9a42039ede74cc} ServableMap 

[GetAllServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#abc3c1c27b6b7c0e8ef9a42039ede74cc){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

Returns the current states of all tracked versions of all servables.\

 

ServableMap 

[GetLiveServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a522166e0255c93e87a6d63c3d17e3f38){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

void 

[ForgetUnloadedServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#ae3ad2a50b7fa7b695885fe913b70b029){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

[]{#af4623ec7d0e8c756bfe0603d879304c7} ServableSet 

**GetAvailableServableStates** () const TF\_LOCKS\_EXCLUDED(mu\_)

 

[]{#a2afc57f0eb671a3c3342c7dd71a9d6a7} BoundedLog 

[GetBoundedLog](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a2afc57f0eb671a3c3342c7dd71a9d6a7){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

Returns the current bounded log of handled servable state events.\

 

[]{#a06b073bf82b07c224227e1efa5d44603} void 

**NotifyWhenServablesReachState** (const std::vector\<
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
\> &servables, ServableState::ManagerState goal\_state, const
[ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.el}
&notifier\_fn) TF\_LOCKS\_EXCLUDED(mu\_)

 

bool 

[WaitUntilServablesReachStateWithTimeout](classtensorflow_1_1serving_1_1ServableStateMonitor.html#aa9579ee04bf76fa627d65d9cbbb7ccb7){.el}
(const std::vector\<
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
\> &servables, ServableState::ManagerState goal\_state, absl::Duration
timeout, std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
ServableState::ManagerState \> \*states\_reached=nullptr)
TF\_LOCKS\_EXCLUDED(mu\_) TF\_MUST\_USE\_RESULT

 

[]{#a3e01409c4f3d16789ae42ba9b5fd0b12} bool 

**WaitUntilServablesReachState** (const std::vector\<
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
\> &servables, ServableState::ManagerState goal\_state, std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
ServableState::ManagerState \> \*states\_reached=nullptr)
TF\_MUST\_USE\_RESULT

 

[]{#a6d8b172f93c8e74937c4594dd332c154} void 

**Notify** (const NotifyFn &notify\_fn)
TF\_LOCKS\_EXCLUDED(notify\_mu\_)

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A utility that listens to an
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}&lt;[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}\>,
and keeps track of the state of each servable mentioned on the bus. The
intended use case is to track the states of servables in a
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el}.

Offers an interface for querying the servable states. It may be useful
as the basis for dashboards, as well as for testing a manager.

IMPORTANT: You must create this monitor before arranging for events to
be published on the event bus, e.g. giving the event bus to a
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el}.
:::

Member Typedef Documentation {#member-typedef-documentation .groupheader}
----------------------------

[]{#a6b64d18d981941012439766e57bd8d66}

[[◆ ](#a6b64d18d981941012439766e57bd8d66)]{.permalink}ServableStateNotifierFn {#servablestatenotifierfn .memtitle}
-----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  using [tensorflow::serving::ServableStateMonitor::ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.el} = std::function\<void( bool reached\_goal\_state, const std::map\<[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}, ServableState::ManagerState\>& states\_reached)\>
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
Notifies when all of the servables have reached the \'goal\_state\'.

Servables can be specified in two ways:

1.  As specific versions of a servable stream name. In this case, we
    check whether the specific version has reached the \'goal\_state\'
    or kEnd.
2.  As latest versions, in which case any version for a servable stream
    name will be matched against the \'goal\_state\' or kEnd.

We call the \'notifier\_fn\' when both conditions are true -

1.  All of the specific servable requests have either reached the
    \'goal\_state\' or kEnd.
2.  All of the latest servable requests have reached \'goal\_state\' or
    kEnd. The \'notifier\_fn\' will be called only once, and not
    repeatedly.

The \'reached\_goal\_state\' argument is set as true iff all of the
specific servables have reached \'goal\_state\'. So callers should
verify that \'reached\_goal\_state\' is true in the \'notifier\_fn\'.

The \'states\_reached\' argument is populated with the servable\'s id
and the state it reached. The state would be \'goal\_state\' if
\'reached\_goal\_state\' is true, else it will contain one or more
servables in kEnd state. For latest servable requests, the servable id
will be the id of the servable in the stream which reached the state.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ae3ad2a50b7fa7b695885fe913b70b029}

[[◆ ](#ae3ad2a50b7fa7b695885fe913b70b029)]{.permalink}ForgetUnloadedServableStates() {#forgetunloadedservablestates .memtitle}
------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------------------------ --- -- --- --
  void tensorflow::serving::ServableStateMonitor::ForgetUnloadedServableStates   (      )   
  ------------------------------------------------------------------------------ --- -- --- --
:::

::: {.memdoc}
Removes all servable versions from the ServableMap whose states have
transitioned to kEnd.
:::
:::

[]{#a522166e0255c93e87a6d63c3d17e3f38}

[[◆ ](#a522166e0255c93e87a6d63c3d17e3f38)]{.permalink}GetLiveServableStates() {#getliveservablestates .memtitle}
-----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------------------------------------------------- --- -- --- -------
  ServableStateMonitor::ServableMap tensorflow::serving::ServableStateMonitor::GetLiveServableStates   (      )   const
  ---------------------------------------------------------------------------------------------------- --- -- --- -------
:::

::: {.memdoc}
Returns the current states of all versions of all servables which have
not transitioned to state ServableState::ManagerState::kEnd.
:::
:::

[]{#a8fa6dd1536bbb85a55b3e41c1d2577d1}

[[◆ ](#a8fa6dd1536bbb85a55b3e41c1d2577d1)]{.permalink}GetState() {#getstate .memtitle}
----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ---------------- --- -------
  absl::optional\< [ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el} \> tensorflow::serving::ServableStateMonitor::GetState   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *servable\_id*   )   const
  ------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ---------------- --- -------
:::

::: {.memdoc}
Returns the current state of one servable, or nullopt if that servable
is not being tracked.
:::
:::

[]{#a8ff54ab2471885168dba0b1a05be7bea}

[[◆ ](#a8ff54ab2471885168dba0b1a05be7bea)]{.permalink}GetStateAndTime() {#getstateandtime .memtitle}
-----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ---------------- --- -------
  absl::optional\< [ServableStateMonitor::ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.el} \> tensorflow::serving::ServableStateMonitor::GetStateAndTime   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *servable\_id*   )   const
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ---------------- --- -------
:::

::: {.memdoc}
Returns the current state and time of one servable, or nullopt if that
servable is not being tracked.
:::
:::

[]{#a501ef561e30709fe17f10c913d34bb1e}

[[◆ ](#a501ef561e30709fe17f10c913d34bb1e)]{.permalink}GetVersionStates() {#getversionstates .memtitle}
------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------------------------------------------- --- ----------------- ------------------ --- -------
  ServableStateMonitor::VersionMap tensorflow::serving::ServableStateMonitor::GetVersionStates   (   const string &    *servable\_name*   )   const
  ---------------------------------------------------------------------------------------------- --- ----------------- ------------------ --- -------
:::

::: {.memdoc}
Returns the current states of all tracked versions of the given
servable, if any.
:::
:::

[]{#aa9579ee04bf76fa627d65d9cbbb7ccb7}

[[◆ ](#aa9579ee04bf76fa627d65d9cbbb7ccb7)]{.permalink}WaitUntilServablesReachStateWithTimeout() {#waituntilservablesreachstatewithtimeout .memtitle}
-----------------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------------------------- --- ------------------------------------------------------------------------------------------------------------------ --------------------------------
  bool tensorflow::serving::ServableStateMonitor::WaitUntilServablesReachStateWithTimeout   (   const std::vector\< [ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el} \> &               *servables*,
                                                                                                ServableState::ManagerState                                                                                        *goal\_state*,
                                                                                                absl::Duration                                                                                                     *timeout*,
                                                                                                std::map\< [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}, ServableState::ManagerState \> \*    *states\_reached* = `nullptr` 
                                                                                            )                                                                                                                      
  ----------------------------------------------------------------------------------------- --- ------------------------------------------------------------------------------------------------------------------ --------------------------------
:::

::: {.memdoc}
Similar to NotifyWhenServablesReachState(\...), but instead of
notifying, we wait until the \'goal\_state\' or kEnd is reached.

To understand the return value and the return parameter
\'states\_reached\', please read the documentation on
NotifyWhenServablesReachState(\...).
WaitUntilServablesReachStateWithTimeout and WaitUntilServablesReachState
perform the same function, but the former has a timeout while the latter
waits indefinitely.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[servable\_state\_monitor.h](servable__state__monitor_8h_source.html){.el}
-   tensorflow\_serving/core/servable\_state\_monitor.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
