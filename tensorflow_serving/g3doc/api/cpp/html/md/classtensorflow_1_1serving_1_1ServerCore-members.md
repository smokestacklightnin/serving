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
-   [ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::ServerCore Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------- -------------------------------------
  [Create](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642){.el}(Options options, std::unique\_ptr\< ServerCore \> \*core)                                                                                                   [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [static]{.mlabel}
  [CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.el} typedef                                                                                                                                    [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   
  **enable\_cors\_support**() const (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                       [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}
  **GetAvailableServableHandles**() const (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                 [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}
  [GetServableHandle](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf){.el}(const ModelSpec &model\_spec, ServableHandle\< T \> \*const handle)                                                                              [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}
  **GetServableHandle**(const ModelSpec &model\_spec, ServableHandle\< Servable \> \*const handle) (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                        [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  [tensorflow::serving::Manager::GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.el}(const ServableRequest &request, ServableHandle\< T \> \*const handle)                                                 [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}         
  [ListAvailableServableIds](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709){.el}() const override                                                                                                                          [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  [Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.el}(const google::protobuf::Message &request, const google::protobuf::Message &response, const LogMetadata &log\_metadata)                                         [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **predict\_response\_tensor\_serialization\_option**() const (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                            [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}
  **PreLoadHook** typedef (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                                 [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   
  [ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669){.el}(const ModelServerConfig &config) TF\_LOCKS\_EXCLUDED(config\_mu\_)                                                                                    [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [virtual]{.mlabel}
  [servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.el}() const                                                                                                                                   [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **ServableStateMonitorCreator** typedef (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                 [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   
  **ServerCore**(Options options) (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                         [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [protected]{.mlabel}
  [ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.el} typedef                                                                                                                                 [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   
  **StartLoggingStream**(const LogMetadata &log\_metadata, ServerRequestLogger::CreateStreamLoggerFn\< Request, Response \> create\_stream\_logger\_fn) (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})   [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [inline]{.mlabel}
  **test\_util::ServerCoreTestAccess** (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                    [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [friend]{.mlabel}
  **\~Manager**()=default (defined in [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el})                                                                                                                                       [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}         [virtual]{.mlabel}
  **\~ServerCore**()=default (defined in [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el})                                                                                                                              [tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.el}   [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
