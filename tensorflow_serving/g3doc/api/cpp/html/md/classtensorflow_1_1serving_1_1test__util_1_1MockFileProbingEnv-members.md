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
-   [MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::MockFileProbingEnv Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el},
including all inherited members.

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- -------------------------
  **FileExists**(const string &fname)=0 (defined in [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el})                                                                                                          [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el}                                     [pure virtual]{.mlabel}
  **GetChildren**(const string &dir, std::vector\< string \> \*children)=0 (defined in [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el})                                                                       [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el}                                     [pure virtual]{.mlabel}
  **GetFileSize**(const string &fname, uint64\_t \*file\_size)=0 (defined in [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el})                                                                                 [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el}                                     [pure virtual]{.mlabel}
  **IsDirectory**(const string &fname)=0 (defined in [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el})                                                                                                         [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el}                                     [pure virtual]{.mlabel}
  **MOCK\_METHOD**(Status, FileExists,(const string &fname),(override)) (defined in [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el})                                        [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el}   
  **MOCK\_METHOD**(Status, GetChildren,(const string &fname, std::vector\< string \> \*children),(override)) (defined in [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el})   [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el}   
  **MOCK\_METHOD**(Status, IsDirectory,(const string &fname),(override)) (defined in [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el})                                       [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el}   
  **MOCK\_METHOD**(Status, GetFileSize,(const string &fname, uint64\_t \*file\_size),(override)) (defined in [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el})               [tensorflow::serving::test\_util::MockFileProbingEnv](classtensorflow_1_1serving_1_1test__util_1_1MockFileProbingEnv.html){.el}   
  **\~FileProbingEnv**()=default (defined in [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el})                                                                                                                 [tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.el}                                     [virtual]{.mlabel}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
