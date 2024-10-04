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
-   [AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Protected Member
Functions](#pro-static-methods) \| [Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1AspiredVersionPolicy-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::AspiredVersionPolicy Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <aspired_version_policy.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::AspiredVersionPolicy:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1AspiredVersionPolicy__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.el}

 

Action and the id of the servable associated with it.
[More\...](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html#details)\

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

enum class  

[Action](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85){.el}
: int {
[kLoad](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a){.el}
,
[kUnload](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1){.el}
}

 

The different actions that could be recommended by a policy.
[More\...](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85)\

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

virtual absl::optional\<
[ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.el}
\> 

[GetNextAction](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a86135f0f3225cd2999033da63e013214){.el}
(const std::vector\<
[AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.el}
\> &all\_versions) const =0

 

[]{#pro-static-methods} Static Protected Member Functions {#static-protected-member-functions .groupheader}
---------------------------------------------------------

static absl::optional\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[GetHighestAspiredNewServableId](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a71bde7aea4c6116cede2714758688857){.el}
(const std::vector\<
[AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.el}
\> &all\_versions)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a2ad82a88769861ba90f16c53008216f1} class 

**AspiredVersionPolicyTest**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
An interface for the policy to be applied for transitioning servable
versions in a servable stream.

Policies should be entirely stateless and idempotent. Asking the same
policy multiple times for the next action, for an identical vector of
AspiredServableStateSnapshots, should return the same result.

If additional state is required to implement a Policy, such state shall
be shared via AspiredServableStateSnapshots. Depending on the kind of
state, the most likely candidates for originating or tracking state are
Sources or the Harness and
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el}.
:::

Member Enumeration Documentation {#member-enumeration-documentation .groupheader}
--------------------------------

[]{#a5681f3f1c6c14f088084b29438e6fa85}

[[◆ ](#a5681f3f1c6c14f088084b29438e6fa85)]{.permalink}Action {#action .memtitle}
------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ----------------------------    | [[strong]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
|   enum [tensorflow::serving:      |                                   |
| :AspiredVersionPolicy::Action](cl |                                   |
| asstensorflow_1_1serving_1_1Aspir |                                   |
| edVersionPolicy.html#a5681f3f1c6c |                                   |
| 14f088084b29438e6fa85){.el} : int |                                   |
|   ----------------------------    |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
The different actions that could be recommended by a policy.

Enumerator
:::
:::

[]{#a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a}kLoad 

Call load on the servable.

[]{#a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1}kUnload 

Call unload on the servable.

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a71bde7aea4c6116cede2714758688857}

[[◆ ](#a71bde7aea4c6116cede2714758688857)]{.permalink}GetHighestAspiredNewServableId() {#gethighestaspirednewservableid .memtitle}
--------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -----------------------         | [[static]{.mlabe                  |
| --------------------------------- | l}[protected]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------ --- ---------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------- ----------------- --- -- |                                   |
|   absl::optional\< [Ser           |                                   |
| vableId](structtensorflow_1_1serv |                                   |
| ing_1_1ServableId.html){.el} \> t |                                   |
| ensorflow::serving::AspiredVersio |                                   |
| nPolicy::GetHighestAspiredNewServ |                                   |
| ableId   (   const std::vector\<  |                                   |
| [AspiredServableStateSnapshot](st |                                   |
| ructtensorflow_1_1serving_1_1Aspi |                                   |
| redServableStateSnapshot.html){.e |                                   |
| l} \> &    *all\_versions*   )    |                                   |
|   -----------------------         |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------ --- ---------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------- ----------------- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns the aspired
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} with
the highest version that matches kNew state, if any exists.
:::
:::

[]{#a86135f0f3225cd2999033da63e013214}

[[◆ ](#a86135f0f3225cd2999033da63e013214)]{.permalink}GetNextAction() {#getnextaction .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ----------------                | [[pure                            |
| --------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| - --- --------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --- ----------------- --- ------- |                                   |
|   virtual absl::                  |                                   |
| optional\<[ServableAction](struct |                                   |
| tensorflow_1_1serving_1_1AspiredV |                                   |
| ersionPolicy_1_1ServableAction.ht |                                   |
| ml){.el}\> tensorflow::serving::A |                                   |
| spiredVersionPolicy::GetNextActio |                                   |
| n   (   const std::vector\< [Aspi |                                   |
| redServableStateSnapshot](structt |                                   |
| ensorflow_1_1serving_1_1AspiredSe |                                   |
| rvableStateSnapshot.html){.el} \> |                                   |
|  &    *all\_versions*   )   const |                                   |
|   ----------------                |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| - --- --------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --- ----------------- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Takes in a vector of state snapshots of all versions of a servable
stream and returns an action to be performed for a particular servable
version, depending only on the states of all the versions.

If no action is to be performed, we don\'t return an action, meaning
that the servable stream is up to date.

Implemented in
[tensorflow::serving::ResourcePreservingPolicy](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html#ab1fa4fa3d4a8dc165bb86f5377436532){.el},
and
[tensorflow::serving::AvailabilityPreservingPolicy](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html#a3e7f155e7dd0bb9fadacfdfe4cad5d4c){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[aspired\_version\_policy.h](aspired__version__policy_8h_source.html){.el}
-   tensorflow\_serving/core/aspired\_version\_policy.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
