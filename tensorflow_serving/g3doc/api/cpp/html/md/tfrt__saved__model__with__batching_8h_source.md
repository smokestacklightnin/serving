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
-   [tensorflow\_serving](dir_bbc8937306723ff096d79d77f4a73363.html){.el}
-   [batching](dir_02baa623061b1c8249c9d45b41261099.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tfrt\_saved\_model\_with\_batching.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2020 Google Inc. All Rights
Reserved.]{.comment}
:::

::: {.line}
[]{#l00002}[ 2]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00003}[ 3]{.lineno} [Licensed under the Apache License, Version 2.0
(the \"License\");]{.comment}
:::

::: {.line}
[]{#l00004}[ 4]{.lineno} [you may not use this file except in compliance
with the License.]{.comment}
:::

::: {.line}
[]{#l00005}[ 5]{.lineno} [You may obtain a copy of the License
at]{.comment}
:::

::: {.line}
[]{#l00006}[ 6]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00007}[ 7]{.lineno} [
http://www.apache.org/licenses/LICENSE-2.0]{.comment}
:::

::: {.line}
[]{#l00008}[ 8]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00009}[ 9]{.lineno} [Unless required by applicable law or agreed to
in writing, software]{.comment}
:::

::: {.line}
[]{#l00010}[ 10]{.lineno} [distributed under the License is distributed
on an \"AS IS\" BASIS,]{.comment}
:::

::: {.line}
[]{#l00011}[ 11]{.lineno} [WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied.]{.comment}
:::

::: {.line}
[]{#l00012}[ 12]{.lineno} [See the License for the specific language
governing permissions and]{.comment}
:::

::: {.line}
[]{#l00013}[ 13]{.lineno} [limitations under the License.]{.comment}
:::

::: {.line}
[]{#l00014}[
14]{.lineno} [==============================================================================\*/]{.comment}
:::

::: {.line}
[]{#l00015}[ 15]{.lineno} 
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [// Batching interface on top of TFRT
SavedModel. Subject to change since TFRT]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// SavedModel API is temporary and
experimental.]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_BATCHING\_TFRT\_SAVED\_MODEL\_WITH\_BATCHING\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_TFRT\_SAVED\_MODEL\_WITH\_BATCHING\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/tfrt/saved\_model/saved\_model.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/batching/batching\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/batching/batching\_session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// The batch scheduler task type used for
SavedModel batching, for use in batch]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// scheduler template parameters,
e.g.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//
BasicBatchScheduler\<SavedModelBatchingTask\>.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [struct ]{.keyword}SavedModelBatchingTask;
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// A function to construct a batch scheduler
for SavedModelBatchingTasks from a]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// process-batch callback.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [using]{.keyword}
SavedModelBatchingSchedulerCreator = std::function\<Status(
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<SavedModelBatchingTask\>\>)\>,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
std::unique\_ptr\<BatchScheduler\<SavedModelBatchingTask\>\> \*)\>;
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// A function name paired with a lambda to
create a batch scheduler for Run()]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// calls matching the function
name.]{.comment}
:::

::: {.line}
[]{#l00045}[
[45](structtensorflow_1_1serving_1_1FuncNameWithBatchingSchedulerCreator.html){.line}]{.lineno} [struct
]{.keyword}[FuncNameWithBatchingSchedulerCreator](structtensorflow_1_1serving_1_1FuncNameWithBatchingSchedulerCreator.html){.code}
{
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  absl::string\_view func\_name;
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  SavedModelBatchingSchedulerCreator
scheduler\_creator;
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} };
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [using]{.keyword}
[SavedModelBatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}
=
[BatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// Creates \`saved\_model\_with\_batching\`
that batches requests per function]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// internally, where the batch scheduler for
each function is created according]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// to
\`func\_name\_with\_batching\_scheduler\_creator\`. \`saved\_model\` is
the]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// underlying core to run inference logic and
must not be null. Upon successful]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// return, \`saved\_model\_with\_batching\`
should be used in the same way as a]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// normal SavedModel. Run() call is still
synchronized, and all the batching]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// logic is transparent to the
caller.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// Also note that the first dimension of all
tensors passed to Run() must be]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// batching dimension.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} Status CreateSavedModelWithBatching(
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [const]{.keyword}
[SavedModelBatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}
&options,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [const]{.keyword}
std::vector\<FuncNameWithBatchingSchedulerCreator\>
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
&func\_name\_with\_batching\_scheduler\_creator,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  std::unique\_ptr\<tfrt::SavedModel\>
saved\_model,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  std::unique\_ptr\<tfrt::SavedModel\>
\*saved\_model\_with\_batching);
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[
[68](structtensorflow_1_1serving_1_1SavedModelBatchingTask.html){.line}]{.lineno} [struct
]{.keyword}[SavedModelBatchingTask](structtensorflow_1_1serving_1_1SavedModelBatchingTask.html){.code}
: [public]{.keyword}
[BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.code}
{
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// For monitoring purpose.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [static]{.keyword} std::string Name() {
[return]{.keywordflow}
[\"tfrt\_saved\_model\_with\_batching\"]{.stringliteral}; }
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  tfrt::HostContext \*host\_context;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  absl::Span\<const Tensor\> tfrt\_inputs;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  std::vector\<Tensor\> \*tfrt\_outputs;
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  tfrt::SavedModel::RunOptions run\_options;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// If fields below are used, this is a
partial task by splitting a large batch]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// task.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  std::vector\<Tensor\> tfrt\_partial\_inputs;
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// Status shared by all partial tasks by
splitting a large batch task. The]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [// original task succedds only if all
partial tasks succeed.]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.code}
\*partial\_status = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} };
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [// The default implementation of]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [//
\`BasicBatchScheduler::Options.split\_input\_task\_func\` if
corresponding batch]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// scheduler for a batching session
sets]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [//
\`BasicBatchScheduler::Options.enable\_large\_batch\_splitting\` to
true.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} Status SplitSavedModelInputTask(
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::unique\_ptr\<SavedModelBatchingTask\>
\*input\_task\_ptr,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [int]{.keywordtype}
open\_batch\_remaining\_slot, [int]{.keywordtype} max\_batch\_size,
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
std::vector\<std::unique\_ptr\<SavedModelBatchingTask\>\>
\*output\_tasks);
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_TFRT\_SAVED\_MODEL\_WITH\_BATCHING\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadSafeStatus_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html)
:::

::: {.ttdef}
**Definition:** threadsafe\_status.h:45
:::
:::

::: {#astructtensorflow_1_1serving_1_1BatchingOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::BatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html)
:::

::: {.ttdef}
**Definition:** batching\_options.h:25
:::
:::

::: {#astructtensorflow_1_1serving_1_1BatchingSessionTask_html .ttc}
::: {.ttname}
[tensorflow::serving::BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html)
:::

::: {.ttdef}
**Definition:** batching\_session.h:167
:::
:::

::: {#astructtensorflow_1_1serving_1_1FuncNameWithBatchingSchedulerCreator_html .ttc}
::: {.ttname}
[tensorflow::serving::FuncNameWithBatchingSchedulerCreator](structtensorflow_1_1serving_1_1FuncNameWithBatchingSchedulerCreator.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_with\_batching.h:45
:::
:::

::: {#astructtensorflow_1_1serving_1_1SavedModelBatchingTask_html .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBatchingTask](structtensorflow_1_1serving_1_1SavedModelBatchingTask.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_with\_batching.h:68
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
