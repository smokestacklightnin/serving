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
-   [TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::TfLiteBatchTask Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------- ------------------------------------
  **CreatePartialTfLiteBatchTask**(std::vector\< int \> input\_indices, const std::vector\< string \> \*output\_tensor\_names, std::vector\< Tensor \> \*outputs, std::function\< void()\> done\_callback, ThreadSafeStatus \*partial\_status, std::unique\_ptr\< TfLiteBatchTask \> \*batch\_task) (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})   [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}[static]{.mlabel}
  **CreateTfLiteBatchTask**(const std::vector\< string \> \*output\_tensor\_names, std::vector\< Tensor \> \*outputs, Notification \*done, Status \*status, std::unique\_ptr\< TfLiteBatchTask \> \*batch\_task) (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                      [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}[static]{.mlabel}
  **done** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                            [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **done\_callback** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                  [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **enqueue\_time\_micros** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                           [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **input\_indices** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                  [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **inputs** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                          [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **is\_partial** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                     [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **operator=**(const TfLiteBatchTask &)=delete (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                       [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **output\_tensor\_names** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                           [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **outputs** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                         [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **partial\_status** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                 [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **run\_options** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                    [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **set\_output**(Tensor t) (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                           [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}
  **size**() const override (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                           [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}
  **start\_time\_micros**() const (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                     [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}
  **status** (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                                          [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **TfLiteBatchTask**() (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                                               [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   [inline]{.mlabel}
  **TfLiteBatchTask**(const TfLiteBatchTask &)=delete (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                 [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  **\~TfLiteBatchTask**() override=default (defined in [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el})                                                                                                                                                                                                                                                            [tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}   
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------- ------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
