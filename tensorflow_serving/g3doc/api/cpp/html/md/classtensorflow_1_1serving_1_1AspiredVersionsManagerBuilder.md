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
-   [AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Types](#pub-types) \| [Public Member Functions](#pub-methods) \|
[Static Public Member Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::AspiredVersionsManagerBuilder Class Reference
:::
:::
:::

::: {.contents}
`#include <aspired_versions_manager_builder.h>`

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------
:::

[]{#af921abbdbda20510e5aed5a0d28d9edb} using 

**Options** =
[AspiredVersionsManager::Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.el}

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

template\<typename S \>

void 

[AddSource](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed){.el}
(std::unique\_ptr\< S \> source)

 

template\<typename S , typename SA , typename\... Args\>

void 

[AddSourceChain](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a4b8c4eda9ac206ecc69b7464b6e42a44){.el}
(std::unique\_ptr\< S \> source, std::unique\_ptr\< SA \>
first\_source\_adapter, std::unique\_ptr\< Args \>\...
remaining\_source\_adapters)

 

[]{#a9a95dc4a19029c2bc28fdc6caa274656} std::unique\_ptr\<
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} \> 

[Build](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a9a95dc4a19029c2bc28fdc6caa274656){.el}
()

 

Builds the
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
and returns it as the
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} interface.\

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a2a6aa53dab22f2d35af4a9022b84c5ea} static Status 

**Create**
([Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.el}
options, std::unique\_ptr\<
[AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.el}
\> \*builder)

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
Builds an
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
with options and sources connected to it. It takes over the ownership of
the sources and the returned manager handles the destruction of itself
and its dependencies. Both single sources and source/source-adapter
chains are accepted, i.e. you can use sources that directly supply
loaders
([Source](classtensorflow_1_1serving_1_1Source.html){.el}&lt;std::unique\_ptr&lt;[Loader](classtensorflow_1_1serving_1_1Loader.html){.el}\>\>)
or composites that consist of
[Source](classtensorflow_1_1serving_1_1Source.html){.el}&lt;S\> + some
chain of
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}&lt;S,
\...\>, \...,
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}&lt;\...,
std::unique\_ptr&lt;[Loader](classtensorflow_1_1serving_1_1Loader.html){.el}\>\>.
The builder connects the chain for you.

Usage:

``` {.fragment}
...
AspiredVersionsManagerBuilder::Options options = ManagerOptions();
std::unique_ptr&lt;AspiredVersionsManagerBuilder> builder;
TF_CHECK_OK(AspiredVersionsManagerBuilder::Create(
    std::move(options), &builder));
builder->AddSource(std::move(some_source));
builder->AddSourceChain(
    std::move(source), std::move(source_adapter1),
    std::move(source_adapter2));
std::unique_ptr&lt;Manager> manager = builder->Build();
...
```

NOTE: A builder can only be used to build a single
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}.

This class is not thread-safe.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#abd6f745193c54f7887119ed886dda0ed}

[[◆ ](#abd6f745193c54f7887119ed886dda0ed)]{.permalink}AddSource() {#addsource .memtitle}
-----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename S \>
:::

  -------------------------------------------------------------------- --- -------------------------- ---------- --- --
  void tensorflow::serving::AspiredVersionsManagerBuilder::AddSource   (   std::unique\_ptr\< S \>    *source*   )   
  -------------------------------------------------------------------- --- -------------------------- ---------- --- --
:::

::: {.memdoc}
Connects the source to the
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
being built and takes over its ownership.

REQUIRES: Template type S be convertible to
[Source](classtensorflow_1_1serving_1_1Source.html){.el}&lt;std::unique\_ptr&lt;[Loader](classtensorflow_1_1serving_1_1Loader.html){.el}\>\>.
:::
:::

[]{#a4b8c4eda9ac206ecc69b7464b6e42a44}

[[◆ ](#a4b8c4eda9ac206ecc69b7464b6e42a44)]{.permalink}AddSourceChain() {#addsourcechain .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename S , typename SA , typename\... Args\>
:::

  ------------------------------------------------------------------------- --- --------------------------------- --------------------------------
  void tensorflow::serving::AspiredVersionsManagerBuilder::AddSourceChain   (   std::unique\_ptr\< S \>           *source*,
                                                                                std::unique\_ptr\< SA \>          *first\_source\_adapter*,
                                                                                std::unique\_ptr\< Args \>\...    *remaining\_source\_adapters* 
                                                                            )                                     
  ------------------------------------------------------------------------- --- --------------------------------- --------------------------------
:::

::: {.memdoc}
Connects a chain comprising a source and a chain of source adapters,
s.t. the final adapter in the chain emits Loaders for the manager. The
final adapter is connected to the manager. We take ownership of the
whole chain.

REQUIRES: At least one source adapter.

Usage: builder-\>AddSourceChain( std::move(source),
std::move(source\_adapter1), std::move(source\_adapter2));
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[aspired\_versions\_manager\_builder.h](aspired__versions__manager__builder_8h_source.html){.el}
-   tensorflow\_serving/core/aspired\_versions\_manager\_builder.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
