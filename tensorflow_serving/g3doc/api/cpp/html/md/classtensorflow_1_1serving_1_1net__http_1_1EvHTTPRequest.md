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
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::EvHTTPRequest Class
Reference[[final]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::net\_http::EvHTTPRequest:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::net\_http::EvHTTPRequest:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#adb8947627ca8dca836b736e45b7d009d}  

**EvHTTPRequest** (const
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}
&other)=delete

 

[]{#a405bc5482952d8ce4901b2d928259f91}
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}
& 

**operator=** (const
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.el}
&other)=delete

 

[]{#ac415abc071c4d01ac51bf3024aafbed2}  

**EvHTTPRequest** (std::unique\_ptr\<
[ParsedEvRequest](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html){.el}
\> request,
[ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.el}
\*server)

 

[]{#a9cebd921f58f27e9b74a684e347a9049} absl::string\_view 

**uri\_path** () const override

 

[]{#a2012dfc89986f7ec987489ceadf9f348} absl::string\_view 

**http\_method** () const override

 

[]{#a7a428c079d77b5417d901b5764de7337} void 

**WriteResponseBytes** (const char \*data, int64\_t size) override

 

[]{#ad6c8bd95d250a1ae8c13ecb6ee56522a} void 

**WriteResponseString** (absl::string\_view data) override

 

[]{#ac206741a825d105757bd02a30417c5e7} std::unique\_ptr\< char\[\],
[ServerRequestInterface::BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.el}
\> 

**ReadRequestBytes** (int64\_t \*size) override

 

[]{#a9b4837c2a7fdf61502747f4010990119} absl::string\_view 

**GetRequestHeader** (absl::string\_view header) const override

 

[]{#a7345deacbcb4d685dc6617e7f0d6d93f} std::vector\< absl::string\_view
\> 

**request\_headers** () const override

 

[]{#af69857b53b2e17c8124ede8ee1255d71} void 

**OverwriteResponseHeader** (absl::string\_view header,
absl::string\_view value) override

 

[]{#a6b6c1f21b8e466f336184f0a54d4a1c4} void 

**AppendResponseHeader** (absl::string\_view header, absl::string\_view
value) override

 

[]{#a46a106a783fc5530b6dc23b4d166595a} void 

**PartialReplyWithStatus** (HTTPStatusCode status) override

 

[]{#a5c822af861049d5c8c66723ea7e33cb0} void 

**PartialReply** () override

 

[]{#ac8f335609b185cd064394074e04f6baf} CallbackStatus 

**PartialReplyWithFlushCallback** (std::function\< void()\> callback)
override

 

[]{#aa525ec2cd5b25678f07bdc12a77a1440} void 

**ReplyWithStatus** (HTTPStatusCode status) override

 

[]{#a2d16e56f7e4b49cbb915fcd1e2b68c09} void 

**Reply** () override

 

[]{#a2f42750b0a4062061b1c76dac164aa2a} void 

**Abort** () override

 

[]{#a027f3459fd1d3f5b935e7a211d0834e0} bool 

**Initialize** ()

 

[]{#af75cbe925296ed9bbac4cb7f78fc6f1d} void 

**SetHandlerOptions** (const
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.el}
&handler\_options)

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}

[]{#a3a5ad543b7d882b97e28c7e151de0bbb}  

**ServerRequestInterface** (const
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}
&other)=delete

 

[]{#a6f512b015cc9668b9c1836fb6c992e68}
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}
& 

**operator=** (const
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}
&other)=delete

 

[]{#abd9dea278abdd8c9e4942469f8173275} virtual BodyStatus 

**response\_body\_status** ()

 

[]{#ae19225bd125fe4f04966b1b7ef3d6160} virtual BodyStatus 

**request\_body\_status** ()

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.el}

[]{#a99e6341cf57a054cb8b938b0ca744f95}enum class  

**BodyStatus** { **PENDING** = 0 , **COMPLETE** = 1 , **FAILED** = 2 }

 

[]{#ad3b9246024c81fc53df8f03c3f42ada3}enum class  

**CallbackStatus** { **NOT\_SCHEDULED** = 0 , **SCHEDULED** = 1 }

 

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/util/net\_http/server/internal/[evhttp\_request.h](evhttp__request_8h_source.html){.el}
-   tensorflow\_serving/util/net\_http/server/internal/evhttp\_request.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
