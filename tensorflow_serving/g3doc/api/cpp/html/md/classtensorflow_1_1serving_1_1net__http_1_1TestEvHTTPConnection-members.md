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
-   [TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::TestEvHTTPConnection Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el},
including all inherited members.

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------
  **BlockingSendRequest**(const TestClientRequest &request, TestClientResponse \*response) override (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})   [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [virtual]{.mlabel}
  **Connect**(absl::string\_view url) (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                                 [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [static]{.mlabel}
  **Connect**(absl::string\_view host, int port) (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                      [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [static]{.mlabel}
  **ConnectLocal**(int port) (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                                          [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [inline]{.mlabel}[static]{.mlabel}
  **operator=**(const TestEvHTTPConnection &other)=delete (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                             [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         
  **operator=**(const TestHTTPClientInterface &other)=delete (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                    [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   
  **SendRequest**(const TestClientRequest &request, TestClientResponse \*response) override (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})           [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [virtual]{.mlabel}
  **SetExecutor**(std::unique\_ptr\< EventExecutor \> executor) override (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                              [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [virtual]{.mlabel}
  **Terminate**() override (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                                            [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         [virtual]{.mlabel}
  **TestEvHTTPConnection**()=default (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                                  [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         
  **TestEvHTTPConnection**(const TestEvHTTPConnection &other)=delete (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                  [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         
  **TestHTTPClientInterface**(const TestHTTPClientInterface &other)=delete (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                      [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   
  **TestHTTPClientInterface**()=default (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                                         [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [protected]{.mlabel}
  **\~TestEvHTTPConnection**() override (defined in [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el})                                                               [tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}         
  **\~TestHTTPClientInterface**()=default (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                                       [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [virtual]{.mlabel}
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
