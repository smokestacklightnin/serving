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
-   [SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::SourceRouter\< T \> Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::SourceRouter\< T
\>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}, including all
inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------- ---------------------------------------------
  **Detach**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                       [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}       [protected]{.mlabel}
  **GetAspiredVersionsCallback**() final (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                             [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}       [virtual]{.mlabel}
  **GetOutputPorts**() (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                           [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   
  **kNoRoute** (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                                   [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [static]{.mlabel}
  **num\_output\_ports**() const =0 (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                              [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [protected]{.mlabel}[pure virtual]{.mlabel}
  **Route**(const StringPiece servable\_name, const std::vector\< ServableData\< T \>\> &versions)=0 (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})             [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [protected]{.mlabel}[pure virtual]{.mlabel}
  **SetAspiredVersions**(const StringPiece servable\_name, std::vector\< ServableData\< T \>\> versions) final (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})   [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [virtual]{.mlabel}
  **SourceRouter**()=default (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                     [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [protected]{.mlabel}
  **TargetBase**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                   [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}       [protected]{.mlabel}
  **\~SourceRouter**() override=0 (defined in [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el})                                                                                [tensorflow::serving::SourceRouter\< T \>](classtensorflow_1_1serving_1_1SourceRouter.html){.el}   [pure virtual]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                                                                     [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el}               [virtual]{.mlabel}
  **\~TargetBase**() override (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                        [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}       
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------- ---------------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
