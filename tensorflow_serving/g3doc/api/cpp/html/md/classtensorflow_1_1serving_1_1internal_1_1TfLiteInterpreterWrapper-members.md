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
-   **internal**
-   [TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::internal::TfLiteInterpreterWrapper Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el},
including all inherited members.

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- -------------------
  **CreateTfLiteInterpreterWrapper**(const tflite::FlatBufferModel &model, const tensorflow::SessionOptions &options, std::unique\_ptr\< TfLiteInterpreterWrapper \> &wrapper) (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})   [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   [static]{.mlabel}
  **Get**() (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                                                                                                                                                      [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   [inline]{.mlabel}
  **GetBatchSize**() (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                                                                                                                                             [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   [inline]{.mlabel}
  **Invoke**() (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                                                                                                                                                   [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   
  **SetBatchSize**(int batch\_size) (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                                                                                                                              [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   [inline]{.mlabel}
  **SetStringData**(const std::vector\< const Tensor \* \> &tensors, TfLiteTensor \*tflite\_tensor, int tensor\_index, int batch\_size) (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                          [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   
  **TfLiteInterpreterWrapper**(std::unique\_ptr\< tflite::ExternalCpuBackendContext \> external\_context, std::unique\_ptr\< tflite::Interpreter \> interpreter) (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                 [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   
  **TfLiteInterpreterWrapper**(std::unique\_ptr\< tflite::Interpreter \> interpreter) (defined in [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el})                                                                                            [tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.el}   [inline]{.mlabel}
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
