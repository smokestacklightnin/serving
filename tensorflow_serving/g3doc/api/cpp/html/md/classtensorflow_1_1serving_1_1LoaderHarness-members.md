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
-   [LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::LoaderHarness Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------- -------------------
  [additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.el}()                                                                                                                                     [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [inline]{.mlabel}
  [DoneQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a11b81e561e55c5b21907f8fc2eafe6e9){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                               [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [Error](classtensorflow_1_1serving_1_1LoaderHarness.html#a9833ae8f23545a9975901d8a3508d30a){.el}(const Status &status) TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                   [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.el}() const                                                                                                                                              [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [inline]{.mlabel}
  [Load](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                        [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [LoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#aab4e0158cc9fccd7539df5a9fa312e8c){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.el}() const                                                                                                                                          [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [inline]{.mlabel}
  [loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                               [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  **loader\_state\_snapshot**() const (defined in [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el})                                                                                                       [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [inline]{.mlabel}
  **LoaderHarness**(const ServableId &id, std::unique\_ptr\< Loader \> loader, const Options &options=Options()) (defined in [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el})                            [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a7f7ab209922600ef1d95e6be35dec8fd){.el}(const ServableId &id, std::unique\_ptr\< Loader \> loader, std::unique\_ptr\< T \> additional\_state, const Options &options=Options())   [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [inline]{.mlabel}
  [LoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#af38723eb75813331dad2f0d910466f57){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                               [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [set\_should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#a001ec617f6fd186d27cc911f9a952f00){.el}(std::function\< bool(absl::Status)\> should\_retry) TF\_LOCKS\_EXCLUDED(mu\_)                                                        [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435){.el}(absl::Status status) TF\_LOCKS\_EXCLUDED(mu\_)                                                                                            [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [StartQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a811f9dbe7ab8fb5df0c35916ec57aad8){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                              [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.el} enum name                                                                                                                                         [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                 [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  **StateDebugString**(State state) (defined in [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el})                                                                                                         [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   [static]{.mlabel}
  [status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.el}() const TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [Unload](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                                      [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [UnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a6451e73c25ba30b0c78a560deba29e03){.el}() TF\_LOCKS\_EXCLUDED(mu\_)                                                                                                             [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  [\~LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a60facd158c858dbdcaaae74a18a4edd9){.el}()                                                                                                                                       [tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}   
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------- -------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
