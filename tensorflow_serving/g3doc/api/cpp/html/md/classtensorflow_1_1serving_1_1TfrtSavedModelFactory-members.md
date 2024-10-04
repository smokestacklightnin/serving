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
::: {.headertitle}
::: {.title}
tensorflow::serving::TfrtSavedModelFactory Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------------------------------------------------------------------------------------------------- --------------------
  **Batcher** typedef (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                                                                                                                                                                 [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   
  **config**() const (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                                                                                                                                                                  [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [inline]{.mlabel}
  [Create](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#ad168a4902febebaa51745428a5da5f17){.el}(const TfrtSavedModelConfig &config, std::unique\_ptr\< TfrtSavedModelFactory \> \*factory)                                                                                                                                                                                                         [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [static]{.mlabel}
  [CreateTfrtSavedModelWithMetadata](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386){.el}(const Loader::Metadata &metadata, const string &path, std::unique\_ptr\< Servable \> \*servable)                                                                                                                                                                         [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [virtual]{.mlabel}
  **CreateTfrtSavedModelWithMetadata**(const Loader::Metadata &metadata, const string &path, std::unique\_ptr\< tfrt\_stub::SavedModel \> \*saved\_model) (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                             [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   
  [EstimateResourceRequirement](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#aa1451f446252c259f225722b9cd07aaf){.el}(const string &path, ResourceAllocation \*estimate) const                                                                                                                                                                                                                      [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   
  **GetServingResourceType**() const (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                                                                                                                                                  [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   
  **mutable\_config**() (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                                                                                                                                                               [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [inline]{.mlabel}
  **TfrtSavedModelFactory**(const TfrtSavedModelConfig &config, std::shared\_ptr\< Batcher \> batch\_scheduler, std::unique\_ptr\< ThreadPoolFactory \> thread\_pool\_factory) (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                        [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [inline]{.mlabel}
  **TfrtSavedModelFactory**(const TfrtSavedModelConfig &config, std::shared\_ptr\< Batcher \> batch\_scheduler, std::unique\_ptr\< ThreadPoolFactory \> thread\_pool\_factory, std::function\< std::unique\_ptr\< RequestRecorder \>(TfrtSavedModelServable &)\> recorder\_creator) (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})   [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   
  **\~TfrtSavedModelFactory**() (defined in [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el})                                                                                                                                                                                                                                                       [tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.el}   [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------------------------------------------------------------------------------------------------- --------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
