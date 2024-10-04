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
-   [MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockServerRequestLogger Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------- -----------------------------------------
  **Create**(LoggerCreator request\_logger\_creator, std::unique\_ptr\< ServerRequestLogger \> \*server\_request\_logger) (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                              [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     [static]{.mlabel}
  **CreateStreamLoggerFn** typedef (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                                                                                                                     [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     
  **Log**(const google::protobuf::Message &request, const google::protobuf::Message &response, const LogMetadata &log\_metadata) (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                       [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     [virtual]{.mlabel}
  **LoggerCreator** typedef (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                                                                                                                            [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     
  **MOCK\_METHOD**(Status, Update,((const std::map\< string, std::vector\< LoggingConfig \>\> &logging\_config\_map)),(override)) (defined in [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el})                                    [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el}   
  **MOCK\_METHOD**(Status, Log,(const google::protobuf::Message &request, const google::protobuf::Message &response, const LogMetadata &log\_metadata),(override)) (defined in [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el})   [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el}   
  **MockServerRequestLogger**() (defined in [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el})                                                                                                                                      [tensorflow::serving::test\_util::MockServerRequestLogger](classtensorflow_1_1serving_1_1test__util_1_1MockServerRequestLogger.html){.el}   [inline]{.mlabel}
  **ServerRequestLogger**(LoggerCreator request\_logger\_creator) (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                                                                                      [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     [explicit]{.mlabel}[protected]{.mlabel}
  **StartLoggingStream**(const LogMetadata &log\_metadata, CreateStreamLoggerFn\< Request, Response \> create\_stream\_logger\_fn) (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                     [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     
  **Update**(const std::map\< string, std::vector\< LoggingConfig \>\> &logging\_config\_map) (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                                                          [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     [virtual]{.mlabel}
  **\~ServerRequestLogger**()=default (defined in [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el})                                                                                                                                                                  [tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.el}                                     [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------- -----------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
