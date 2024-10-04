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
-   **net\_http**
-   [ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::ZLib Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el},
including all inherited members.

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- ------------------------------------
  **Compress**(Bytef \*dest, uLongf \*destLen, const Bytef \*source, uLong sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                      [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **CompressAtMost**(Bytef \*dest, uLongf \*destLen, const Bytef \*source, uLong \*sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})              [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **CompressChunkDone**(Bytef \*dest, uLongf \*destLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                    [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **first\_chunk**() const (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                 [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}
  **GzipUncompressedLength**(const Bytef \*source, uLong len) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                              [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **HasGzipHeader**(const char \*source, int sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                    [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [static]{.mlabel}
  **IsGzipFooterComplete**() const (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                         [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **IsGzipFooterValid**() const (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                            [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **kMaxUncompressedBytes** (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [static]{.mlabel}
  **MinCompressbufSize**(uLong uncompress\_size) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                           [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}[static]{.mlabel}
  **MinFooterSize**() const (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **Reinit**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                             [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **Reset**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                              [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **SetCompressionLevel**(int level) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                       [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}
  **SetCompressionMemLevel**(int level) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                    [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}
  **SetCompressionWindowSizeInBits**(int bits) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                             [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}
  **SetDontHideStreamEnd**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                               [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **Uncompress**(Bytef \*dest, uLongf \*destLen, const Bytef \*source, uLong sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                    [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **UncompressAtMost**(Bytef \*dest, uLongf \*destLen, const Bytef \*source, uLong \*sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})            [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **UncompressChunkDone**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **uncompressed\_size**() const (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                           [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   [inline]{.mlabel}
  **UncompressGzipAndAllocate**(Bytef \*\*dest, uLongf \*destLen, const Bytef \*source, uLong sourceLen) (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})   [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **ZLib**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                               [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  **\~ZLib**() (defined in [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el})                                                                                             [tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.el}   
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- ------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
