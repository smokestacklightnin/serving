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
-   [EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::EmptyServable Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el},
including all inherited members.

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------- -------------------------------------
  **Classify**(const RunOptions &run\_options, const ClassificationRequest &request, ClassificationResponse \*response) override (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})             [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **EmptyServable**() (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})                                                                                                                        [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   
  **GetModelMetadata**(const GetModelMetadataRequest &request, GetModelMetadataResponse \*response) override (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})                                 [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **IsCritical**() const (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                               [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [inline]{.mlabel}
  **MultiInference**(const RunOptions &run\_options, const MultiInferenceRequest &request, MultiInferenceResponse \*response) override (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})       [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **name**() const (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                                     [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [inline]{.mlabel}
  **Predict**(const RunOptions &run\_options, const PredictRequest &request, PredictResponse \*response) override (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})                            [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **PredictStreamed**(const RunOptions &run\_options, absl::AnyInvocable\< void(absl::StatusOr\< PredictResponse \>)\> response\_callback) (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})   [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **Regress**(const RunOptions &run\_options, const RegressionRequest &request, RegressionResponse \*response) override (defined in [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el})                      [tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **Resume**() (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                                         [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [virtual]{.mlabel}
  **RunOptions** typedef (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                               [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             
  **Servable**(absl::string\_view name, int64\_t version, bool is\_critical=false) (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                     [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [inline]{.mlabel}
  **SupportsPaging**() const (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                           [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [virtual]{.mlabel}
  **Suspend**() (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                                        [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [virtual]{.mlabel}
  **version**() const (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                                  [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [inline]{.mlabel}
  **\~Servable**()=default (defined in [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el})                                                                                                                             [tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html){.el}             [virtual]{.mlabel}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
