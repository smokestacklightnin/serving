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
-   [MockServable](classtensorflow_1_1serving_1_1MockServable.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1MockServable-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::MockServable Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::MockServable:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1MockServable__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::MockServable:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1MockServable__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#aa91aacc480ccc6263b74bf78ec199b51}  

**MOCK\_METHOD** (absl::Status, Classify,(const
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const tensorflow::serving::ClassificationRequest
&request, tensorflow::serving::ClassificationResponse
\*response),(final))

 

[]{#a16bbb72efd6149b5ae6e8bda0c2f8567}  

**MOCK\_METHOD** (absl::Status, Regress,(const
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const tensorflow::serving::RegressionRequest &request,
tensorflow::serving::RegressionResponse \*response),(final))

 

[]{#a679c3361f4c95fb547ba8f404819dbbb}  

**MOCK\_METHOD** (absl::Status, Predict,(const
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const tensorflow::serving::PredictRequest &request,
tensorflow::serving::PredictResponse \*response),(final))

 

[]{#a1e24702b948802e177f5c7bc8425d36c}  

**MOCK\_METHOD** (absl::StatusOr\< std::unique\_ptr\<
[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.el}
\>\>, PredictStreamed,(const
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, absl::AnyInvocable\< void(absl::StatusOr\<
tensorflow::serving::PredictResponse \>)\> response\_callback),(final))

 

[]{#aeca0916ebcc135a7bcd29c7b761cdfdc}  

**MOCK\_METHOD** (absl::Status, MultiInference,(const
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const tensorflow::serving::MultiInferenceRequest
&request, tensorflow::serving::MultiInferenceResponse
\*response),(final))

 

[]{#a8c4d6a337dce912c30fbee2ca262958a}  

**MOCK\_METHOD** (absl::Status, GetModelMetadata,(const
tensorflow::serving::GetModelMetadataRequest &request,
tensorflow::serving::GetModelMetadataResponse \*response),(final))

 

[]{#acecedf98762504ff1001c5f7fe7c6da8}  

**MOCK\_METHOD** (bool, SupportsPaging,(),(const, final))

 

[]{#aba68ccb4d8a13a49d9b9147615037fb5}  

**MOCK\_METHOD** (absl::Status, Suspend,(),(final))

 

[]{#a54ff9f365143af108771de33c7d92f20}  

**MOCK\_METHOD** (absl::Status, Resume,(),(final))

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}

[]{#a38b7c413e4c12e95fdc9680b2888b8a0}  

**Servable** (absl::string\_view name, int64\_t version, bool
is\_critical=false)

 

[]{#a393737a4803a6ba744f9eedd132ddb65} absl::string\_view 

**name** () const

 

[]{#a6f4b30e48d3a5ad24899492f88ec4e1a} int64\_t 

**version** () const

 

[]{#a64816027ce86cefe5a07649c40b8f235} bool 

**IsCritical** () const

 

[]{#aa3aaf988243ae1a3ea994609aefc2cf3} virtual absl::Status 

**Classify** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const ClassificationRequest &request,
ClassificationResponse \*response)=0

 

[]{#a9d377f74c29f65fb94f3220350aebf94} virtual absl::Status 

**Regress** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const RegressionRequest &request, RegressionResponse
\*response)=0

 

[]{#a56da3044f582c699b457cbe53f4880ff} virtual absl::Status 

**Predict** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const PredictRequest &request, PredictResponse
\*response)=0

 

[]{#a6d2e1d7315e0016e745a9ddc49ab60df} virtual absl::StatusOr\<
std::unique\_ptr\<
[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.el}
\> \> 

**PredictStreamed** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, absl::AnyInvocable\< void(absl::StatusOr\<
PredictResponse \>)\> response\_callback)=0

 

[]{#a0a40bd468c4b10f28000f806f66ab321} virtual absl::Status 

**MultiInference** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const MultiInferenceRequest &request,
MultiInferenceResponse \*response)=0

 

[]{#a157d7274afc086fa899e8b179c110fcd} virtual absl::Status 

**GetModelMetadata** (const GetModelMetadataRequest &request,
GetModelMetadataResponse \*response)=0

 

[]{#a09a3e5a158832c0d0abf4a837e4e250c} virtual bool 

**SupportsPaging** () const

 

[]{#a0f14477ac47c94af784ef19410b5637d} virtual absl::Status 

**Suspend** ()

 

[]{#a5714db8d9e57bef3af74926977677b78} virtual absl::Status 

**Resume** ()

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}

[]{#aae1542327fc78499507b9a4f2fa75571} using 

**RunOptions** =
[tensorflow::serving::servables::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}

 

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/servables/tensorflow/[mock\_servable.h](mock__servable_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
