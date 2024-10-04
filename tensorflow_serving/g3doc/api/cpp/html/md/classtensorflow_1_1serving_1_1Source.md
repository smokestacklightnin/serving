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
-   [Source](classtensorflow_1_1serving_1_1Source.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Types](#pub-types) \| [Public Member Functions](#pub-methods) \|
[List of all members](classtensorflow_1_1serving_1_1Source-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::Source\< T \> Class Template
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <source.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::Source\< T \>:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1Source__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------
:::

using 

[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
= std::function\< void(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\< T
\> \> versions)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#a70d7f3b3ab429deb777d4672c0cec447} virtual void 

[SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}
([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
callback)=0

 

Supplies an AspiredVersionsCallback to use. Can be called at most once.\

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
### template\<typename T\> class tensorflow::serving::Source\< T \>

An abstraction for a module that sources servables to load, or, more
precisely, handles to data that can be used to load those servables.
Examples of such data handles are:

-   a file-system path to a serialized vocabulary map
-   a handle to an incoming RPC that specifies a machine-learned model
    to load
-   a [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} (see
    [loader.h](loader_8h_source.html){.el}) The data handles are
    generally assumed to be small.

A [Source](classtensorflow_1_1serving_1_1Source.html){.el} monitors some
external resource (e.g. file system, RPC calls) to find out about new
servables and/or new versions of servables and/or the need to unload
servable versions. It uses the provided callback to instruct a
[Target](classtensorflow_1_1serving_1_1Target.html){.el} module (e.g.
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})
which version(s) of a given servable to load. Furthermore, depending on
the semantics of the
[Target](classtensorflow_1_1serving_1_1Target.html){.el} module, the
[Source](classtensorflow_1_1serving_1_1Source.html){.el} implicitly
instructs it which ones to unload by omitting those servables.

A common case is that a
[Source](classtensorflow_1_1serving_1_1Source.html){.el} emits versions
for exactly one servable. An even simpler case is that a servable has a
single, static version for the lifetime of the server.

Sources can house state that is shared among multiple emitted servables,
e.g.

1.  A shared thread pool or other resource that multiple servables use.
2.  A shared read-only data structure that multiple servables use, to
    avoid the time and space overhead of replicating the data structure
    in each servable instance. Shared state whose initialization time
    and size is negligible (e.g. thread pools) can be created eagerly by
    the source, which then embeds a pointer to it in each emitted
    [ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}
    item. Creation of expensive or large shared state should be deferred
    to the first applicable
    [Loader::Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
    call, i.e. governed by the manager. Symmetrically, the
    [Loader::Unload()](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}
    call to the final servable using the expensive/large shared state
    should tear it down.
:::

Member Typedef Documentation {#member-typedef-documentation .groupheader}
----------------------------

[]{#aeb281087e1478b0ff4a74e3f60496c6f}

[[◆ ](#aeb281087e1478b0ff4a74e3f60496c6f)]{.permalink}AspiredVersionsCallback {#aspiredversionscallback .memtitle}
-----------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  using [tensorflow::serving::Source](classtensorflow_1_1serving_1_1Source.html){.el}\< T \>::[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el} = std::function\<void( const StringPiece servable\_name, std::vector\<[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<T\> \> versions)\>
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
A callback for a
[Source](classtensorflow_1_1serving_1_1Source.html){.el} to supply
version(s) of a servable to a
[Target](classtensorflow_1_1serving_1_1Target.html){.el}, to be loaded.

A single invocation of the callback pertains to a single servable stream
(given by \'servable\_name\'). All versions supplied in a call must be
for the servable identified in \'servable\_name\'. Invocations on
different servable streams are orthogonal to one another.

Multiple invocations may supply servable-data objects with identical ids
(i.e. same servable name and version). Such servable-data objects are
treated as semantically equivalent. The recipient will ultimately retain
one and discard the rest.

If a servable version V is supplied in a first invocation, and
subsequently omitted from a second invocation, the implication of
omitting V depends on the semantics of the
[Target](classtensorflow_1_1serving_1_1Target.html){.el} of the
callback. Certain Targets will interpret V\'s omission as an implicit
instruction to unload V. Each
[Target](classtensorflow_1_1serving_1_1Target.html){.el} must document
its semantics in this regard.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[source.h](source_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
