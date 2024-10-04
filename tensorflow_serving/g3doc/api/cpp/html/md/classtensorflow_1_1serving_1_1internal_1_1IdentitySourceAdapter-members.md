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
-   [IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::internal::IdentitySourceAdapter\< T \> Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::internal::IdentitySourceAdapter\< T
\>](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------
  [AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.el}(ServableData\< T \> input)                                                                                [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                      
  [AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el} typedef                                                                                                  [tensorflow::serving::Source\< T \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                       
  **Detach**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                               [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                               [protected]{.mlabel}
  **GetAspiredVersionsCallback**() final (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                     [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                               [virtual]{.mlabel}
  **IdentitySourceAdapter**()=default (defined in [tensorflow::serving::internal::IdentitySourceAdapter\< T \>](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el})                            [tensorflow::serving::internal::IdentitySourceAdapter\< T \>](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el}   
  [SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.el}(const StringPiece servable\_name, std::vector\< ServableData\< T \>\> versions) final                  [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                      
  **SetAspiredVersions**(const StringPiece servable\_name, std::vector\< ServableData\< T \>\> versions)=0 (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})   [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                               [protected]{.mlabel}[pure virtual]{.mlabel}
  **SetAspiredVersionsCallback**(typename Source\< T \>::AspiredVersionsCallback callback) final (defined in [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})    [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                      
  [tensorflow::serving::Source::SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}(AspiredVersionsCallback callback)=0                                      [tensorflow::serving::Source\< T \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                       [pure virtual]{.mlabel}
  **SourceAdapter**()=default (defined in [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})                                                                       [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                      [protected]{.mlabel}
  **TargetBase**() (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                           [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                               [protected]{.mlabel}
  **\~IdentitySourceAdapter**() override (defined in [tensorflow::serving::internal::IdentitySourceAdapter\< T \>](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el})                         [tensorflow::serving::internal::IdentitySourceAdapter\< T \>](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.el}   [inline]{.mlabel}
  **\~Source**()=default (defined in [tensorflow::serving::Source\< T \>](classtensorflow_1_1serving_1_1Source.html){.el})                                                                                             [tensorflow::serving::Source\< T \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                       [virtual]{.mlabel}
  **\~SourceAdapter**() override=0 (defined in [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})                                                                  [tensorflow::serving::SourceAdapter\< T, T \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                      [pure virtual]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                                                             [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el}                                                       [virtual]{.mlabel}
  **\~TargetBase**() override (defined in [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                [tensorflow::serving::TargetBase\< T \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                               
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
