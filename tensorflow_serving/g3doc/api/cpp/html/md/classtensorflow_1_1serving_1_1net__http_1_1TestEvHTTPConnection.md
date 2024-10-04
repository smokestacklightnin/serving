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
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::TestEvHTTPConnection Class
Reference[[final]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for
tensorflow::serving::net\_http::TestEvHTTPConnection:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::net\_http::TestEvHTTPConnection:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#af0f6d1a44ae8cde23369bbf67e0a64d8}  

**TestEvHTTPConnection** (const
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
&other)=delete

 

[]{#aaa3298c849c68d9b4d54cea31493a72b}
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
& 

**operator=** (const
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
&other)=delete

 

[]{#aa6514c0457bcf28c33f9bc074a4d2833} void 

**Terminate** () override

 

[]{#a8fd460b64308127e543562b78652f080} bool 

**BlockingSendRequest** (const
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.el}
&request,
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.el}
\*response) override

 

[]{#a41357800736a2bc4516cb18b9eb4e55e} bool 

**SendRequest** (const
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.el}
&request,
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.el}
\*response) override

 

[]{#a117a8f7ddc785ee7832a8a366ef5cc6c} void 

**SetExecutor** (std::unique\_ptr\<
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.el}
\> executor) override

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}

[]{#ae49eed1257f6090570e4fe8945a6e5f5}  

**TestHTTPClientInterface** (const
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}
&other)=delete

 

[]{#ab2475abd13f1dd54458ddcac63776314}
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}
& 

**operator=** (const
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.el}
&other)=delete

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a474285be99fdd4cf595f91da3fbc729e} static std::unique\_ptr\<
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
\> 

**Connect** (absl::string\_view url)

 

[]{#a2710dfe62103f842758ded371631214b} static std::unique\_ptr\<
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
\> 

**Connect** (absl::string\_view host, int port)

 

[]{#a81445984f79a709567d7981d05d7a347} static std::unique\_ptr\<
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.el}
\> 

**ConnectLocal** (int port)

 

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/util/net\_http/client/test\_client/internal/[evhttp\_connection.h](evhttp__connection_8h_source.html){.el}
-   tensorflow\_serving/util/net\_http/client/test\_client/internal/evhttp\_connection.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
