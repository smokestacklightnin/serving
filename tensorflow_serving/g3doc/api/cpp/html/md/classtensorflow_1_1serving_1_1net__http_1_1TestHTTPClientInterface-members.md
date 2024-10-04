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
-   [TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::TestHTTPClientInterface Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- -------------------------
  **BlockingSendRequest**(const TestClientRequest &request, TestClientResponse \*response)=0 (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})   [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [pure virtual]{.mlabel}
  **operator=**(const TestHTTPClientInterface &other)=delete (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                   [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   
  **SendRequest**(const TestClientRequest &request, TestClientResponse \*response)=0 (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})           [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [pure virtual]{.mlabel}
  **SetExecutor**(std::unique\_ptr\< EventExecutor \> executor)=0 (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                              [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [pure virtual]{.mlabel}
  **Terminate**()=0 (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                                                            [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [pure virtual]{.mlabel}
  **TestHTTPClientInterface**(const TestHTTPClientInterface &other)=delete (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                     [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   
  **TestHTTPClientInterface**()=default (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                                        [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [protected]{.mlabel}
  **\~TestHTTPClientInterface**()=default (defined in [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el})                                                      [tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}   [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
