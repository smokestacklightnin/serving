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
-   [TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1TfrtSavedModelServable-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::TfrtSavedModelServable Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::TfrtSavedModelServable:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1TfrtSavedModelServable__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::TfrtSavedModelServable:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1TfrtSavedModelServable__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#a45a5da4983f5fe6b862697fbce9350b4}  

**TfrtSavedModelServable** (absl::string\_view name, int64\_t version,
const TfrtSavedModelConfig &config, const SavedModelConfig
&model\_config, std::unique\_ptr\< tfrt\_stub::SavedModel \>
saved\_model,
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.el}
\*thread\_pool\_factory)

 

[]{#a1c030cd2189aff8a4efe44d9a028d0c4}  

**TfrtSavedModelServable** (absl::string\_view name, int64\_t version,
const TfrtSavedModelConfig &config, const SavedModelConfig
&model\_config, std::unique\_ptr\< tfrt\_stub::SavedModel \>
saved\_model,
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.el}
\*thread\_pool\_factory, std::function\< std::unique\_ptr\<
[RequestRecorder](classtensorflow_1_1serving_1_1RequestRecorder.html){.el}
\>([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.el}
&)\> recorder\_creator)

 

[]{#a2145a828680d89213120ee5b40ecef7a} absl::Status 

**Classify** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const ClassificationRequest &request,
ClassificationResponse \*response) override

 

[]{#a19543571e73874c4a49383795429a40f} absl::Status 

**Regress** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const RegressionRequest &request, RegressionResponse
\*response) override

 

[]{#a6009af9816f87208564f9e6aa9c20d25} absl::Status 

**Predict** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const PredictRequest &request, PredictResponse
\*response) override

 

[]{#aab502e05af33a4cd61407c524090f8ea} absl::StatusOr\<
std::unique\_ptr\<
[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.el}
\> \> 

**PredictStreamed** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, absl::AnyInvocable\< void(absl::StatusOr\<
PredictResponse \>)\> response\_callback) override

 

[]{#ac0ab6a2ac24d6f51903a9db4fd4a1bc2} absl::Status 

**MultiInference** (const
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}
&run\_options, const MultiInferenceRequest &request,
MultiInferenceResponse \*response) override

 

[]{#a4c444df2d52ea82108599685d07bf715} absl::Status 

**GetModelMetadata** (const GetModelMetadataRequest &request,
GetModelMetadataResponse \*response) override

 

[]{#a264c963eaf59e0509f9fab620fd45c0c} bool 

**SupportsPaging** () const override

 

[]{#a9d654d28c40e514d38bef198edc230dc} absl::Status 

**Suspend** () override

 

[]{#ae5fb11c47ab58187638b1af63753f133} absl::Status 

**Resume** () override

 

[]{#a39d0e1fb10328be68f36f33a2f2fb678} tfrt\_stub::SavedModel & 

**saved\_model** () const

 

[]{#a41c731f83584e3625a5c0a1e97a2ffcd} void 

**set\_resume\_fn** (absl::AnyInvocable\<
absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.el}
\*)\> resume\_fn)

 

[]{#a7f27383faefb9a7dcc1f9122b323513a} void 

**set\_suspend\_fn** (absl::AnyInvocable\<
absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.el}
\*)\> suspend\_fn)

 

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

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}

[]{#aae1542327fc78499507b9a4f2fa75571} using 

**RunOptions** =
[tensorflow::serving::servables::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.el}

 

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/servables/tensorflow/[tfrt\_servable.h](tfrt__servable_8h_source.html){.el}
-   tensorflow\_serving/servables/tensorflow/tfrt\_servable.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
