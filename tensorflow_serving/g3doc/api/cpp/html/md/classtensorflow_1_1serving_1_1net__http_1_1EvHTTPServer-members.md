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
-   [EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::EvHTTPServer Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el},
including all inherited members.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- ----------------------
  **DecOps**() override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                                       [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **EventLoopSchedule**(std::function\< void()\> fn) override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                 [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **EvHTTPServer**(const EvHTTPServer &other)=delete (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                          [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 
  **EvHTTPServer**(std::unique\_ptr\< ServerOptions \> options) (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                               [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [explicit]{.mlabel}
  **HTTPServerInterface**(const HTTPServerInterface &other)=delete (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                              [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   
  **HTTPServerInterface**()=default (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                             [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [protected]{.mlabel}
  **IncOps**() override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                                       [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **Initialize**() (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                                            [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 
  **is\_accepting\_requests**() const override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **is\_terminating**() const override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                        [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **listen\_port**() const override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                           [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **operator=**(const EvHTTPServer &other)=delete (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                             [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 
  **operator=**(const HTTPServerInterface &other)=delete (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                        [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   
  **operator=**(const ServerSupport &other)=delete (defined in [tensorflow::serving::net\_http::ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.el})                                                                          [tensorflow::serving::net\_http::ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.el}               [private]{.mlabel}
  **RegisterRequestDispatcher**(RequestDispatcher dispatcher, const RequestHandlerOptions &options) override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                  [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **RegisterRequestHandler**(absl::string\_view uri, RequestHandler handler, const RequestHandlerOptions &options) override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})   [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **StartAcceptingRequests**() override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                       [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **Terminate**() override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                                    [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **WaitForTermination**() override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                           [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **WaitForTerminationWithTimeout**(absl::Duration timeout) override (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                          [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **\~EvHTTPServer**() (defined in [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el})                                                                                                        [tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.el}                 [virtual]{.mlabel}
  **\~HTTPServerInterface**()=default (defined in [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el})                                                                           [tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.el}   [virtual]{.mlabel}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- ----------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
