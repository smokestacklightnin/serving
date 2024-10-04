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
-   [TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1TfLiteSession-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::TfLiteSession Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::TfLiteSession:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1TfLiteSession__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::TfLiteSession:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1TfLiteSession__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#af56c4d888c6d9b14fa7f93c3ebf2aec9} Status 

**Run** (const std::vector\< std::pair\< string, Tensor \>\> &inputs,
const std::vector\< string \> &output\_tensor\_names, const
std::vector\< string \> &target\_node\_names, std::vector\< Tensor \>
\*outputs) override

 

[]{#ad2a1c5664ab495ba320e2517b4d09ff2} Status 

**Run** (const RunOptions &run\_options, const std::vector\< std::pair\<
string, Tensor \>\> &inputs, const std::vector\< string \>
&output\_tensor\_names, const std::vector\< string \>
&target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata
\*run\_metadata) override

 

[]{#a5fa1a7c147c933e0316a54789cc513d3} Status 

**Run** (const RunOptions &run\_options, const std::vector\< std::pair\<
string, Tensor \>\> &inputs, const std::vector\< string \>
&output\_tensor\_names, const std::vector\< string \>
&target\_node\_names, std::vector\< Tensor \> \*outputs, RunMetadata
\*run\_metadata, const thread::ThreadPoolOptions &thread\_pool\_options)
override

 

[]{#ad869ad828216829a1eb6dfd95b8ddbff} Status 

**ListDevices** (std::vector\< DeviceAttributes \> \*response) override

 

[]{#aac1155c582aa38320c71b822fa3bad7c} Status 

**SetScheduler** (const SchedulerCreator &scheduler\_creator, const
BasicBatchScheduler\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>::Options &options)

 

[]{#aabe9a6b7e0aa93a3eb265f098f5ac2b8} BasicBatchScheduler\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>::Options 

**GetSchedulerOptions** ()

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.el}

[]{#a9bd35520578059d4c2e800fe35af269d} Status 

**Create** (const GraphDef &graph) final

 

[]{#a95aac4bd40b4d9c28df32e914cbce0df} Status 

**Extend** (const GraphDef &graph) final

 

[]{#a4033e3f5d34c27241effd523773aa556} Status 

**Close** () final

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a15f669ebbee48bd099d5ef6cf848c75c} static Status 

**Create** (string &&buffer, const SessionOptions &options, int
num\_pools, int num\_interpreters\_per\_pool, std::unique\_ptr\<
[TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.el}
\> \*tflite\_session, ::google::protobuf::Map\< string, SignatureDef \>
\*signatures)

 

[]{#a691ec11977b3a1b5cb325ca2f771f9eb} static Status 

**CreateDefaultBasicBatchScheduler** (const BasicBatchScheduler\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>::Options &options, std::function\< void(std::unique\_ptr\< Batch\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>\>)\> process\_batch\_callback, std::unique\_ptr\<
BasicBatchScheduler\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>\> \*batch\_scheduler)

 

[]{#ae296cc32dbee906cc35d78e5ebf280ff} static Status 

**SplitTfLiteInputTask** (std::unique\_ptr\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\> \*input\_task\_ptr, int open\_batch\_remaining\_slot, int
max\_batch\_size, std::vector\< std::unique\_ptr\<
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.el}
\>\> \*output\_tasks)

 

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/servables/tensorflow/[tflite\_session.h](tflite__session_8h_source.html){.el}
-   tensorflow\_serving/servables/tensorflow/tflite\_session.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
