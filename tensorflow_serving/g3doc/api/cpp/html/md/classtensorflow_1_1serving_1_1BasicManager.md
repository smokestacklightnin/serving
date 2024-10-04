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
-   [BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1BasicManager-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::BasicManager Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <basic_manager.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::BasicManager:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1BasicManager__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::BasicManager:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1BasicManager__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Options](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html){.el}

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

[]{#abeacf431a3e838da2b1602828f0c0eb2} using 

**PreLoadHook** = std::function\< void(const
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &)\>

 

using 

[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el}
= std::function\< void(const Status &status)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

 

[\~BasicManager](classtensorflow_1_1serving_1_1BasicManager.html#a492123b8bb97709184ddb57772e3ccf3){.el}
() override

 

std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639){.el}
() const override

 

[]{#ad58907b2d551d693d13b6c979c4bd511} Status 

**GetUntypedServableHandle** (const
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
&request, std::unique\_ptr\<
[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.el}
\> \*untyped\_handle) override

 

[]{#a675a065bc2acf6229be899618e190b2b} std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
std::unique\_ptr\<
[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.el}
\> \> 

**GetAvailableUntypedServableHandles** () const override

 

Status 

[ManageServable](classtensorflow_1_1serving_1_1BasicManager.html#ac2759caea67d3d37b9dba31589f9ef1d){.el}
([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>\> servable)

 

template\<typename T \>

Status 

[ManageServableWithAdditionalState](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc){.el}
([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>\> servable,
std::unique\_ptr\< T \> additional\_state)

 

Status 

[StopManagingServable](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id)

 

std::vector\< string \> 

[GetManagedServableNames](classtensorflow_1_1serving_1_1BasicManager.html#afbdc3d0ed83559c7d8b3b0092194ead6){.el}
() const

 

template\<typename T = std::nullptr\_t\>

std::vector\<
[ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\<
T \> \> 

[GetManagedServableStateSnapshots](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826){.el}
(const string &servable\_name) const

 

template\<typename T = std::nullptr\_t\>

absl::optional\<
[ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\<
T \> \> 

[GetManagedServableStateSnapshot](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id)

 

template\<typename T \>

T \* 

[GetAdditionalServableState](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id)

 

void 

[LoadServable](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id,
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el}
done\_callback)

 

void 

[CancelLoadServableRetry](classtensorflow_1_1serving_1_1BasicManager.html#a84dca5ec1ecc28421d5ab020beac2ee3){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id)

 

void 

[UnloadServable](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id,
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el}
done\_callback)

 

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

[]{#af8f89ab0900a43b12cfbd9b2185fbfde} static Status 

**Create**
([Options](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html){.el}
options, std::unique\_ptr\<
[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el} \>
\*manager)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a2158193bbefd406c1206927ce42fb865} class 

**AspiredVersionsManager**

 

[]{#aa40648d98e6ee77b0bc8b0a272b54410} class 

**test\_util::BasicManagerTestAccess**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
Helps manage the lifecycle of servables including loading, serving and
unloading them. The manager accepts servables in the form of Loaders.

We start managing a servable through one of the ManageServable\*
methods. You can go on to load the servable after this by calling
[LoadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}.
Loading will also make the servable available to serve. Once you decide
to unload it, you can call
[UnloadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.el}
on it, which will make it unavailable to serve, then unload the
servable.

Servables are retained until
[StopManagingServable()](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43){.el}
is called. This allows a higher level manager with more information to
decide when it\'s safe to forget about a servable.

[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}
tracks the resources (e.g. RAM) used by loaded servables, and only
allows loading new servables that fit within the overall resource pool.

[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el} can
be configured to use a thread-pool to do it\'s load and unloads. This
makes the
[LoadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}
and
[UnloadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.el}
methods schedule the load/unloads rather than executing them
synchronously. If there are more pending load/unloads than threads in
the thread pool, they are processed in FIFO order.

In the presence of loaders that over-estimate their servables\' resource
needs and/or only bind their servables\' resources to device instances,
load/unload concurrency can be reduced below the thread-pool size. That
is because we may have to wait for one servable\'s load/unload to finish
to pin down the resource availability for loading another servable.

REQUIRES:

1.  Order of method calls -
    [ManageServable()](classtensorflow_1_1serving_1_1BasicManager.html#ac2759caea67d3d37b9dba31589f9ef1d){.el}
    (and variants) -\>
    [LoadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}
    -\>
    [UnloadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.el}
    -\>
    [StopManagingServable()](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43){.el}.
2.  Do not schedule concurrent load and unloads of the same servable.
3.  Do not call load or unload multiple times on the same servable.

This class is thread-safe.

Example usage:

``` {.fragment}
const ServableId id = {kServableName, 0};
std::unique_ptr&lt;Loader> loader = ...;
...
BasicManager manager;
TF_CHECK_OK(manager.ManageServable(
  CreateServableData(id, std::move(loader))));
TF_CHECK_OK(manager.LoadServable(id));

...
TF_CHECK_OK(manager.GetServableHandle(
    ServableRequest::Latest(kServableName), &handle));
...

TF_CHECK_OK(manager.UnloadServable(id));
TF_CHECK_OK(manager.StopManagingServable(id)); 
```
:::

Member Typedef Documentation {#member-typedef-documentation .groupheader}
----------------------------

[]{#a8ee7a19d059b362c0702686d981bf5fc}

[[◆ ](#a8ee7a19d059b362c0702686d981bf5fc)]{.permalink}DoneCallback {#donecallback .memtitle}
------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  using [tensorflow::serving::BasicManager::DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el} = std::function\<void(const Status& status)\>
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
Callback called at the end of {Load,Unload}Servable(). We pass in the
status of the operation to the callback.
:::
:::

Constructor & Destructor Documentation {#constructor-destructor-documentation .groupheader}
--------------------------------------

[]{#a492123b8bb97709184ddb57772e3ccf3}

[[◆ ](#a492123b8bb97709184ddb57772e3ccf3)]{.permalink}\~BasicManager() {#basicmanager .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[override]{.mlabel}]{.mlabels}   |
|  -------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   tensorflow::serving::BasicMana  |                                   |
| ger::\~BasicManager   (      )    |                                   |
|                                   |                                   |
|  -------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
If configured to use a load/unload thread-pool, waits until all
scheduled loads and unloads have finished and then destroys the set of
threads.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a84dca5ec1ecc28421d5ab020beac2ee3}

[[◆ ](#a84dca5ec1ecc28421d5ab020beac2ee3)]{.permalink}CancelLoadServableRetry() {#cancelloadservableretry .memtitle}
-------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
  void tensorflow::serving::BasicManager::CancelLoadServableRetry   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *id*   )   
  ----------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
:::

::: {.memdoc}
Cancels retrying the servable load during
[LoadServable()](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}
by replacing the
[LoaderHarness::should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435 "Returns true if the servable should be retried."){.el}
with a function that always returns false. Does nothing if the servable
isn\'t managed.

If the retries are cancelled, the servable goes into a state dependent
on the last Load() called on it. If the last Load() was successful, it
will be in state kReady, else in kError.
:::
:::

[]{#a99dbea960f6d47461dbfca5bfa149335}

[[◆ ](#a99dbea960f6d47461dbfca5bfa149335)]{.permalink}GetAdditionalServableState() {#getadditionalservablestate .memtitle}
----------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  -------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
  T \* tensorflow::serving::BasicManager::GetAdditionalServableState   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *id*   )   
  -------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
:::

::: {.memdoc}

Returns
:   the additional state for the servable. Returns nullptr if there is
    no additional state setup or if there is a type mismatch between
    what was setup and what is being asked for.

REQUIRES: This manager should have been managing this servable already,
else we return nullptr.
:::
:::

[]{#afbdc3d0ed83559c7d8b3b0092194ead6}

[[◆ ](#afbdc3d0ed83559c7d8b3b0092194ead6)]{.permalink}GetManagedServableNames() {#getmanagedservablenames .memtitle}
-------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------------------------------ --- -- --- -------
  std::vector\< string \> tensorflow::serving::BasicManager::GetManagedServableNames   (      )   const
  ------------------------------------------------------------------------------------ --- -- --- -------
:::

::: {.memdoc}

Returns
:   the names of all the servables managed by this manager. The names
    will be duplicate-free and not in any particular order.
:::
:::

[]{#af681f56bbef07ab201f25c0097f73e75}

[[◆ ](#af681f56bbef07ab201f25c0097f73e75)]{.permalink}GetManagedServableStateSnapshot() {#getmanagedservablestatesnapshot .memtitle}
---------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
  absl::optional\< [ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\< T \> \> tensorflow::serving::BasicManager::GetManagedServableStateSnapshot   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *id*   )   
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
:::

::: {.memdoc}

Returns
:   the state snapshot of a particular servable-id managed by this
    manager if available.

REQUIRES: This manager should have been managing this servable already,
else we return nullopt.
:::
:::

[]{#a31716665d8df8451d379363309dac826}

[[◆ ](#a31716665d8df8451d379363309dac826)]{.permalink}GetManagedServableStateSnapshots() {#getmanagedservablestatesnapshots .memtitle}
----------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ----------------- ------------------ --- -------
  std::vector\< [ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\< T \> \> tensorflow::serving::BasicManager::GetManagedServableStateSnapshots   (   const string &    *servable\_name*   )   const
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --- ----------------- ------------------ --- -------
:::

::: {.memdoc}

Returns
:   the state snapshots of all the servables of a particular stream,
    managed by this manager.

T is the additional-state type, if any.
:::
:::

[]{#a3c004d32952596c1f5759b1cfcc3c639}

[[◆ ](#a3c004d32952596c1f5759b1cfcc3c639)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
--------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------------------------------- | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   std::vector\< [ServableId](st   |                                   |
| ructtensorflow_1_1serving_1_1Serv |                                   |
| ableId.html){.el} \> tensorflow:: |                                   |
| serving::BasicManager::ListAvaila |                                   |
| bleServableIds   (      )   const |                                   |
|   ------------------------------- |                                   |
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

[]{#a09e87e3b0bc3410a78db3439ff0fb9bb}

[[◆ ](#a09e87e3b0bc3410a78db3439ff0fb9bb)]{.permalink}LoadServable() {#loadservable .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------ --- --------------------------------------------------------------------------------------------------------- -------------------
  void tensorflow::serving::BasicManager::LoadServable   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &                                 *id*,
                                                             [DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el}    *done\_callback* 
                                                         )                                                                                                             
  ------------------------------------------------------ --- --------------------------------------------------------------------------------------------------------- -------------------
:::

::: {.memdoc}
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
:::
:::

[]{#ac2759caea67d3d37b9dba31589f9ef1d}

[[◆ ](#ac2759caea67d3d37b9dba31589f9ef1d)]{.permalink}ManageServable() {#manageservable .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------- --- ---------------------------------------------------------------------------------------------------------------------------------------------------------- ------------ --- --
  Status tensorflow::serving::BasicManager::ManageServable   (   [ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\< std::unique\_ptr\< [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>\>    *servable*   )   
  ---------------------------------------------------------- --- ---------------------------------------------------------------------------------------------------------------------------------------------------------- ------------ --- --
:::

::: {.memdoc}
Starts managing the servable.

Returns an error if given a servable that is already being managed.

If *servable* is in an error state, this method does **not** return an
error. Instead, the manager accepts the servable, puts it in state
kError (with a notification sent to the event bus), and then immediately
stops managing it. This behavior facilitates uniform handling of errors
that occur in sources (e.g. invalid file path to servable data) and ones
that occur in the manager (e.g. insufficient resources to load
servable).
:::
:::

[]{#a72406e3aedfa0084e24f2bd8ec7efdcc}

[[◆ ](#a72406e3aedfa0084e24f2bd8ec7efdcc)]{.permalink}ManageServableWithAdditionalState() {#manageservablewithadditionalstate .memtitle}
-----------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  ----------------------------------------------------------------------------- --- ---------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------
  Status tensorflow::serving::BasicManager::ManageServableWithAdditionalState   (   [ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\< std::unique\_ptr\< [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>\>    *servable*,
                                                                                    std::unique\_ptr\< T \>                                                                                                                                    *additional\_state* 
                                                                                )                                                                                                                                                              
  ----------------------------------------------------------------------------- --- ---------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------
:::

::: {.memdoc}
Similar to the above method, but callers, usually other managers built
on top of this one, can associate additional state with the servable.
Additional state may be ACL or lifetime metadata for that servable. The
ownership of the state is transferred to this class.
:::
:::

[]{#a3209cd82cbb5eac79bc3238b3c6bec43}

[[◆ ](#a3209cd82cbb5eac79bc3238b3c6bec43)]{.permalink}StopManagingServable() {#stopmanagingservable .memtitle}
----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
  Status tensorflow::serving::BasicManager::StopManagingServable   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &    *id*   )   
  ---------------------------------------------------------------- --- ---------------------------------------------------------------------------- ------ --- --
:::

::: {.memdoc}
Tells the manager to stop managing this servable. Requires that the
servable is currently being managed and that its state is one of {kNew,
kError, kDisabled}.
:::
:::

[]{#a97af7156e38c29225534bacdeefe9408}

[[◆ ](#a97af7156e38c29225534bacdeefe9408)]{.permalink}UnloadServable() {#unloadservable .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------- --- --------------------------------------------------------------------------------------------------------- -------------------
  void tensorflow::serving::BasicManager::UnloadServable   (   const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} &                                 *id*,
                                                               [DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el}    *done\_callback* 
                                                           )                                                                                                             
  -------------------------------------------------------- --- --------------------------------------------------------------------------------------------------------- -------------------
:::

::: {.memdoc}
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
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[basic\_manager.h](basic__manager_8h_source.html){.el}
-   tensorflow\_serving/core/basic\_manager.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
