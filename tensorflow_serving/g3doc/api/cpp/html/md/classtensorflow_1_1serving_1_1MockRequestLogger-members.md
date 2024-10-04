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
-   [MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::MockRequestLogger Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------- -------------------------------------
  **GetStreamLoggerFn** typedef (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                                                                                                                                                  [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           
  **Log**(const google::protobuf::Message &request, const google::protobuf::Message &response, const LogMetadata &log\_metadata) (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                                                 [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           
  **logging\_config**() const (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                                                                                                                                                    [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           [inline]{.mlabel}
  **MaybeStartLoggingStream**(const LogMetadata &log\_metadata, GetStreamLoggerFn\< Request, Response \> get\_stream\_logger\_fn) (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                                                [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           
  **MOCK\_METHOD**(Status, CreateLogMessage,(const google::protobuf::Message &request, const google::protobuf::Message &response, const LogMetadata &log\_metadata, std::unique\_ptr\< google::protobuf::Message \> \*log),(override)) (defined in [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el})   [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el}   
  **MOCK\_METHOD**(LogMetadata, FillLogMetadata,(const LogMetadata &),(override)) (defined in [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el})                                                                                                                                                        [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el}   
  **MockRequestLogger**(const LoggingConfig &logging\_config, const std::vector\< string \> &saved\_model\_tags, LogCollector \*log\_collector, std::function\< void(void)\> notify\_destruction=std::function\< void(void)\>()) (defined in [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el})         [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el}   [inline]{.mlabel}
  **RequestLogger**(const LoggingConfig &logging\_config, const std::vector\< string \> &saved\_model\_tags, std::unique\_ptr\< LogCollector \> log\_collector) (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                  [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           
  **\~MockRequestLogger**() (defined in [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el})                                                                                                                                                                                                              [tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **\~RequestLogger**()=default (defined in [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el})                                                                                                                                                                                                                  [tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.el}           [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
