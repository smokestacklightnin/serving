::: {#classtensorflow_1_1serving_1_1AspiredVersionsManager}
:::

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager
label="classtensorflow_1_1serving_1_1AspiredVersionsManager"}

\#include $<$aspired\_versions\_manager.h$>$

Inheritance diagram for tensorflow::serving::AspiredVersionsManager:

![image](classtensorflow_1_1serving_1_1AspiredVersionsManager__inherit__graph.pdf){width="350pt"}

Collaboration diagram for tensorflow::serving::AspiredVersionsManager:

![image](classtensorflow_1_1serving_1_1AspiredVersionsManager__coll__graph.pdf){width="350pt"}

struct
[Options](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_a005f473f7335996a1c58beb773dd4cbb\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_a005f473f7335996a1c58beb773dd4cbb
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_a005f473f7335996a1c58beb773dd4cbb"}
using **PreLoadHook** = BasicManager::PreLoadHook

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_aad4848a5ef2d47bfbe5bfd0075ce906a\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_aad4848a5ef2d47bfbe5bfd0075ce906a
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_aad4848a5ef2d47bfbe5bfd0075ce906a"}
using **CustomSortActionsFn** = std::function$<$ bool(const
[AspiredVersionPolicy::ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
&, const
[AspiredVersionPolicy::ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
&)$>$

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1AspiredVersionsManager_a058a76ee71c52d4a6319f14cd9b2ad69)
() const override

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_a4fcdded2573a67abe77f238857e57f35\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_a4fcdded2573a67abe77f238857e57f35
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_a4fcdded2573a67abe77f238857e57f35"}
[Source](#classtensorflow_1_1serving_1_1Source)$<$ std::unique\_ptr$<$
[Loader](#classtensorflow_1_1serving_1_1Loader) $>$
$>$::AspiredVersionsCallback
[GetAspiredVersionsCallback](#classtensorflow_1_1serving_1_1AspiredVersionsManager_a4fcdded2573a67abe77f238857e57f35)
() override

*Returns a callback to set the list of aspired versions for a particular
servable stream, using Loaders.*

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_a77527bce2c78cc09f55ec7bce2f3a28a\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_a77527bce2c78cc09f55ec7bce2f3a28a
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_a77527bce2c78cc09f55ec7bce2f3a28a"}
static Status **Create**
([Options](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options)
options, std::unique\_ptr$<$
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
$>$ $\ast$manager)

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_a331176a8d12da02dcfc7a4b475d8d845\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_a331176a8d12da02dcfc7a4b475d8d845
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_a331176a8d12da02dcfc7a4b475d8d845"}
class **internal::AspiredVersionsManagerTargetImpl**

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_acc49d7142d1c0d62cd06180eb4a9d492\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_acc49d7142d1c0d62cd06180eb4a9d492
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_acc49d7142d1c0d62cd06180eb4a9d492"}
class **test\_util::AspiredVersionsManagerTestAccess**

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_aef1c2aea9a94c4a1b0b2d735f8585246\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_aef1c2aea9a94c4a1b0b2d735f8585246
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_aef1c2aea9a94c4a1b0b2d735f8585246"}
class **ServerCore**

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_acfcc9f5a29a54b98d9ff40d5af34ee0a\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_acfcc9f5a29a54b98d9ff40d5af34ee0a
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_acfcc9f5a29a54b98d9ff40d5af34ee0a"}
uint32 **internal::GetManagerNumLoadThreads**
([AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
$\ast$manager)

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_aa91cf33196ca873f547c8f1a894722f6\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_aa91cf33196ca873f547c8f1a894722f6
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_aa91cf33196ca873f547c8f1a894722f6"}
std::function$<$ void(uint32)$>$
**internal::SetManagerNumLoadThreadsNotifier**
([AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
$\ast$manager)

A manager that implements the
[Target](#classtensorflow_1_1serving_1_1Target)&lt;[Loader](#classtensorflow_1_1serving_1_1Loader)$>$
API which uses aspired-versions callbacks to dictate which servable
versions to load. This manager also uses that API to infer which ones to
unload: If a given servable version is currently loaded, and is omitted
from an aspired-versions callback invocation pertaining to its servable
stream, this manager interprets that omission as an implicit instruction
to unload the version. See below for details.

(The implicit-unload semantics facilitates stateless
[Source](#classtensorflow_1_1serving_1_1Source) implementations, whereby
a given iteration of the
[Source](#classtensorflow_1_1serving_1_1Source)s logic simply decides
which versions of a servable ought to be loaded, without needing to know
what it has decided in the past.)

This manager makes transitions between versions of a servable stream
using a configured
[AspiredVersionPolicy](#classtensorflow_1_1serving_1_1AspiredVersionPolicy).
The manager prefers unloading before loading to free up resources in the
server when deciding among transitions suggested by the policy.

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManager\_a058a76ee71c52d4a6319f14cd9b2ad69\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManager_a058a76ee71c52d4a6319f14cd9b2ad69
label="classtensorflow_1_1serving_1_1AspiredVersionsManager_a058a76ee71c52d4a6319f14cd9b2ad69"}

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
tensorflow::serving::AspiredVersionsManager::ListAvailableServableIds (

) const,

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/aspired\_versions\_manager.h

tensorflow\_serving/core/aspired\_versions\_manager.cc
