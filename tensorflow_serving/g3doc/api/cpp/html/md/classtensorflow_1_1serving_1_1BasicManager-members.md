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
-   [BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::BasicManager Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el},
including all inherited members.

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------- --------------------
  **AspiredVersionsManager** (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})                                                                                                             [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [friend]{.mlabel}
  [CancelLoadServableRetry](classtensorflow_1_1serving_1_1BasicManager.html#a84dca5ec1ecc28421d5ab020beac2ee3){.el}(const ServableId &id)                                                                                                       [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  **Create**(Options options, std::unique\_ptr\< BasicManager \> \*manager) (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})                                                              [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [static]{.mlabel}
  [DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.el} typedef                                                                                                                                [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [GetAdditionalServableState](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335){.el}(const ServableId &id)                                                                                                    [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.el}() const                                                                                                                      [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}             
  **GetAvailableUntypedServableHandles**() const override (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})                                                                                [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [virtual]{.mlabel}
  [GetManagedServableNames](classtensorflow_1_1serving_1_1BasicManager.html#afbdc3d0ed83559c7d8b3b0092194ead6){.el}() const                                                                                                                     [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [GetManagedServableStateSnapshot](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75){.el}(const ServableId &id)                                                                                               [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [GetManagedServableStateSnapshots](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826){.el}(const string &servable\_name) const                                                                                [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.el}(const ServableRequest &request, ServableHandle\< T \> \*const handle)                                                                  [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}             
  **GetUntypedServableHandle**(const ServableRequest &request, std::unique\_ptr\< UntypedServableHandle \> \*untyped\_handle) override (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})   [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [virtual]{.mlabel}
  [ListAvailableServableIds](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639){.el}() const override                                                                                                           [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [virtual]{.mlabel}
  [LoadServable](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.el}(const ServableId &id, DoneCallback done\_callback)                                                                                     [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [ManageServable](classtensorflow_1_1serving_1_1BasicManager.html#ac2759caea67d3d37b9dba31589f9ef1d){.el}(ServableData\< std::unique\_ptr\< Loader \>\> servable)                                                                              [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [ManageServableWithAdditionalState](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc){.el}(ServableData\< std::unique\_ptr\< Loader \>\> servable, std::unique\_ptr\< T \> additional\_state)                [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  **PreLoadHook** typedef (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})                                                                                                                [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [StopManagingServable](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43){.el}(const ServableId &id)                                                                                                          [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  **test\_util::BasicManagerTestAccess** (defined in [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el})                                                                                                 [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   [friend]{.mlabel}
  [UnloadServable](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.el}(const ServableId &id, DoneCallback done\_callback)                                                                                   [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  [\~BasicManager](classtensorflow_1_1serving_1_1BasicManager.html#a492123b8bb97709184ddb57772e3ccf3){.el}() override                                                                                                                           [tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.el}   
  **\~Manager**()=default (defined in [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el})                                                                                                                          [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}             [virtual]{.mlabel}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------- --------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
