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
-   [AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
-   [Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Attributes](#pub-attribs) \| [List of all
members](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::AspiredVersionsManager::Options Struct Reference
:::
:::
:::

::: {.contents}
`#include <aspired_versions_manager.h>`

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::AspiredVersionsManager::Options:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-attribs} Public Attributes {#public-attributes .groupheader}
----------------------------------
:::

std::unique\_ptr\<
[ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.el}
\> 

[resource\_tracker](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68571485293a22013658ecaff027b0a1){.el}

 

int64\_t 

[manage\_state\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a60e52c6ea540f1a1bfad9a8987699684){.el}
= 100 \* 1000

 

[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}
\> \* 

[servable\_event\_bus](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac021adf80573b8c2e0c61688b43f6130){.el}
= nullptr

 

[]{#a921d700e38f7e4f6add9288beb0506e5} std::unique\_ptr\<
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}
\> 

[aspired\_version\_policy](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a921d700e38f7e4f6add9288beb0506e5){.el}

 

The
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}
to use for the manager. Must be non-null.\

 

CustomSortActionsFn 

[custom\_sort\_actions](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68dce64ddf3bec5995ad7161c03efdb9){.el}

 

uint32 

[num\_load\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#aae4c93fdb83f2538e44df55f3669d38e){.el}
= 0

 

uint32 

[num\_unload\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a6c54dcb0499ef952eca4fdb364aa4859){.el}
= 0

 

uint32 

[max\_num\_load\_retries](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a2d3ca06a39d39b03efd513250ce1cf89){.el}
= 5

 

int64\_t 

[load\_retry\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ad44f1e8c79d9b60cc87bd616b2f02169){.el}
= 1LL \* 60 \* 1000 \* 1000

 

[]{#a0784e23b8eebd22ea3663794fb32b692} std::function\<
bool(absl::Status)\> 

**should\_retry\_model\_load**

 

[]{#aa0667eb3976a0aafc2e18973051c5831} bool 

**flush\_filesystem\_caches** = false

 

Env \* 

[env](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a8f08cac3875a829ae408727f852269e7){.el}
= Env::Default()

 

PreLoadHook 

[pre\_load\_hook](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac16d5d89359873e7004b4a64c2c54a4f){.el}

 

[]{#aa6a0217f4d0b8837e78a1b603a9accd2} bool 

**enable\_reload\_servables\_with\_error** = false

 

[]{#ac660188e05ac8415d3881e3d5a292ccc} bool 

**with\_current\_context** = false

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
Config options and pluggable objects that will be used by the
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}.
:::

Member Data Documentation {#member-data-documentation .groupheader}
-------------------------

[]{#a68dce64ddf3bec5995ad7161c03efdb9}

[[◆ ](#a68dce64ddf3bec5995ad7161c03efdb9)]{.permalink}custom\_sort\_actions {#custom_sort_actions .memtitle}
---------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------------------
  CustomSortActionsFn tensorflow::serving::AspiredVersionsManager::Options::custom\_sort\_actions
  -------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
Given a list of ServableAction, each ServableAction representing the
chosen version for that servable, this provides a custom sort order on
which action to take first. Useful when certain servable needs to be
loaded or unloaded before some other servable
:::
:::

[]{#a8f08cac3875a829ae408727f852269e7}

[[◆ ](#a8f08cac3875a829ae408727f852269e7)]{.permalink}env {#env .memtitle}
---------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------------------
  Env\* tensorflow::serving::AspiredVersionsManager::Options::env = Env::Default()
  ----------------------------------------------------------------------------------
:::

::: {.memdoc}
The environment to use for starting threads in the thread-pool or for
sleeping.
:::
:::

[]{#ad44f1e8c79d9b60cc87bd616b2f02169}

[[◆ ](#ad44f1e8c79d9b60cc87bd616b2f02169)]{.permalink}load\_retry\_interval\_micros {#load_retry_interval_micros .memtitle}
-----------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------------------------------------------------------------------------------
  int64\_t tensorflow::serving::AspiredVersionsManager::Options::load\_retry\_interval\_micros = 1LL \* 60 \* 1000 \* 1000
  --------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
The interval, in microseconds, between each servable load retry. If set
negative, we don\'t wait. Default: 1 minute.
:::
:::

[]{#a60e52c6ea540f1a1bfad9a8987699684}

[[◆ ](#a60e52c6ea540f1a1bfad9a8987699684)]{.permalink}manage\_state\_interval\_micros {#manage_state_interval_micros .memtitle}
-------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------------------------------------------------------------------
  int64\_t tensorflow::serving::AspiredVersionsManager::Options::manage\_state\_interval\_micros = 100 \* 1000
  --------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
The periodicity, in microseconds, of the thread which manages the state
of the servables. Default: 100 milliseconds. If this is set less than or
equal to 0, we don\'t run this thread at all.
:::
:::

[]{#a2d3ca06a39d39b03efd513250ce1cf89}

[[◆ ](#a2d3ca06a39d39b03efd513250ce1cf89)]{.permalink}max\_num\_load\_retries {#max_num_load_retries .memtitle}
-----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------------------------------------
  uint32 tensorflow::serving::AspiredVersionsManager::Options::max\_num\_load\_retries = 5
  ------------------------------------------------------------------------------------------
:::

::: {.memdoc}
Maximum number of times we retry loading a servable, after the first
failure, before we give up.
:::
:::

[]{#aae4c93fdb83f2538e44df55f3669d38e}

[[◆ ](#aae4c93fdb83f2538e44df55f3669d38e)]{.permalink}num\_load\_threads {#num_load_threads .memtitle}
------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------
  uint32 tensorflow::serving::AspiredVersionsManager::Options::num\_load\_threads = 0
  -------------------------------------------------------------------------------------
:::

::: {.memdoc}
The number of threads in the thread-pool used to load servables.

If set as 0, we don\'t use a thread-pool, and servable loads are
performed serially in the manager\'s main work loop.
:::
:::

[]{#a6c54dcb0499ef952eca4fdb364aa4859}

[[◆ ](#a6c54dcb0499ef952eca4fdb364aa4859)]{.permalink}num\_unload\_threads {#num_unload_threads .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------------------------------------
  uint32 tensorflow::serving::AspiredVersionsManager::Options::num\_unload\_threads = 0
  ---------------------------------------------------------------------------------------
:::

::: {.memdoc}
The number of threads in the thread-pool used to unload servables.

If set as 0, we don\'t use a thread-pool, and servable unloads are
performed serially in the manager\'s main work loop.
:::
:::

[]{#ac16d5d89359873e7004b4a64c2c54a4f}

[[◆ ](#ac16d5d89359873e7004b4a64c2c54a4f)]{.permalink}pre\_load\_hook {#pre_load_hook .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -----------------------------------------------------------------------------------
  PreLoadHook tensorflow::serving::AspiredVersionsManager::Options::pre\_load\_hook
  -----------------------------------------------------------------------------------
:::

::: {.memdoc}
Callback to be called just before a servable is to be loaded. This will
called on the same manager load thread which starts the load.
:::
:::

[]{#a68571485293a22013658ecaff027b0a1}

[[◆ ](#a68571485293a22013658ecaff027b0a1)]{.permalink}resource\_tracker {#resource_tracker .memtitle}
-----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  std::unique\_ptr\<[ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.el}\> tensorflow::serving::AspiredVersionsManager::Options::resource\_tracker
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
The resource tracker to use while managing servable resources. Optional.
If left as nullptr, we do not validate servable resource usage.
:::
:::

[]{#ac021adf80573b8c2e0c61688b43f6130}

[[◆ ](#ac021adf80573b8c2e0c61688b43f6130)]{.permalink}servable\_event\_bus {#servable_event_bus .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\<[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.el}\>\* tensorflow::serving::AspiredVersionsManager::Options::servable\_event\_bus = nullptr
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} to publish
servable state changes. This is optional, if unset, we don\'t publish.
:::
:::

------------------------------------------------------------------------

The documentation for this struct was generated from the following file:

-   tensorflow\_serving/core/[aspired\_versions\_manager.h](aspired__versions__manager_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
