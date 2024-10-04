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
-   **test\_util**
-   [MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockSavedModel Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el},
including all inherited members.

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------- -------------------
  **MOCK\_METHOD**(const tensorflow::MetaGraphDef &, GetMetaGraphDef,(),(const, override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                                                                                                                                                                                                                                             [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MOCK\_METHOD**(absl::optional\< tfrt::FunctionMetadata \>, GetFunctionMetadata,(absl::string\_view func\_name),(const, override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                                                                                                                                                                                                  [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Run,(const tfrt::SavedModel::RunOptions &run\_options, absl::string\_view func\_name, absl::Span\< const Tensor \> inputs, std::vector\< Tensor \> \*outputs),(override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                                                                                                                     [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MOCK\_METHOD**(std::vector\< std::string \>, GetFunctionNames,(),(const, override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                                                                                                                                                                                                                                                [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, RunMultipleSignatures,(const tfrt::SavedModel::RunOptions &run\_options, absl::Span\< const std::string \> names, absl::Span\< const std::vector\< tensorflow::Tensor \>\> multi\_inputs, std::vector\< std::vector\< tensorflow::Tensor \>\> \*multi\_outputs),(override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                   [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, RunByTensorNames,(const tfrt::SavedModel::RunOptions &run\_options,(absl::Span\< const std::pair\< std::string, tensorflow::Tensor \>\> inputs), absl::Span\< const std::string \> output\_tensor\_names, absl::Span\< const std::string \> target\_node\_names, std::vector\< tensorflow::Tensor \> \*outputs),(override)) (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})   [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   
  **MockSavedModel**() (defined in [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el})                                                                                                                                                                                                                                                                                                                                                 [tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.el}   [inline]{.mlabel}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
