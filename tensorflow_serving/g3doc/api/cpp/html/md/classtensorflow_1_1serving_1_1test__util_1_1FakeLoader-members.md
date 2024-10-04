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
-   [FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::FakeLoader Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- -------------------------------------
  [EstimateResources](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}(ResourceAllocation \*estimate) const final                                       [tensorflow::serving::ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.el}         [inline]{.mlabel}[virtual]{.mlabel}
  **FakeLoader**(int64\_t servable, const Status load\_status=Status()) (defined in [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el})   [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [explicit]{.mlabel}
  [Load](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}() override                                                                                [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [virtual]{.mlabel}
  **load\_status**() (defined in [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el})                                                      [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   
  [LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}(const Metadata &metadata)                                                                       [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [inline]{.mlabel}[virtual]{.mlabel}
  **num\_fake\_loaders**() (defined in [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el})                                                [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [static]{.mlabel}
  [servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el}() override                                                                            [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [virtual]{.mlabel}
  [Unload](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el}() override                                                                              [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [virtual]{.mlabel}
  **was\_deleted\_in\_this\_thread**() (defined in [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el})                                    [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   [static]{.mlabel}
  **\~FakeLoader**() override (defined in [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el})                                             [tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}   
  [\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}()=default                                                                                               [tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}                                     [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
