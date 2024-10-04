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
-   [MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::MockLogCollector Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- -------------------------
  **CollectMessage**(const google::protobuf::Message &message)=0 (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                       [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [pure virtual]{.mlabel}
  **Create**(const LogCollectorConfig &log\_collector\_config, const uint32 id, std::unique\_ptr\< LogCollector \> \*log\_collector) (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})   [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [static]{.mlabel}
  **Factory** typedef (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                                                                  [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           
  **Flush**()=0 (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                                                                        [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [pure virtual]{.mlabel}
  **LogCollector**()=default (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                                                           [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [protected]{.mlabel}
  **MOCK\_METHOD**(Status, CollectMessage,(const google::protobuf::Message &message),(override)) (defined in [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el})                               [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el}   
  **MOCK\_METHOD**(Status, Flush,(),(override)) (defined in [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el})                                                                                [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el}   
  **MockLogCollector**()=default (defined in [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el})                                                                                               [tensorflow::serving::MockLogCollector](classtensorflow_1_1serving_1_1MockLogCollector.html){.el}   
  **RegisterFactory**(const string &type, const Factory &factory) (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                      [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [static]{.mlabel}
  **\~LogCollector**()=default (defined in [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el})                                                                                                         [tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.el}           [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
