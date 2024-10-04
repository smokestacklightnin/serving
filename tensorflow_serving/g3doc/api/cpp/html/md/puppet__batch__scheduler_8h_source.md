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
-   [test\_util](dir_d92abc2f6fc99fb526a3ec2b7e72fba9.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
puppet\_batch\_scheduler.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2016 Google Inc. All Rights
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
[]{#l00016}[ 16]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_BATCHING\_TEST\_UTIL\_PUPPET\_BATCH\_SCHEDULER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_TEST\_UTIL\_PUPPET\_BATCH\_SCHEDULER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<stddef.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<limits\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<queue\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/batch\_scheduler.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// A BatchScheduler implementation that
enqueues tasks, and when requested via]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// a method call places them into a batch and
runs the batch. (It doesn\'t have]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// any threads or enforce any maximum batch
size or timeout.)]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// This scheduler is useful for testing
classes whose implementation relies on]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// a batch scheduler. The class under testing
can be configured to use a]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// PuppetBatchScheduler, in lieu of a real
one, for the purpose of the test.]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00041}[
[41](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.line}]{.lineno} [class
]{.keyword}[PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.code}
: [public]{.keyword} BatchScheduler\<TaskType\> {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [explicit]{.keyword}
[PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.code}(
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  process\_batch\_callback);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
\~[PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  Status
Schedule(std::unique\_ptr\<TaskType\>\* task) [override]{.keyword};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [size\_t]{.keywordtype} NumEnqueuedTasks()
[const override]{.keyword};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// This schedule has unbounded capacity, so
this method returns the maximum]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// size\_t value to simulate
infinity.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [size\_t]{.keywordtype} SchedulingCapacity()
[const override]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// Processes up to \'num\_tasks\' enqueued
tasks, in FIFO order.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [void]{.keywordtype}
ProcessTasks([int]{.keywordtype} num\_tasks);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// Processes all enqueued tasks.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [void]{.keywordtype} ProcessAllTasks();
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [size\_t]{.keywordtype} max\_task\_size()[
const override ]{.keyword}{
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [return]{.keywordflow}
std::numeric\_limits\<size\_t\>::max();
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  }
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
std::function\<void(std::unique\_ptr\<Batch\<TaskType\>\>)\>
process\_batch\_callback\_;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// Tasks submitted to the scheduler.
Processed in FIFO order.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  std::queue\<std::unique\_ptr\<TaskType\>\>
queue\_;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.code});
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} };
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00079}[
79]{.lineno} [PuppetBatchScheduler\<TaskType\>::PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html){.code}(
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  process\_batch\_callback)
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  :
process\_batch\_callback\_(process\_batch\_callback) {}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} Status
PuppetBatchScheduler\<TaskType\>::Schedule(
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  std::unique\_ptr\<TaskType\>\* task) {
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  queue\_.push(std::move(\*task));
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [size\_t]{.keywordtype}
PuppetBatchScheduler\<TaskType\>::NumEnqueuedTasks()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [return]{.keywordflow} queue\_.size();
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [size\_t]{.keywordtype}
PuppetBatchScheduler\<TaskType\>::SchedulingCapacity()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [return]{.keywordflow}
std::numeric\_limits\<size\_t\>::max();
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} }
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [void]{.keywordtype}
PuppetBatchScheduler\<TaskType\>::ProcessTasks([int]{.keywordtype}
num\_tasks) {
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [if]{.keywordflow} (queue\_.empty()) {
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  }
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [auto]{.keyword} batch =
std::unique\_ptr\<Batch\<TaskType\>\>([new]{.keyword}
Batch\<TaskType\>);
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [while]{.keywordflow} (batch-\>num\_tasks()
\< num\_tasks && !queue\_.empty()) {
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  batch-\>AddTask(std::move(queue\_.front()));
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  queue\_.pop();
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  }
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  batch-\>Close();
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
process\_batch\_callback\_(std::move(batch));
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} }
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [void]{.keywordtype}
PuppetBatchScheduler\<TaskType\>::ProcessAllTasks() {
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  ProcessTasks(queue\_.size());
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_TEST\_UTIL\_PUPPET\_BATCH\_SCHEDULER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::PuppetBatchScheduler](classtensorflow_1_1serving_1_1test__util_1_1PuppetBatchScheduler.html)
:::

::: {.ttdef}
**Definition:** puppet\_batch\_scheduler.h:41
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
