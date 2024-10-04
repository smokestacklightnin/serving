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
-   [TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Types](#pub-types) \| [Public Member Functions](#pub-methods) \|
[Static Public Member Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1TfrtSavedModelFactory-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::TfrtSavedModelFactory Class Reference
:::
:::
:::

::: {.contents}
`#include <tfrt_saved_model_factory.h>`

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------
:::

[]{#ab74f14db2692406da470b58598de8480} using 

**Batcher** = SharedBatchScheduler\<
[SavedModelBatchingTask](structtensorflow_1_1serving_1_1SavedModelBatchingTask.html){.el}
\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#a0e0170fbaf2589f5a0847023e4d91c1c}  

**TfrtSavedModelFactory** (const TfrtSavedModelConfig &config,
std::shared\_ptr\< Batcher \> batch\_scheduler, std::unique\_ptr\<
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.el}
\> thread\_pool\_factory)

 

[]{#aa148cff5fb3ab4122762ac9cf360b75b}  

**TfrtSavedModelFactory** (const TfrtSavedModelConfig &config,
std::shared\_ptr\< Batcher \> batch\_scheduler, std::unique\_ptr\<
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.el}
\> thread\_pool\_factory, std::function\< std::unique\_ptr\<
[RequestRecorder](classtensorflow_1_1serving_1_1RequestRecorder.html){.el}
\>([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.el}
&)\> recorder\_creator)

 

virtual absl::Status 

[CreateTfrtSavedModelWithMetadata](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386){.el}
(const
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata, const string &path, std::unique\_ptr\<
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} \>
\*servable)

 

[]{#a580da5425b4fac83100cdb6f3065e6a2} absl::Status 

**CreateTfrtSavedModelWithMetadata** (const
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata, const string &path, std::unique\_ptr\< tfrt\_stub::SavedModel
\> \*saved\_model)

 

absl::Status 

[EstimateResourceRequirement](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#aa1451f446252c259f225722b9cd07aaf){.el}
(const string &path, ResourceAllocation \*estimate) const

 

[]{#a997159ccadc111184b10717926e502f4} const TfrtSavedModelConfig & 

**config** () const

 

[]{#a29020fcd753a5d2d630f753d447c6ebc} TfrtSavedModelConfig & 

**mutable\_config** ()

 

[]{#acdff7e86f61c57cd4bae187295a40d39} absl::string\_view 

**GetServingResourceType** () const

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

static absl::Status 

[Create](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#ad168a4902febebaa51745428a5da5f17){.el}
(const TfrtSavedModelConfig &config, std::unique\_ptr\<
[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}
\> \*factory)

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A factory that creates tfrt\_stub::SavedModel from SavedModel export
paths.

The factory can also estimate the resource (e.g. RAM) requirements of a
tfrt\_stub::SavedModel based on the SavedModel (i.e. prior to loading
the session).

This class is thread-safe.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ad168a4902febebaa51745428a5da5f17}

[[◆ ](#ad168a4902febebaa51745428a5da5f17)]{.permalink}Create() {#create .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[static]{.mlabel}]{.mlabels}     |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
|  --- ---------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
|   absl::Status tensorflow::serv   |                                   |
| ing::TfrtSavedModelFactory::Creat |                                   |
| e   (   const TfrtSavedModelConfi |                                   |
| g &                               |                                   |
|                                   |                                   |
|                         *config*, |                                   |
|                                   |                                   |
|                                   |                                   |
|        std::unique\_ptr\< [TfrtSa |                                   |
| vedModelFactory](classtensorflow_ |                                   |
| 1_1serving_1_1TfrtSavedModelFacto |                                   |
| ry.html){.el} \> \*    *factory*  |                                   |
|                                   |                                   |
|                                   |                                   |
|              )                    |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
|  --- ---------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------------- ------------ |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Instantiates a
[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}
using a config.

Parameters

:   --------- -----------------------------------------------------
      config    Config with initialization options.
      factory   Newly created factory if the returned Status is OK.
      --------- -----------------------------------------------------
:::
:::

[]{#affd90c58362c83fb9949bc9892201386}

[[◆ ](#affd90c58362c83fb9949bc9892201386)]{.permalink}CreateTfrtSavedModelWithMetadata() {#createtfrtsavedmodelwithmetadata .memtitle}
----------------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ----------                      | [[virtual]{.mlabel}]{.mlabels}    |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----------------------- --- ----- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- ------------- |                                   |
|   virtual                         |                                   |
| absl::Status tensorflow::serving: |                                   |
| :TfrtSavedModelFactory::CreateTfr |                                   |
| tSavedModelWithMetadata   (   con |                                   |
| st [Loader::Metadata](structtenso |                                   |
| rflow_1_1serving_1_1Loader_1_1Met |                                   |
| adata.html){.el} &    *metadata*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|  const string &                   |                                   |
|                                   |                                   |
|                           *path*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                               std |                                   |
| ::unique\_ptr\< [Servable](classt |                                   |
| ensorflow_1_1serving_1_1Servable. |                                   |
| html){.el} \> \*      *servable*  |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|     )                             |                                   |
|                                   |                                   |
|                                   |                                   |
|   ----------                      |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----------------------- --- ----- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- ------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Instantiates a tfrt\_stub::SavedModel from a given export or SavedModel
path and the given metadata.

Parameters

:   ---------- ----------------------------------------------------------------------------------------------------------
      metadata   Metadata to be associated with the saved\_model.
      path       Path to the model.
      servable   Newly created [Servable](classtensorflow_1_1serving_1_1Servable.html){.el} if the returned Status is OK.
      ---------- ----------------------------------------------------------------------------------------------------------
:::
:::

[]{#aa1451f446252c259f225722b9cd07aaf}

[[◆ ](#aa1451f446252c259f225722b9cd07aaf)]{.permalink}EstimateResourceRequirement() {#estimateresourcerequirement .memtitle}
-----------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  -------------------------------------------------------------------------------------- --- ------------------------ -------------
  absl::Status tensorflow::serving::TfrtSavedModelFactory::EstimateResourceRequirement   (   const string &           *path*,
                                                                                             ResourceAllocation \*    *estimate* 
                                                                                         )                            const
  -------------------------------------------------------------------------------------- --- ------------------------ -------------
:::

::: {.memdoc}
Estimates the resources a SavedModel will use once loaded, from its
export path.

Parameters

:   ---------- --------------------------------------------------------------------------------------------------------
      path       Path to the model.
      estimate   Output resource usage estimates. Different kinds of resources (e.g. CPU, RAM, etc.) may get populated.
      ---------- --------------------------------------------------------------------------------------------------------
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/servables/tensorflow/[tfrt\_saved\_model\_factory.h](tfrt__saved__model__factory_8h_source.html){.el}
-   tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
