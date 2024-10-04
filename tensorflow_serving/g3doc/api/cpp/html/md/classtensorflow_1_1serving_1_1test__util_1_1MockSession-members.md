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
-   [MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockSession Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------- -------------------
  **MOCK\_METHOD**(::tensorflow::Status, Create,(const GraphDef &graph),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                                                                                                                                                       [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Extend,(const GraphDef &graph),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                                                                                                                                                       [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Run,((const std::vector\< std::pair\< string, Tensor \>\> &inputs), const std::vector\< string \> &output\_names, const std::vector\< string \> &target\_nodes, std::vector\< Tensor \> \*outputs),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                   [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Run,(const RunOptions &run\_options,(const std::vector\< std::pair\< string, Tensor \>\> &inputs), const std::vector\< string \> &output\_names, const std::vector\< string \> &target\_nodes, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                       [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Run,(const RunOptions &run\_options,(const std::vector\< std::pair\< string, Tensor \>\> &inputs), const std::vector\< string \> &output\_names, const std::vector\< string \> &target\_nodes, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata, const tensorflow::thread::ThreadPoolOptions &thread\_pool\_options),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})   [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, PRunSetup,(const std::vector\< string \> &input\_names, const std::vector\< string \> &output\_names, const std::vector\< string \> &target\_nodes, string \*handle),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                 [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, PRun,(const string &handle,(const std::vector\< std::pair\< string, Tensor \>\> &inputs), const std::vector\< string \> &output\_names, std::vector\< Tensor \> \*outputs),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                           [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, ListDevices,(std::vector\<::tensorflow::DeviceAttributes \> \*response),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                                                                                                              [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MOCK\_METHOD**(::tensorflow::Status, Close,(),(override)) (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                                                                                                                                                                             [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   
  **MockSession**() (defined in [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el})                                                                                                                                                                                                                                                                                                                                                                       [tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.el}   [inline]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
