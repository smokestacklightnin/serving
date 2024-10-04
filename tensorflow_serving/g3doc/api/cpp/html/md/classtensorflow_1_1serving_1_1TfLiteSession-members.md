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
-   [TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::TfLiteSession Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------- -------------------
  **Close**() final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                               [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}   
  **Create**(string &&buffer, const SessionOptions &options, int num\_pools, int num\_interpreters\_per\_pool, std::unique\_ptr\< TfLiteSession \> \*tflite\_session, ::google::protobuf::Map\< string, SignatureDef \> \*signatures) (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                               [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     [static]{.mlabel}
  **Create**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}   
  **CreateDefaultBasicBatchScheduler**(const BasicBatchScheduler\< TfLiteBatchTask \>::Options &options, std::function\< void(std::unique\_ptr\< Batch\< TfLiteBatchTask \>\>)\> process\_batch\_callback, std::unique\_ptr\< BasicBatchScheduler\< TfLiteBatchTask \>\> \*batch\_scheduler) (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                        [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     [static]{.mlabel}
  **Extend**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}   
  **GetSchedulerOptions**() (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                                                                                                                                                                                                                         [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     [inline]{.mlabel}
  **ListDevices**(std::vector\< DeviceAttributes \> \*response) override (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                                                                                                                                                                            [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  **Run**(const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs) override (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                        [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata) override (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                           [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata, const thread::ThreadPoolOptions &thread\_pool\_options) override (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})   [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  **ServingSession**()=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                    [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}   
  **SetScheduler**(const SchedulerCreator &scheduler\_creator, const BasicBatchScheduler\< TfLiteBatchTask \>::Options &options) (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                                                                                                                    [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  **SplitTfLiteInputTask**(std::unique\_ptr\< TfLiteBatchTask \> \*input\_task\_ptr, int open\_batch\_remaining\_slot, int max\_batch\_size, std::vector\< std::unique\_ptr\< TfLiteBatchTask \>\> \*output\_tasks) (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                                 [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     [static]{.mlabel}
  **\~ServingSession**() override=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}   
  **\~TfLiteSession**() override=default (defined in [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el})                                                                                                                                                                                                                                                                                                            [tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}     
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
