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
-   [SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::SimpleLoader\< ServableType \> Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}, including all
inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------------------------------------------------------------------------------------------------- -------------------------------------
  **Creator** typedef (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                                               [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **CreatorVariant** typedef (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                                        [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **CreatorWithMetadata** typedef (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                                   [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **EstimateNoResources**() (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                                         [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [static]{.mlabel}
  [EstimateResources](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.el}(ResourceAllocation \*estimate) const override                                                                                                                                  [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [virtual]{.mlabel}
  [Load](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}() override                                                                                                                                                                                  [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [virtual]{.mlabel}
  [LoadWithMetadata](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.el}(const Metadata &metadata) override                                                                                                                                              [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [virtual]{.mlabel}
  **ResourceEstimator** typedef (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                                     [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  [servable](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.el}() override                                                                                                                                                                              [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **SimpleLoader**(Creator creator, ResourceEstimator resource\_estimator) (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                          [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **SimpleLoader**(CreatorWithMetadata creator\_with\_metadata, ResourceEstimator resource\_estimator) (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                              [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **SimpleLoader**(Creator creator, ResourceEstimator resource\_estimator, ResourceEstimator post\_load\_resource\_estimator) (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                       [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **SimpleLoader**(CreatorWithMetadata creator\_with\_metadata, ResourceEstimator resource\_estimator, ResourceEstimator post\_load\_resource\_estimator) (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})           [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  **SimpleLoader**(CreatorVariant creator\_variant, ResourceEstimator resource\_estimator, absl::optional\< ResourceEstimator \> post\_load\_resource\_estimator) (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})   [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  [Unload](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el}() override                                                                                                                                                                                [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   [virtual]{.mlabel}
  [\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}()=default                                                                                                                                                                                     [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                 [virtual]{.mlabel}
  **\~SimpleLoader**() override=default (defined in [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el})                                                                                                                             [tensorflow::serving::SimpleLoader\< ServableType \>](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}   
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
