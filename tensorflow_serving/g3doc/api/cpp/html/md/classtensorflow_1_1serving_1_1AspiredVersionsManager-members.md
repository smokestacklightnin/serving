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
-   [AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::AspiredVersionsManager Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- --------------------
  **Create**(Options options, std::unique\_ptr\< AspiredVersionsManager \> \*manager) (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})   [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [static]{.mlabel}
  **CustomSortActionsFn** typedef (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                                       [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     
  [GetAspiredVersionsCallback](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a4fcdded2573a67abe77f238857e57f35){.el}() override                                                                        [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [virtual]{.mlabel}
  [GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.el}() const                                                                                         [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}                                   
  [GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.el}(const ServableRequest &request, ServableHandle\< T \> \*const handle)                                     [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}                                   
  **internal::AspiredVersionsManagerTargetImpl** (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                        [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [friend]{.mlabel}
  **internal::GetManagerNumLoadThreads** (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                                [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [friend]{.mlabel}
  **internal::SetManagerNumLoadThreadsNotifier** (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                        [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [friend]{.mlabel}
  [ListAvailableServableIds](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a058a76ee71c52d4a6319f14cd9b2ad69){.el}() const override                                                                    [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [virtual]{.mlabel}
  **PreLoadHook** typedef (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                                               [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     
  **ServerCore** (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                                                        [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [friend]{.mlabel}
  **test\_util::AspiredVersionsManagerTestAccess** (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                      [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     [friend]{.mlabel}
  **\~AspiredVersionsManager**() override (defined in [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el})                                               [tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}     
  **\~Manager**()=default (defined in [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el})                                                                                             [tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}                                   [virtual]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                              [tensorflow::serving::Target\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1Target.html){.el}   [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- --------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
