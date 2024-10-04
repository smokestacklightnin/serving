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
-   [StreamingBatchScheduler](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::StreamingBatchScheduler\< TaskType \> Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::StreamingBatchScheduler\< TaskType
\>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------- -------------------
  **Create**(const Options &options, std::function\< void(std::unique\_ptr\< Batch\< TaskType \>\>)\> process\_batch\_callback, std::unique\_ptr\< StreamingBatchScheduler\< TaskType \>\> \*scheduler) (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})   [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   [static]{.mlabel}
  **max\_task\_size**() const override (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})                                                                                                                                                                    [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   [inline]{.mlabel}
  **NumEnqueuedTasks**() const override (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})                                                                                                                                                                   [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   [inline]{.mlabel}
  **Schedule**(std::unique\_ptr\< TaskType \> \*task) override (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})                                                                                                                                            [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   
  **SchedulingCapacity**() const override (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})                                                                                                                                                                 [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   
  **\~StreamingBatchScheduler**() override (defined in [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el})                                                                                                                                                                [tensorflow::serving::StreamingBatchScheduler\< TaskType \>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.el}   
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
