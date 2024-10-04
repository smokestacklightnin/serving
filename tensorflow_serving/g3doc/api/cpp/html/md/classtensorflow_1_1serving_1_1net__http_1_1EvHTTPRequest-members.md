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
-   [EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::EvHTTPRequest Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------
  **Abort**() override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                                        [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **AppendResponseHeader**(absl::string\_view header, absl::string\_view value) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})      [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **BodyStatus** enum name (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                                  [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **CallbackStatus** enum name (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                              [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **EvHTTPRequest**(const EvHTTPRequest &other)=delete (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                        [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     
  **EvHTTPRequest**(std::unique\_ptr\< ParsedEvRequest \> request, ServerSupport \*server) (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})    [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     
  **GetRequestHeader**(absl::string\_view header) const override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                              [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **http\_method**() const override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                           [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **Initialize**() (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                                            [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     
  **operator=**(const EvHTTPRequest &other)=delete (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                            [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     
  **operator=**(const ServerRequestInterface &other)=delete (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                 [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **OverwriteResponseHeader**(absl::string\_view header, absl::string\_view value) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})   [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **PartialReply**() override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                                 [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **PartialReplyWithFlushCallback**(std::function\< void()\> callback) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})               [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **PartialReplyWithStatus**(HTTPStatusCode status) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                  [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **ReadRequestBytes**(int64\_t \*size) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                              [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **Reply**() override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                                        [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **ReplyWithStatus**(HTTPStatusCode status) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                         [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **request\_body\_status**() (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                               [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **request\_headers**() const override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                       [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **response\_body\_status**() (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                              [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [inline]{.mlabel}[virtual]{.mlabel}
  **ServerRequestInterface**(const ServerRequestInterface &other)=delete (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})    [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   
  **ServerRequestInterface**()=default (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                      [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [protected]{.mlabel}
  **SetHandlerOptions**(const RequestHandlerOptions &handler\_options) (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                        [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [inline]{.mlabel}
  **uri\_path**() const override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                              [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **WriteResponseBytes**(const char \*data, int64\_t size) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                           [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **WriteResponseString**(absl::string\_view data) override (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                   [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **\~EvHTTPRequest**() (defined in [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el})                                                                       [tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}                     [virtual]{.mlabel}
  **\~ServerRequestInterface**()=default (defined in [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el})                                    [tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}   [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
