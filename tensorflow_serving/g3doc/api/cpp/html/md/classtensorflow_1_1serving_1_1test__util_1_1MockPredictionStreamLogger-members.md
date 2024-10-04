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
-   [MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockPredictionStreamLogger Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------
  **AddLogCallback**(const LogMetadata &log\_metadata, LogMessageFn log\_message\_fn) (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                      [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    
  **LogMessage**() (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                                                         [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    
  **LogMessageFn** typedef (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                                                 [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    
  **LogStreamRequest**(PredictRequest request)=0 (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                           [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    [pure virtual]{.mlabel}
  **LogStreamResponse**(PredictResponse response)=0 (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                        [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    [pure virtual]{.mlabel}
  **MOCK\_METHOD**(void, LogStreamRequest,(PredictRequest),(override)) (defined in [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el})                                                                    [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el}   
  **MOCK\_METHOD**(void, LogStreamResponse,(PredictResponse),(override)) (defined in [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el})                                                                  [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el}   
  **MOCK\_METHOD**(absl::Status, CreateLogMessage,(const LogMetadata &, std::unique\_ptr\< google::protobuf::Message \> \*),(override)) (defined in [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el})   [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el}   
  **StreamLogger**() (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                                                       [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    [inline]{.mlabel}
  **\~MockPredictionStreamLogger**() override=default (defined in [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el})                                                                                     [tensorflow::serving::test\_util::MockPredictionStreamLogger](classtensorflow_1_1serving_1_1test__util_1_1MockPredictionStreamLogger.html){.el}   
  **\~StreamLogger**()=default (defined in [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el})                                                                                                                             [tensorflow::serving::StreamLogger\< PredictRequest, PredictResponse \>](classtensorflow_1_1serving_1_1StreamLogger.html){.el}                    [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
