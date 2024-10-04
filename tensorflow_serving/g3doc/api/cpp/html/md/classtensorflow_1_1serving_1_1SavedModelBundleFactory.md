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
-   [SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1SavedModelBundleFactory-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::SavedModelBundleFactory Class Reference
:::
:::
:::

::: {.contents}
`#include <saved_model_bundle_factory.h>`

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

Status 

[CreateSavedModelBundle](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#aa27eec255c83cd1d2f249a2e4a2d0526){.el}
(const string &path, std::unique\_ptr\< SavedModelBundle \> \*bundle)

 

Status 

[CreateSavedModelBundleWithMetadata](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a88da623c02425fe3d01a21e13b956d49){.el}
(const
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata, const string &path, std::unique\_ptr\< SavedModelBundle \>
\*bundle)

 

Status 

[EstimateResourceRequirement](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a4b897842868d8f090ebe972974e03bf7){.el}
(const string &path, ResourceAllocation \*estimate) const

 

[]{#a36f97e1012459789c56ba07eef4b834c} const SessionBundleConfig & 

**config** () const

 

[]{#a1b7a4e8f7f3bf2ce30570d8b1391de78} SessionBundleConfig & 

**mutable\_config** ()

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

static Status 

[Create](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a234678b40af9995c21a72d265540fdb9){.el}
(const SessionBundleConfig &config, std::unique\_ptr\<
[SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.el}
\> \*factory)

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A factory that creates SavedModelBundles from SavedModel or
[SessionBundle](structtensorflow_1_1serving_1_1SessionBundle.html){.el}
export paths.

The emitted sessions only support Run(), and although not enforced it is
expected that the client will only make non-mutating Run() calls. (If
this restriction, which we\'ve added as a safety measure, is problematic
for your use-case please contact the TensorFlow Serving team to discuss
disabling it.)

If the config calls for batching, the emitted sessions automatically
batch Run() calls behind the scenes, using a SharedBatchScheduler owned
by the factory. The \'config.num\_batch\_threads\' threads are shared
across all session instances created by this factory. However, each
session has its own dedicated queue of size
\'config.max\_enqueued\_batches\'.

The factory can also estimate the resource (e.g. RAM) requirements of a
SavedModelBundle based on the SavedModel (i.e. prior to loading the
session).

This class is thread-safe.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a234678b40af9995c21a72d265540fdb9}

[[◆ ](#a234678b40af9995c21a72d265540fdb9)]{.permalink}Create() {#create .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[static]{.mlabel}]{.mlabels}     |
|  -------------------------------- |                                   |
| ----------------------------- --- |                                   |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
|   Status tensorflow::serving::S   |                                   |
| avedModelBundleFactory::Create    |                                   |
| (   const SessionBundleConfig &   |                                   |
|                                   |                                   |
|                                   |                                   |
|                         *config*, |                                   |
|                                   |                                   |
|                                   |                                   |
|    std::unique\_ptr\< [SavedModel |                                   |
| BundleFactory](classtensorflow_1_ |                                   |
| 1serving_1_1SavedModelBundleFacto |                                   |
| ry.html){.el} \> \*    *factory*  |                                   |
|                                   |                                   |
|                                   |                                   |
|          )                        |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|  -------------------------------- |                                   |
| ----------------------------- --- |                                   |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Instantiates a
[SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.el}
using a config.

Parameters

:   --------- -----------------------------------------------------
      config    Config with initialization options.
      factory   Newly created factory if the returned Status is OK.
      --------- -----------------------------------------------------
:::
:::

[]{#aa27eec255c83cd1d2f249a2e4a2d0526}

[[◆ ](#aa27eec255c83cd1d2f249a2e4a2d0526)]{.permalink}CreateSavedModelBundle() {#createsavedmodelbundle .memtitle}
------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------------- --- -------------------------------------------- -----------
  Status tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundle   (   const string &                               *path*,
                                                                                    std::unique\_ptr\< SavedModelBundle \> \*    *bundle* 
                                                                                )                                                
  ----------------------------------------------------------------------------- --- -------------------------------------------- -----------
:::

::: {.memdoc}
Instantiates a bundle from a given export or SavedModel path.

Parameters

:   -------- --------------------------------------------------------------
      path     Path to the model.
      bundle   Newly created SavedModelBundle if the returned Status is OK.
      -------- --------------------------------------------------------------
:::
:::

[]{#a88da623c02425fe3d01a21e13b956d49}

[[◆ ](#a88da623c02425fe3d01a21e13b956d49)]{.permalink}CreateSavedModelBundleWithMetadata() {#createsavedmodelbundlewithmetadata .memtitle}
------------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------------------------------------- --- ------------------------------------------------------------------------------------------ -------------
  Status tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundleWithMetadata   (   const [Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el} &    *metadata*,
                                                                                                const string &                                                                             *path*,
                                                                                                std::unique\_ptr\< SavedModelBundle \> \*                                                  *bundle* 
                                                                                            )                                                                                              
  ----------------------------------------------------------------------------------------- --- ------------------------------------------------------------------------------------------ -------------
:::

::: {.memdoc}
Instantiates a bundle from a given export or SavedModel path and the
given metadata.

Parameters

:   ---------- --------------------------------------------------------------
      metadata   Metadata to be associated with the bundle.
      path       Path to the model.
      bundle     Newly created SavedModelBundle if the returned Status is OK.
      ---------- --------------------------------------------------------------
:::
:::

[]{#a4b897842868d8f090ebe972974e03bf7}

[[◆ ](#a4b897842868d8f090ebe972974e03bf7)]{.permalink}EstimateResourceRequirement() {#estimateresourcerequirement .memtitle}
-----------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------------------------------- --- ------------------------ -------------
  Status tensorflow::serving::SavedModelBundleFactory::EstimateResourceRequirement   (   const string &           *path*,
                                                                                         ResourceAllocation \*    *estimate* 
                                                                                     )                            const
  ---------------------------------------------------------------------------------- --- ------------------------ -------------
:::

::: {.memdoc}
Estimates the resources a SavedModel bundle will use once loaded, from
its export path.

Parameters

:   ---------- --------------------------------------------------------------------------------------------------------
      path       Path to the model.
      estimate   Output resource usage estimates. Different kinds of resources (e.g. CPU, RAM, etc.) may get populated.
      ---------- --------------------------------------------------------------------------------------------------------
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/servables/tensorflow/[saved\_model\_bundle\_factory.h](saved__model__bundle__factory_8h_source.html){.el}
-   tensorflow\_serving/servables/tensorflow/saved\_model\_bundle\_factory.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
