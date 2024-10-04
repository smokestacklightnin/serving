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
-   [FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1FileSystemStoragePathSource-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::FileSystemStoragePathSource Class Reference
:::
:::
:::

::: {.contents}
`#include <file_system_storage_path_source.h>`

::: {.dynheader}
Inheritance diagram for
tensorflow::serving::FileSystemStoragePathSource:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1FileSystemStoragePathSource__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::FileSystemStoragePathSource:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1FileSystemStoragePathSource__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

Status 

[UpdateConfig](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html#ad29df4b1d9628b03723474db5a0d6ad0){.el}
(const FileSystemStoragePathSourceConfig &config)

 

[]{#a3f341338d7fe9be5176eb788222df5b0} void 

**SetAspiredVersionsCallback**
([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
callback) override

 

[]{#a8ee923530b9479c220996691a06c464a}
FileSystemStoragePathSourceConfig 

**config** () const

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Source\< StoragePath
\>](classtensorflow_1_1serving_1_1Source.html){.el}

[]{#a70d7f3b3ab429deb777d4672c0cec447} virtual void 

[SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}
([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
callback)=0

 

Supplies an AspiredVersionsCallback to use. Can be called at most once.\

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a9f8e64bda0d205fd9bb34bf54f18857c} static Status 

**Create** (const FileSystemStoragePathSourceConfig &config,
std::unique\_ptr\<
[FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}
\> \*result)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a0ddc7d29ad0b369a0f70b22e30083d3a} class 

**internal::FileSystemStoragePathSourceTestAccess**

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::Source\< StoragePath
\>](classtensorflow_1_1serving_1_1Source.html){.el}

using 

[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
= std::function\< void(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
StoragePath \> \> versions)\>

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A storage path source that aspires versions for a given set of
servables. For each servable, it monitors a given file-system base path.
It identifies base-path children whose name is a number (e.g. 123) and
emits the path corresponding to the largest number as the servable\'s
single aspired version. (To do the file-system monitoring, it uses a
background thread that polls the file system periodically.)

For example, if a configured servable\'s base path is /foo/bar, and a
file- system poll reveals child paths /foo/bar/baz, /foo/bar/123 and
/foo/bar/456, the aspired-versions callback is called with {456,
\"/foo/bar/456\"}. If, at any time, the base path is found to contain no
numerical children, the aspired-versions callback is called with an
empty versions list.

The configured set of servables to monitor can be updated at any time by
calling
[UpdateConfig()](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html#ad29df4b1d9628b03723474db5a0d6ad0){.el}.
If any servables were present in the old config but not in the new one,
the source will immediately aspire zero versions for that servable
(causing it to be unloaded in the
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} that
ultimately consumes the aspired-versions calls).
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ad29df4b1d9628b03723474db5a0d6ad0}

[[◆ ](#ad29df4b1d9628b03723474db5a0d6ad0)]{.permalink}UpdateConfig() {#updateconfig .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------- --- -------------------------------------------- ---------- --- --
  Status tensorflow::serving::FileSystemStoragePathSource::UpdateConfig   (   const FileSystemStoragePathSourceConfig &    *config*   )   
  ----------------------------------------------------------------------- --- -------------------------------------------- ---------- --- --
:::

::: {.memdoc}
Supplies a new config to use. The set of servables to monitor can be
changed at any time (see class comment for more information), but it is
illegal to change the file-system polling period once
SetAspiredVersionsCallback() has been called.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/sources/storage\_path/[file\_system\_storage\_path\_source.h](file__system__storage__path__source_8h_source.html){.el}
-   tensorflow\_serving/sources/storage\_path/file\_system\_storage\_path\_source.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
