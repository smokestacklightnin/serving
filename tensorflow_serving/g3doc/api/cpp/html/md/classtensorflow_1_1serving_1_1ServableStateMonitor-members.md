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
-   [ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::ServableStateMonitor Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------- ---------------------
  **BoundedLog** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                    [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [ForgetUnloadedServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#ae3ad2a50b7fa7b695885fe913b70b029){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                                       [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetAllServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#abc3c1c27b6b7c0e8ef9a42039ede74cc){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                                         [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **GetAvailableServableStates**() const TF\_LOCKS\_EXCLUDED(mu\_) (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                          [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetBoundedLog](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a2afc57f0eb671a3c3342c7dd71a9d6a7){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                                                [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetLiveServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a522166e0255c93e87a6d63c3d17e3f38){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                                        [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetState](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8fa6dd1536bbb85a55b3e41c1d2577d1){.el}(const ServableId &servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                       [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetStateAndTime](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8ff54ab2471885168dba0b1a05be7bea){.el}(const ServableId &servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [GetVersionStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a501ef561e30709fe17f10c913d34bb1e){.el}(const string &servable\_name) const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                                                                                                                 [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **Notify**(const NotifyFn &notify\_fn) TF\_LOCKS\_EXCLUDED(notify\_mu\_) (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                  [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **NotifyFn** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                      [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **NotifyWhenServablesReachState**(const std::vector\< ServableRequest \> &servables, ServableState::ManagerState goal\_state, const ServableStateNotifierFn &notifier\_fn) TF\_LOCKS\_EXCLUDED(mu\_) (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                      [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **ServableMap** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                   [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **ServableName** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                  [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **ServableSet** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                   [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **ServableStateMonitor**(EventBus\< ServableState \> \*bus, const Options &options=Options()) (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                             [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   [explicit]{.mlabel}
  [ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.el} typedef                                                                                                                                                                                                                                                                [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **Version** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                       [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **VersionMap** typedef (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                                    [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **WaitUntilServablesReachState**(const std::vector\< ServableRequest \> &servables, ServableState::ManagerState goal\_state, std::map\< ServableId, ServableState::ManagerState \> \*states\_reached=nullptr) TF\_MUST\_USE\_RESULT (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                       [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  [WaitUntilServablesReachStateWithTimeout](classtensorflow_1_1serving_1_1ServableStateMonitor.html#aa9579ee04bf76fa627d65d9cbbb7ccb7){.el}(const std::vector\< ServableRequest \> &servables, ServableState::ManagerState goal\_state, absl::Duration timeout, std::map\< ServableId, ServableState::ManagerState \> \*states\_reached=nullptr) TF\_LOCKS\_EXCLUDED(mu\_) TF\_MUST\_USE\_RESULT   [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   
  **\~ServableStateMonitor**() (defined in [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el})                                                                                                                                                                                                                                              [tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.el}   [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------- ---------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
