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
-   [FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::FileSystemStoragePathSource Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------- -------------------------
  [AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el} typedef                                                                                                                                            [tensorflow::serving::Source\< StoragePath \>](classtensorflow_1_1serving_1_1Source.html){.el}                            
  **config**() const (defined in [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el})                                                                                                        [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   [inline]{.mlabel}
  **Create**(const FileSystemStoragePathSourceConfig &config, std::unique\_ptr\< FileSystemStoragePathSource \> \*result) (defined in [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el})   [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   [static]{.mlabel}
  **internal::FileSystemStoragePathSourceTestAccess** (defined in [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el})                                                                       [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   [friend]{.mlabel}
  **SetAspiredVersionsCallback**(AspiredVersionsCallback callback) override (defined in [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el})                                                 [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   
  [Source\< StoragePath \>::SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}(AspiredVersionsCallback callback)=0                                                                                    [tensorflow::serving::Source\< StoragePath \>](classtensorflow_1_1serving_1_1Source.html){.el}                            [pure virtual]{.mlabel}
  [UpdateConfig](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html#ad29df4b1d9628b03723474db5a0d6ad0){.el}(const FileSystemStoragePathSourceConfig &config)                                                                                         [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   
  **\~FileSystemStoragePathSource**() override (defined in [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el})                                                                              [tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.el}   
  **\~Source**()=default (defined in [tensorflow::serving::Source\< StoragePath \>](classtensorflow_1_1serving_1_1Source.html){.el})                                                                                                                             [tensorflow::serving::Source\< StoragePath \>](classtensorflow_1_1serving_1_1Source.html){.el}                            [virtual]{.mlabel}
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
