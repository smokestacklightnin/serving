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
-   [DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::DynamicSourceRouter\< T \> Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::DynamicSourceRouter\< T
\>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------
  **Create**(int num\_output\_ports, const Routes &routes, std::unique\_ptr\< DynamicSourceRouter\< T \>\> \*result) (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})   [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   [static]{.mlabel}
  **Detach**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                           [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                     [protected]{.mlabel}
  **GetAspiredVersionsCallback**() final (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                 [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                     [virtual]{.mlabel}
  **GetOutputPorts**() (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                                               [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}                 
  **GetRoutes**() const (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})                                                                                                [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   
  **kNoRoute** (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                                                       [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}                 [static]{.mlabel}
  **num\_output\_ports**() const override (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})                                                                              [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   [inline]{.mlabel}[protected]{.mlabel}[virtual]{.mlabel}
  **Route**(const StringPiece servable\_name, const std::vector\< ServableData\< T \>\> &versions) override (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})            [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   [protected]{.mlabel}[virtual]{.mlabel}
  **Routes** typedef (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})                                                                                                   [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   
  **SetAspiredVersions**(const StringPiece servable\_name, std::vector\< ServableData\< T \>\> versions) final (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                       [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}                 [virtual]{.mlabel}
  **SourceRouter**()=default (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                                         [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}                 [protected]{.mlabel}
  **TargetBase**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                       [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                     [protected]{.mlabel}
  **UpdateRoutes**(const Routes &routes) (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})                                                                               [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   
  **\~DynamicSourceRouter**() override (defined in [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el})                                                                                 [tensorflow::serving::DynamicSourceRouter\< T \>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.el}   
  **\~SourceRouter**() override=0 (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                                    [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}                 [pure virtual]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                                                                                         [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el}                             [virtual]{.mlabel}
  **\~TargetBase**() override (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                            [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                     
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
