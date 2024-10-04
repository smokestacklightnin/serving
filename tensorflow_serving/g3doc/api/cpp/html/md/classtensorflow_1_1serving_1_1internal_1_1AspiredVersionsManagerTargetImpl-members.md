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
-   **internal**
-   [AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::internal::AspiredVersionsManagerTargetImpl Member
List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------
  **AspiredVersionsManagerTargetImpl**(AspiredVersionsManager \*const parent) (defined in [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el})                                                                 [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el}   [inline]{.mlabel}[explicit]{.mlabel}
  **Detach**() (defined in [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                                                [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                   [protected]{.mlabel}
  **GetAspiredVersionsCallback**() final (defined in [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                      [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                   [virtual]{.mlabel}
  **SetAspiredVersions**(const StringPiece servable\_name, std::vector\< ServableData\< std::unique\_ptr\< Loader \>\>\> versions) override (defined in [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el})   [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el}   [inline]{.mlabel}[protected]{.mlabel}
  **SetAspiredVersions**(const StringPiece servable\_name, std::vector\< ServableData\< std::unique\_ptr\< Loader \> \>\> versions)=0 (defined in [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                         [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                   [protected]{.mlabel}[pure virtual]{.mlabel}
  **TargetBase**() (defined in [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                                            [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                   [protected]{.mlabel}
  **\~AspiredVersionsManagerTargetImpl**() override (defined in [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el})                                                                                           [tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.el}   [inline]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                                                                                                                              [tensorflow::serving::Target\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1Target.html){.el}                                           [virtual]{.mlabel}
  **\~TargetBase**() override (defined in [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                                 [tensorflow::serving::TargetBase\< std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                   
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
