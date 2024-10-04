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
-   [SavedModelBatchingTask](structtensorflow_1_1serving_1_1SavedModelBatchingTask.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Static Public Member Functions](#pub-static-methods) \| [Public
Attributes](#pub-attribs) \| [List of all
members](structtensorflow_1_1serving_1_1SavedModelBatchingTask-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::SavedModelBatchingTask Struct Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::SavedModelBatchingTask:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](structtensorflow_1_1serving_1_1SavedModelBatchingTask__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::SavedModelBatchingTask:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](structtensorflow_1_1serving_1_1SavedModelBatchingTask__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------
:::

[]{#a60c23eb53ef4ab7a30a69602d0d10ea9} static std::string 

**Name** ()

 

![-](closed.png) Static Public Member Functions inherited from
[tensorflow::serving::BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.el}

[]{#a373a9cb0a3901cda84d8c9c4d894ecad} static std::string 

**Name** ()

 

[]{#pub-attribs} Public Attributes {#public-attributes .groupheader}
----------------------------------

[]{#a79ac19875c5f78cd1d7e0fd63fa244da} tfrt::HostContext \* 

**host\_context**

 

[]{#a5087e35e5ed7939780218b382f4f8167} absl::Span\< const Tensor \> 

**tfrt\_inputs**

 

[]{#a7fb4fee88d15c2ff7a855a87fd423576} std::vector\< Tensor \> \* 

**tfrt\_outputs**

 

[]{#ab03be8a4e4e48d07330973dcc058af6b} tfrt::SavedModel::RunOptions 

**run\_options**

 

[]{#ae0228a6efe304eb381fc9fef01daa916} std::vector\< Tensor \> 

**tfrt\_partial\_inputs**

 

[]{#a4e5d503873a12620500b3a4bc2a804bf}
[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.el}
\* 

**partial\_status** = nullptr

 

![-](closed.png) Public Attributes inherited from
[tensorflow::serving::BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.el}

[]{#a414c3a8ae8a5a7c38b6aac190361e7dd} uint64\_t 

**enqueue\_time\_micros**

 

[]{#a37211125ccaca7d7d8c1f5a7f78ee956} RunOptions 

**run\_options**

 

[]{#a63740c858ebe283a81afa731b4d5a653} size\_t 

**zeroth\_dim\_size**

 

[]{#a9a3738dcbd22b3f6603d99b2a898cff3} const std::vector\< std::pair\<
string, Tensor \> \> \* 

**inputs**

 

[]{#a91fb78909799f64d611280875f5f790d} const std::vector\< string \> \* 

**output\_tensor\_names**

 

[]{#a3227a00c9984efa3475709e11a303728} Notification \* 

**done**

 

[]{#a15a28436e5788a85fb5bbfef0355bf5c} Status \* 

**status**

 

[]{#a8860c4080caef1a3c410c9e13f711ebd} std::vector\< Tensor \> \* 

**outputs**

 

[]{#aa3a07ee4d98dd35bb77a95dc46eee437} RunMetadata \* 

**run\_metadata**

 

[]{#a8908744c1d1451787e9670d50d825bc7} absl::optional\<
thread::ThreadPoolOptions \> 

**thread\_pool\_options**

 

[]{#abfc7a564550dc4698b81bf3fe69483b0} bool 

**is\_partial** = false

 

[]{#ad3eabcdb4217501db137dad2c76359b8} std::unique\_ptr\< std::vector\<
std::pair\< string, Tensor \> \> \> 

**owned\_split\_inputs**

 

[]{#a9cdcfd844f18c87833ea44b302f3c685} int 

**split\_index** = 0

 

[]{#abf4760aaa56b44d57686a696634860bf} std::function\< void()\> 

**done\_callback**

 

[]{#abe23aaf6416ae82426ed5358c0b1f460} std::shared\_ptr\< TensorMatrix
\> 

**shared\_outputs**

 

[]{#a5322dc380b7173f4424f3802e8a4f09f} std::shared\_ptr\<
[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.el}
\> 

**thread\_safe\_status**

 

[]{#adffabec37d4b342ecce98c6d71513c6f} std::shared\_ptr\< std::vector\<
RunMetadata \> \> 

**split\_run\_metadatas**

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.el}

[]{#a6fdbc9ffcee7d8e5b006b69caa9cf8a5} typedef std::vector\<
std::vector\< Tensor \> \> 

**TensorMatrix**

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.el}

[]{#a91ff8e877221b79a13755b4566e6dd3d} size\_t 

**size** () const override

 

------------------------------------------------------------------------

The documentation for this struct was generated from the following file:

-   tensorflow\_serving/batching/[tfrt\_saved\_model\_with\_batching.h](tfrt__saved__model__with__batching_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
