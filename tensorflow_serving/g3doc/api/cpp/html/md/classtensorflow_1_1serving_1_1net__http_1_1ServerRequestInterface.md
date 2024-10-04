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
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::net\_http::ServerRequestInterface Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for
tensorflow::serving::net\_http::ServerRequestInterface:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.el}

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

[]{#a99e6341cf57a054cb8b938b0ca744f95}enum class  

**BodyStatus** { **PENDING** = 0 , **COMPLETE** = 1 , **FAILED** = 2 }

 

[]{#ad3b9246024c81fc53df8f03c3f42ada3}enum class  

**CallbackStatus** { **NOT\_SCHEDULED** = 0 , **SCHEDULED** = 1 }

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

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

 

[]{#afe73612de6dad7898c068141af590720} virtual absl::string\_view 

**uri\_path** () const =0

 

[]{#ab28896c0defe813c8dbbdb1115aa6e52} virtual absl::string\_view 

**http\_method** () const =0

 

[]{#a7386e69b3f3afe5314eb67217c2fc991} virtual void 

**WriteResponseBytes** (const char \*data, int64\_t size)=0

 

[]{#a7c5430f25c8027aa4addf9b2ad1ff30e} virtual void 

**WriteResponseString** (absl::string\_view data)=0

 

[]{#a963c74640d07cb5392eef91368813cdb} virtual std::unique\_ptr\<
char\[\],
[ServerRequestInterface::BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.el}
\> 

**ReadRequestBytes** (int64\_t \*size)=0

 

[]{#ae3a98d79089c651a03da6289e134890f} virtual absl::string\_view 

**GetRequestHeader** (absl::string\_view header) const =0

 

[]{#a89f7e11f96c388a02fd087ac130844ce} virtual std::vector\<
absl::string\_view \> 

**request\_headers** () const =0

 

[]{#a996fa082fe1ea76d81ad935d90994f47} virtual void 

**OverwriteResponseHeader** (absl::string\_view header,
absl::string\_view value)=0

 

[]{#a71f7e44d9a9db13d1cf6be9eaf5aefd6} virtual void 

**AppendResponseHeader** (absl::string\_view header, absl::string\_view
value)=0

 

[]{#a8160444169240317224840eccacfac37} virtual void 

**PartialReplyWithStatus** (HTTPStatusCode status)=0

 

[]{#a1b73a93234a38221484b9d293bd24b48} virtual void 

**PartialReply** ()=0

 

[]{#aadf9595b07c1c102225d67f1cf152a5d} virtual CallbackStatus 

**PartialReplyWithFlushCallback** (std::function\< void()\> callback)=0

 

[]{#abd9dea278abdd8c9e4942469f8173275} virtual BodyStatus 

**response\_body\_status** ()

 

[]{#ae19225bd125fe4f04966b1b7ef3d6160} virtual BodyStatus 

**request\_body\_status** ()

 

[]{#a38679ff777daa9c8815bc580c2fd8ce5} virtual void 

**ReplyWithStatus** (HTTPStatusCode status)=0

 

[]{#a8b4554fa0e0e6633f92943abe2d82bff} virtual void 

**Reply** ()=0

 

[]{#aa429da9ec48052ab8f3bc3b286951e4e} virtual void 

**Abort** ()=0

 

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/util/net\_http/server/public/[server\_request\_interface.h](server__request__interface_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
