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
-   [SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------
  **Close**() final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                                                               [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}                                                 
  **Create**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}                                                 
  **Extend**(const GraphDef &graph) final (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}                                                 
  **ListDevices**(std::vector\< DeviceAttributes \> \*response) override (defined in [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el})                                                                                                                                                                                                                                                                                                            [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el}                                   [inline]{.mlabel}
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata, const thread::ThreadPoolOptions &thread\_pool\_options) override (defined in [tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el})   [tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el}   [inline]{.mlabel}
  **Run**(const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs) override (defined in [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el})                                                                                                                                                        [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el}                                   [inline]{.mlabel}
  **Run**(const RunOptions &run\_options, const std::vector\< std::pair\< string, Tensor \>\> &inputs, const std::vector\< string \> &output\_tensor\_names, const std::vector\< string \> &target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata \*run\_metadata) override (defined in [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el})                                                                                           [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el}                                   [inline]{.mlabel}
  **ServingSession**()=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                                                    [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}                                                 
  **ServingSessionWrapper**(std::unique\_ptr\< Session \> wrapped) (defined in [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el})                                                                                                                                                                                                                                                                                                                  [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el}                                   [inline]{.mlabel}[explicit]{.mlabel}
  **SessionWrapperIgnoreThreadPoolOptions**(std::unique\_ptr\< Session \> wrapped) (defined in [tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el})                                                                                                                                                                                                                                                                  [tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.el}   [inline]{.mlabel}[explicit]{.mlabel}
  **\~ServingSession**() override=default (defined in [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el})                                                                                                                                                                                                                                                                                                                                                         [tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}                                                 
  **\~ServingSessionWrapper**() override=default (defined in [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el})                                                                                                                                                                                                                                                                                                                                    [tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.el}                                   
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
