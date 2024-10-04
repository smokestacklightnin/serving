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
-   [HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::HTTPServerInterface Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el},
including all inherited members.

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- -------------------------
  **HTTPServerInterface**(const HTTPServerInterface &other)=delete (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                     [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   
  **HTTPServerInterface**()=default (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                    [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [protected]{.mlabel}
  **is\_accepting\_requests**() const =0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                               [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **is\_terminating**() const =0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                       [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **listen\_port**() const =0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                          [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **operator=**(const HTTPServerInterface &other)=delete (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                               [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   
  **RegisterRequestDispatcher**(RequestDispatcher dispatcher, const RequestHandlerOptions &options)=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                  [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **RegisterRequestHandler**(absl::string\_view uri, RequestHandler handler, const RequestHandlerOptions &options)=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})   [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **StartAcceptingRequests**()=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                       [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **Terminate**()=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                                    [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **WaitForTermination**()=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                           [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **WaitForTerminationWithTimeout**(absl::Duration timeout)=0 (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                          [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [pure virtual]{.mlabel}
  **\~HTTPServerInterface**()=default (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                                  [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [virtual]{.mlabel}
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- -------------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
