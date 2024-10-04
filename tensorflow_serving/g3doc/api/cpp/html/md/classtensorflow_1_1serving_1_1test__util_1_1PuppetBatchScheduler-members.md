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
-   [PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>
Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType
\>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------
  **max\_task\_size**() const override (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                                  [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   [inline]{.mlabel}
  **NumEnqueuedTasks**() const override (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                                 [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  **ProcessAllTasks**() (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                                                 [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  **ProcessTasks**(int num\_tasks) (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                                      [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  **PuppetBatchScheduler**(std::function\< void(std::unique\_ptr\< Batch\< TaskType \>\>)\> process\_batch\_callback) (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})   [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   [explicit]{.mlabel}
  **Schedule**(std::unique\_ptr\< TaskType \> \*task) override (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                          [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  **SchedulingCapacity**() const override (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                               [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  **\~PuppetBatchScheduler**() override=default (defined in [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el})                                                                         [tensorflow::serving::test\_util::PuppetBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.el}   
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
