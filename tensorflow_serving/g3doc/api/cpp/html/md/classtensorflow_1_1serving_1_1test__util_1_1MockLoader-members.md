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
-   [MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockLoader Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- -------------------------------------
  [EstimateResources](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.el}(ResourceAllocation \*estimate) const =0                                                                                [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [pure virtual]{.mlabel}
  [Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}()                                                                                                                                   [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [inline]{.mlabel}[virtual]{.mlabel}
  [LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}(const Metadata &metadata)                                                                                               [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [inline]{.mlabel}[virtual]{.mlabel}
  **MOCK\_METHOD**(Status, EstimateResources,(ResourceAllocation \*estimate),(const, override)) (defined in [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el})   [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}   
  **MOCK\_METHOD**(Status, Load,(),(override)) (defined in [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el})                                                    [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}   
  **MOCK\_METHOD**(Status, LoadWithMetadata,(const Metadata &),(override)) (defined in [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el})                        [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}   
  **MOCK\_METHOD**(void, Unload,(),(override)) (defined in [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el})                                                    [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}   
  **MOCK\_METHOD**(AnyPtr, servable,(),(override)) (defined in [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el})                                                [tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.el}   
  [servable](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}()=0                                                                                                                             [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [pure virtual]{.mlabel}
  [Unload](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}()=0                                                                                                                               [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [pure virtual]{.mlabel}
  [\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}()=default                                                                                                                       [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
