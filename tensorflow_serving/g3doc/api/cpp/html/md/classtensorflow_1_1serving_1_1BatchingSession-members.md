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
-   [BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::BatchingSession Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------- -------------------
  **Close**() final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                   [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}     
  **Create**(const BatchingSessionOptions &options, std::unique\_ptr\< Session \> wrapped, const std::vector\< SignatureWithBatchingSessionSchedulerCreator \> &signatures\_with\_scheduler\_creators, const std::string &thread\_pool\_name, std::unique\_ptr\< BatchingSession \> \*result) (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})                                                       [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   [static]{.mlabel}
  **Create**(const BatchingSessionOptions &options, std::unique\_ptr\< Session \> wrapped, const std::vector\< SignatureWithBatchingSessionSchedulerCreator \> &signatures\_with\_scheduler\_creators, BatchingSessionSchedulerCreator default\_creator, const std::string &thread\_pool\_name, std::unique\_ptr\< BatchingSession \> \*result) (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})     [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   [static]{.mlabel}
  **Create**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                             [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}     
  **Extend**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                             [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}     
  **ListDevices**(std::vector\< DeviceAttributes \> \*response) override (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})                                                                                                                                                                                                                                                                            [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   
  **Run**(const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs) override (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})                                                                                                                        [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata) override (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})                                                           [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata, const thread::ThreadPoolOptions &thread\_pool\_options) override (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})   [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   
  **ServingSession**()=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                        [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}     
  **\~BatchingSession**() override=default (defined in [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el})                                                                                                                                                                                                                                                                                                          [tensorflow::serving::BatchingSession](classtensorflow_1_1serving_1_1BatchingSession.html){.el}   
  **\~ServingSession**() override=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                             [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}     
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
