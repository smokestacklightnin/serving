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
-   [ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::ServerRequestInterface Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el},
including all inherited members.

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------
  **Abort**()=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                                        [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **AppendResponseHeader**(absl::string\_view header, absl::string\_view value)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})      [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **BodyStatus** enum name (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                             [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **CallbackStatus** enum name (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                         [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **GetRequestHeader**(absl::string\_view header) const =0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                             [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **http\_method**() const =0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                          [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **operator=**(const ServerRequestInterface &other)=delete (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                            [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **OverwriteResponseHeader**(absl::string\_view header, absl::string\_view value)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})   [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **PartialReply**()=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                                 [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **PartialReplyWithFlushCallback**(std::function\< void()\> callback)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})               [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **PartialReplyWithStatus**(HTTPStatusCode status)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                  [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **ReadRequestBytes**(int64\_t \*size)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                              [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **Reply**()=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                                        [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **ReplyWithStatus**(HTTPStatusCode status)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                         [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **request\_body\_status**() (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                          [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **request\_headers**() const =0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                      [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **response\_body\_status**() (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                         [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **ServerRequestInterface**(const ServerRequestInterface &other)=delete (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})               [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **ServerRequestInterface**()=default (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                 [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [protected]{.mlabel}
  **uri\_path**() const =0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                             [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **WriteResponseBytes**(const char \*data, int64\_t size)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                           [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **WriteResponseString**(absl::string\_view data)=0 (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                   [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [pure virtual]{.mlabel}
  **\~ServerRequestInterface**()=default (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                               [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [virtual]{.mlabel}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
