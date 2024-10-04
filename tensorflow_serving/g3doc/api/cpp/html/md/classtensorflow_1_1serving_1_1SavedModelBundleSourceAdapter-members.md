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
-   [SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::SavedModelBundleSourceAdapter Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el},
including all inherited members.

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------ -------------------------
  [AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.el}(ServableData\< InputType \> input)                                                                                                                           [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                 
  [AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el} typedef                                                                                                                                                     [tensorflow::serving::Source\< OutputType \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                          
  **Create**(const SavedModelBundleSourceAdapterConfig &config, std::unique\_ptr\< SavedModelBundleSourceAdapter \> \*adapter) (defined in [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el})   [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el}                            [static]{.mlabel}
  **Detach**() (defined in [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                          [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                                   [protected]{.mlabel}
  **GetAspiredVersionsCallback**() final (defined in [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                                   [virtual]{.mlabel}
  **SavedModelBundleSourceAdapterCreator** (defined in [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el})                                                                                       [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el}                            [friend]{.mlabel}
  [SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.el}(const StringPiece servable\_name, std::vector\< ServableData\< InputType \>\> versions) final                                                             [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                 [virtual]{.mlabel}
  **SetAspiredVersionsCallback**(typename Source\< OutputType \>::AspiredVersionsCallback callback) final (defined in [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})                             [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                 
  [Source\< OutputType \>::SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}(AspiredVersionsCallback callback)=0                                                                                              [tensorflow::serving::Source\< OutputType \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                          [pure virtual]{.mlabel}
  **SourceAdapter**()=default (defined in [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})                                                                                                         [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                 [protected]{.mlabel}
  **TargetBase**() (defined in [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                                      [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                                   [protected]{.mlabel}
  **UnarySourceAdapter**()=default (defined in [tensorflow::serving::UnarySourceAdapter\< StoragePath, std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.el})                                                                      [tensorflow::serving::UnarySourceAdapter\< StoragePath, std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.el}   [protected]{.mlabel}
  **\~SavedModelBundleSourceAdapter**() override (defined in [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el})                                                                                 [tensorflow::serving::SavedModelBundleSourceAdapter](classtensorflow_1_1serving_1_1SavedModelBundleSourceAdapter.html){.el}                            
  **\~Source**()=default (defined in [tensorflow::serving::Source\< OutputType \>](classtensorflow_1_1serving_1_1Source.html){.el})                                                                                                                                       [tensorflow::serving::Source\< OutputType \>](classtensorflow_1_1serving_1_1Source.html){.el}                                                          [virtual]{.mlabel}
  **\~SourceAdapter**() override=0 (defined in [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el})                                                                                                    [tensorflow::serving::SourceAdapter\< InputType, OutputType \>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}                                 [pure virtual]{.mlabel}
  **\~Target**()=default (defined in [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el})                                                                                                                                                [tensorflow::serving::Target\< T \>](classtensorflow_1_1serving_1_1Target.html){.el}                                                                   [virtual]{.mlabel}
  **\~TargetBase**() override (defined in [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el})                                                                                                                           [tensorflow::serving::TargetBase\< InputType \>](classtensorflow_1_1serving_1_1TargetBase.html){.el}                                                   
  **\~UnarySourceAdapter**() override=0 (defined in [tensorflow::serving::UnarySourceAdapter\< StoragePath, std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.el})                                                                 [tensorflow::serving::UnarySourceAdapter\< StoragePath, std::unique\_ptr\< Loader \> \>](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.el}   [pure virtual]{.mlabel}
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------ -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
