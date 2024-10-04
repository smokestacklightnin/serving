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
streaming\_batch\_scheduler.h
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
TENSORFLOW\_SERVING\_BATCHING\_STREAMING\_BATCH\_SCHEDULER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_STREAMING\_BATCH\_SCHEDULER\_H\_]{.preprocessor}
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
[]{#l00022}[ 22]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/core/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/lib/core/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/batching/batch\_scheduler\_retrier.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [class ]{.keyword}SingleTaskScheduler;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// A BatchScheduler implementation geared
toward handling a single request type]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// running on a specific set of hardware
resources. A typical scenario is one in]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// which all requests invoke the same
machine-learned model on one GPU. The]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// scheduler streams requests (tasks) to the
batch thread while a given batch]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// is still filling up, giving the option to
process them in a streaming fashion]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// in the request thread and/or the batch
thread.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// PARAMETERS AND BEHAVIOR:]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// StreamingBatchScheduler is parameterized
by a maximum batch size and timeout.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// It constructs batches one at a time,
stopping when one of these conditions]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// occurs:]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// (a) the next task would cause the batch to
exceed the size target;]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// (b) waiting for more tasks to be added
would exceed the timeout.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// Batches are processed in a fixed-size
thread pool. When a new batch is]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// started it is immediately assigned to a
thread while it is being filled with]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// tasks. The process-batch callback running
in the thread has the option to]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// process the tasks in a \"streaming\"
fashion as they arrive. Eventually, once]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// the batch size or timeout has been
reached, the batch gets closed and the]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// callback should finish processing it and
exit.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// StreamingBatchScheduler does not enqueue
tasks if the threads are all busy.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// Every task is either immediately added to
a batch that is being serviced by]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// an active thread, or rejected with an
UNAVAILABLE error (the client may]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// subsequently retry submitting the
task).]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// RECOMMENDED USE-CASES:]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [// Please see the RECOMMENDED USE-CASES
section of BasicBatchScheduler\'s class]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [// documentation. The same applies
here.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [// EXAMPLE USE-CASE FLOW:]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// For such use-cases, request processing via
StreamingBatchScheduler generally]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [// follows this flow (given for illustration;
variations are possible):]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [// 1. Optionally perform some pre-processing
on each request in the request]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [// threads.]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [// 2. Route the requests to the batch
scheduler, as batching::Task objects.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// (Since all requests are of the same type
and are not versioned, the]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} [// scheduler is free to group them into
batches arbitrarily.)]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// 3. Optionally perform some pre-processing
on the requests in the batching]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// thread as a given batch fills up, perhaps
including starting to merge the]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// requests into their single batched
representation.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [// 4. Wait for the batch to be closed, e.g.
by calling WaitUntilClosed(). (Note]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// that the batch will become closed
automatically, based on reaching either]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// the maximum batch size or the
timeout.)]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [// 5. Merge the requests into a single
batched representation B.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [// 6. Obtain handles to the servable(s)
needed to process B. The simplest]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [// approach is to obtain the latest version
of each servable. Alternatively,]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// if cross-servable consistency is required
(e.g. the vocabulary lookup]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// table\'s version number must match that
of the tensorflow session),]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// identify an appropriate version number
and obtain the servable handles]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [// accordingly.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} [// 7. Process B using the obtained servable
handles, and split the result into]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [// individual per-request units.]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// 8. Perform any post-processing in the
batch thread and/or request thread.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00113}[
[113](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.line}]{.lineno} [class
]{.keyword}[StreamingBatchScheduler](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.code}
: [public]{.keyword} BatchScheduler\<TaskType\> {
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// TODO(b/25089730): Tune defaults based on
best practices as they develop.]{.comment}
:::

::: {.line}
[]{#l00116}[
[116](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  constexpr
[Options](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options.html){.code}()
{}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// The maximum size of each
batch.]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// The scheduler may form batches of any
size between 1 and this number]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// (inclusive). If there is a need to
quantize the batch sizes, i.e. only]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [// submit batches whose size is in a small
set of allowed sizes, that can be]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// done by adding padding in the
process-batch callback.]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [size\_t]{.keywordtype} max\_batch\_size =
1000;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// The maximum amount of time a task can
sit in a batch before the scheduler]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [// closes the batch, in
microseconds.]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [// Setting this value to 0 will \*not\*
result in the behavior of processing]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// a batch as soon as a thread becomes
available. Instead, it will cause]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// each batch to contain just a single
item, essentially disabling batching.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [// StreamingBatchScheduler is not the right
vehicle for achieving the]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// aforementioned behavior.]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// A negative value means that no timeout
will be enforced. This setting is]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// useful in some test code.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  int64\_t batch\_timeout\_micros = 0;
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// The name to use for the pool of batch
threads.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [string]{.keywordtype} thread\_pool\_name =
[\"batch\_threads\"]{.stringliteral};
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// The number of threads to use to process
batches.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// Must be \>= 1, and should be tuned
carefully.]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [int]{.keywordtype} num\_batch\_threads =
port::MaxParallelism();
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// The following options are typically only
overridden by test code.]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// The environment to use.]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  Env\* env = Env::Default();
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// How long SingleTaskScheduler should wait
if there are no scheduled tasks,]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [// in microseconds.]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  uint64\_t no\_tasks\_wait\_time\_micros =
1000; [// 1 millisecond]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  };
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [static]{.keyword} Status Create(
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options.html){.code}&
options,
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  process\_batch\_callback,
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
std::unique\_ptr\<[StreamingBatchScheduler\<TaskType\>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.code}\>\*
scheduler);
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
\~[StreamingBatchScheduler](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  Status
Schedule(std::unique\_ptr\<TaskType\>\* task) [override]{.keyword};
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [// StreamingBatchScheduler never enqueues
tasks, as discussed above.]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [size\_t]{.keywordtype} NumEnqueuedTasks()[
const override ]{.keyword}{ [return]{.keywordflow} 0; }
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// Scheduling capacity is based purely on
threads that can accept tasks]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [// immediately (there is no
queueing).]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [size\_t]{.keywordtype} SchedulingCapacity()
[const override]{.keyword};
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} 
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [size\_t]{.keywordtype} max\_task\_size()[
const override ]{.keyword}{ [return]{.keywordflow}
options\_.max\_batch\_size; }
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} 
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  StreamingBatchScheduler([const]{.keyword}
Options& options,
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  process\_batch\_callback);
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [// Determines whether it is legal to add
\'task\' to \'batch\'.]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [bool]{.keywordtype}
TaskFitsInBatch([const]{.keyword} TaskType\* task,
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [const]{.keyword} Batch\<TaskType\>\* batch)
[const]{.keyword};
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// Closes \'open\_batch\_\' (unless it
equals nullptr), and replaces it with a]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [// fresh open batch. Schedules the new
batch on \'batch\_threads\_\'.]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [void]{.keywordtype} StartNewBatch()
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [// Takes a snapshot of
\'open\_batch\_num\_\', and schedules an event with]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// \'batch\_closer\_\' to close it at time
\'close\_time\_micros\' if it is still open]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// at that time.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [void]{.keywordtype}
ScheduleCloseOfCurrentOpenBatch(uint64\_t close\_time\_micros)
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  const Options options\_;
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} 
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// A callback invoked to processes a batch
of work units. Always invoked from]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [// a batch thread.]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
process\_batch\_callback\_;
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} 
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [// A pool of
\'options\_.num\_batch\_threads\' batch threads.]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  std::unique\_ptr\<thread::ThreadPool\>
batch\_threads\_;
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} 
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// A mutex protecting \'open\_batch\_\' and
associated metadata.]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  mutable mutex mu\_;
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} 
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [// The batch that is currently open and
into which new tasks can be added.]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [// Not owned here; owned by the batch
thread pool.]{.comment}
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  Batch\<TaskType\>\* open\_batch\_
TF\_GUARDED\_BY(mu\_) = [nullptr]{.keywordtype};
:::

::: {.line}
[]{#l00209}[ 209]{.lineno} 
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [// The sequence number of
\'open\_batch\_\'. Incremented each time \'open\_batch\_\']{.comment}
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [// is assigned to a new (non-null) batch
object.]{.comment}
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  int64\_t open\_batch\_num\_
TF\_GUARDED\_BY(mu\_) = 0;
:::

::: {.line}
[]{#l00213}[ 213]{.lineno} 
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [// The number of batches \"in progress\",
i.e. batches that have been started]{.comment}
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [// but for which the process-batch callback
hasn\'t finished. Note that this]{.comment}
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  [// counter is somewhat conservative (i.e.
might be an overestimate), because]{.comment}
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// it gets decremented after the callback
finishes and there could be races.]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [int]{.keywordtype}
num\_batches\_in\_progress\_ TF\_GUARDED\_BY(mu\_) = 0;
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} 
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  [// A background task we use to schedule
batches to close when they hit their]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  [// timeout.]{.comment}
:::

::: {.line}
[]{#l00222}[ 222]{.lineno} 
std::unique\_ptr\<internal::SingleTaskScheduler\> batch\_closer\_
:::

::: {.line}
[]{#l00223}[ 223]{.lineno}  TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} 
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN(StreamingBatchScheduler);
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} };
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno} [// Constructs a StreamingBatchScheduler
wrapped with a retrier, for convenience.]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} template \<typename TaskType\>
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} Status CreateRetryingStreamingBatchScheduler(
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  const typename
StreamingBatchScheduler\<TaskType\>::Options& schedule\_options,
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  const typename
BatchSchedulerRetrier\<TaskType\>::Options& retry\_options,
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  process\_batch\_callback,
:::

::: {.line}
[]{#l00235}[ 235]{.lineno} 
std::unique\_ptr\<BatchScheduler\<TaskType\>\>\* scheduler);
:::

::: {.line}
[]{#l00236}[ 236]{.lineno} 
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00239}[ 239]{.lineno} 
:::

::: {.line}
[]{#l00240}[ 240]{.lineno} namespace internal {
:::

::: {.line}
[]{#l00241}[ 241]{.lineno} 
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} [// A way to defer a computation until a
specific time in the future.]{.comment}
:::

::: {.line}
[]{#l00243}[ 243]{.lineno} [// Spawns a background thread that sleeps
and then runs the computation.]{.comment}
:::

::: {.line}
[]{#l00244}[ 244]{.lineno} [// While the computation is waiting to run,
the caller may update the time and/]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno} [// or computation that gets run. The new
update supercedes the old one.]{.comment}
:::

::: {.line}
[]{#l00246}[
[246](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html){.line}]{.lineno} [class
]{.keyword}[SingleTaskScheduler](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html){.code}
{
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00248}[ 248]{.lineno} 
[SingleTaskScheduler](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html){.code}(Env\*
env, [string]{.keywordtype} thread\_name,
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  uint64\_t no\_tasks\_wait\_time\_micros);
:::

::: {.line}
[]{#l00250}[ 250]{.lineno} 
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  [// Blocks until the currently-set closure
(if any) runs.]{.comment}
:::

::: {.line}
[]{#l00252}[ 252]{.lineno} 
\~[SingleTaskScheduler](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html){.code}();
:::

::: {.line}
[]{#l00253}[ 253]{.lineno} 
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  [// Schedules \'closure\' to run at time
\'time\_micros\' (in env\_ time units). May]{.comment}
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  [// be called zero or more times. Each call
supercedes any prior calls, and]{.comment}
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  [// cancels any closures provided in them
(if they haven\'t already been run).]{.comment}
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00258}[ 258]{.lineno}  [// IMPORTANT: \'time\_micros\' must be
monotonically non-decreasing across calls.]{.comment}
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [void]{.keywordtype} Schedule(uint64\_t
time\_micros, std::function\<[void]{.keywordtype}()\> closure);
:::

::: {.line}
[]{#l00260}[ 260]{.lineno} 
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00262}[ 262]{.lineno}  [// The code executed in \'thread\_\'. Looks
for updated tasks, and executes them]{.comment}
:::

::: {.line}
[]{#l00263}[ 263]{.lineno}  [// by sleeping for the requisite time and
then (if no intervening tasks have]{.comment}
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  [// come in) invoking the callback. Loops
until \'stop\_\' has been notified.]{.comment}
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  [void]{.keywordtype} ThreadLogic();
:::

::: {.line}
[]{#l00266}[ 266]{.lineno} 
:::

::: {.line}
[]{#l00267}[ 267]{.lineno}  [// The environment to use.]{.comment}
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  Env\* env\_;
:::

::: {.line}
[]{#l00269}[ 269]{.lineno} 
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  [mutable]{.keyword} mutex mu\_;
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} 
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  [// The arguments to Schedule().]{.comment}
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [struct ]{.keyword}Task {
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  uint64\_t time\_micros;
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  std::function\<void()\> closure;
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  };
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  [// A newly-scheduled task hasn\'t yet been
picked up by \'thread\_\'.]{.comment}
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  absl::optional\<Task\> updated\_task\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00280}[ 280]{.lineno} 
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  [// The time parameter passed in the most
recent Schedule() invocation.]{.comment}
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  [// Used to enforce monotonicity.]{.comment}
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  uint64\_t last\_task\_time\_ = 0;
:::

::: {.line}
[]{#l00284}[ 284]{.lineno} 
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [// A notification for stopping the thread,
during destruction.]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  Notification stop\_;
:::

::: {.line}
[]{#l00287}[ 287]{.lineno} 
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [// The name of \'thread\_\'.]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  [const]{.keyword} [string]{.keywordtype}
thread\_name\_;
:::

::: {.line}
[]{#l00290}[ 290]{.lineno} 
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  [// A background thread that runs closures
supplied via Schedule().]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  std::unique\_ptr\<Thread\> thread\_;
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} 
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  [// How long to wait if there are no
scheduled tasks, in microseconds.]{.comment}
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  [const]{.keyword} uint64\_t
no\_tasks\_wait\_time\_micros\_;
:::

::: {.line}
[]{#l00296}[ 296]{.lineno} 
:::

::: {.line}
[]{#l00297}[ 297]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([SingleTaskScheduler](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html){.code});
:::

::: {.line}
[]{#l00298}[ 298]{.lineno} };
:::

::: {.line}
[]{#l00299}[ 299]{.lineno} 
:::

::: {.line}
[]{#l00300}[ 300]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00301}[ 301]{.lineno} 
:::

::: {.line}
[]{#l00302}[ 302]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00303}[ 303]{.lineno} Status
[StreamingBatchScheduler\<TaskType\>::Create](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.code}(
:::

::: {.line}
[]{#l00304}[ 304]{.lineno}  [const]{.keyword} Options& options,
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00306}[ 306]{.lineno}  process\_batch\_callback,
:::

::: {.line}
[]{#l00307}[ 307]{.lineno} 
std::unique\_ptr\<[StreamingBatchScheduler\<TaskType\>](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html){.code}\>\*
scheduler) {
:::

::: {.line}
[]{#l00308}[ 308]{.lineno}  [if]{.keywordflow} (options.max\_batch\_size
\<= 0) {
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"max\_batch\_size must be positive; was
\"]{.stringliteral},
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  options.max\_batch\_size);
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  }
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [if]{.keywordflow}
(options.num\_batch\_threads \<= 0) {
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"num\_batch\_threads must be positive; was
\"]{.stringliteral},
:::

::: {.line}
[]{#l00314}[ 314]{.lineno}  options.num\_batch\_threads);
:::

::: {.line}
[]{#l00315}[ 315]{.lineno}  }
:::

::: {.line}
[]{#l00316}[ 316]{.lineno}  scheduler-\>reset(
:::

::: {.line}
[]{#l00317}[ 317]{.lineno}  [new]{.keyword}
StreamingBatchScheduler\<TaskType\>(options, process\_batch\_callback));
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00319}[ 319]{.lineno} }
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
:::

::: {.line}
[]{#l00321}[ 321]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00322}[
322]{.lineno} StreamingBatchScheduler\<TaskType\>::\~StreamingBatchScheduler()
{
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  {
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  [if]{.keywordflow} (open\_batch\_ !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00326}[ 326]{.lineno}  open\_batch\_-\>Close();
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  open\_batch\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  ++open\_batch\_num\_;
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  }
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  }
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [// The thread pool destructor will block
until the threads have finished]{.comment}
:::

::: {.line}
[]{#l00332}[ 332]{.lineno}  [// processing the batches.]{.comment}
:::

::: {.line}
[]{#l00333}[ 333]{.lineno}  batch\_threads\_.reset([nullptr]{.keyword});
:::

::: {.line}
[]{#l00334}[ 334]{.lineno} }
:::

::: {.line}
[]{#l00335}[ 335]{.lineno} 
:::

::: {.line}
[]{#l00336}[ 336]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00337}[ 337]{.lineno} Status
StreamingBatchScheduler\<TaskType\>::Schedule(
:::

::: {.line}
[]{#l00338}[ 338]{.lineno}  std::unique\_ptr\<TaskType\>\* task) {
:::

::: {.line}
[]{#l00339}[ 339]{.lineno}  [if]{.keywordflow} ((\*task)-\>size() \>
options\_.max\_batch\_size) {
:::

::: {.line}
[]{#l00340}[ 340]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"Task size \"]{.stringliteral},
(\*task)-\>size(),
:::

::: {.line}
[]{#l00341}[ 341]{.lineno}  [\" is larger than maximum batch size
\"]{.stringliteral},
:::

::: {.line}
[]{#l00342}[ 342]{.lineno}  options\_.max\_batch\_size);
:::

::: {.line}
[]{#l00343}[ 343]{.lineno}  }
:::

::: {.line}
[]{#l00344}[ 344]{.lineno} 
:::

::: {.line}
[]{#l00345}[ 345]{.lineno}  {
:::

::: {.line}
[]{#l00346}[ 346]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00347}[ 347]{.lineno} 
:::

::: {.line}
[]{#l00348}[ 348]{.lineno}  [if]{.keywordflow} (open\_batch\_ ==
[nullptr]{.keyword} \|\| !TaskFitsInBatch(task-\>get(), open\_batch\_))
{
:::

::: {.line}
[]{#l00349}[ 349]{.lineno}  StartNewBatch();
:::

::: {.line}
[]{#l00350}[ 350]{.lineno}  }
:::

::: {.line}
[]{#l00351}[ 351]{.lineno} 
:::

::: {.line}
[]{#l00352}[ 352]{.lineno}  [// Given N threads, if there are N+1
batches then the N+1st batch is empty]{.comment}
:::

::: {.line}
[]{#l00353}[ 353]{.lineno}  [// and is waiting to be assigned a thread.
In that situation we reject new]{.comment}
:::

::: {.line}
[]{#l00354}[ 354]{.lineno}  [// tasks with a transient UNAVAILABLE error
code.]{.comment}
:::

::: {.line}
[]{#l00355}[ 355]{.lineno}  [if]{.keywordflow}
(num\_batches\_in\_progress\_ \> options\_.num\_batch\_threads) {
:::

::: {.line}
[]{#l00356}[ 356]{.lineno}  DCHECK(open\_batch\_-\>empty());
:::

::: {.line}
[]{#l00357}[ 357]{.lineno}  [return]{.keywordflow} errors::Unavailable(
:::

::: {.line}
[]{#l00358}[ 358]{.lineno}  [\"This task would start a fresh batch, but
all batch threads are \"]{.stringliteral}
:::

::: {.line}
[]{#l00359}[ 359]{.lineno}  [\"busy, so at present there is no
processing capacity available for \"]{.stringliteral}
:::

::: {.line}
[]{#l00360}[ 360]{.lineno}  [\"this task\"]{.stringliteral});
:::

::: {.line}
[]{#l00361}[ 361]{.lineno}  }
:::

::: {.line}
[]{#l00362}[ 362]{.lineno} 
:::

::: {.line}
[]{#l00363}[ 363]{.lineno}  [// If we are about to add the first task to
a batch, schedule the batch to]{.comment}
:::

::: {.line}
[]{#l00364}[ 364]{.lineno}  [// be closed after the timeout.]{.comment}
:::

::: {.line}
[]{#l00365}[ 365]{.lineno}  [if]{.keywordflow}
(options\_.batch\_timeout\_micros \> 0 && open\_batch\_-\>empty()) {
:::

::: {.line}
[]{#l00366}[ 366]{.lineno}  [const]{.keyword} uint64\_t batch\_deadline
=
:::

::: {.line}
[]{#l00367}[ 367]{.lineno}  options\_.env-\>NowMicros() +
options\_.batch\_timeout\_micros;
:::

::: {.line}
[]{#l00368}[ 368]{.lineno} 
ScheduleCloseOfCurrentOpenBatch(batch\_deadline);
:::

::: {.line}
[]{#l00369}[ 369]{.lineno}  }
:::

::: {.line}
[]{#l00370}[ 370]{.lineno} 
:::

::: {.line}
[]{#l00371}[ 371]{.lineno}  open\_batch\_-\>AddTask(std::move(\*task));
:::

::: {.line}
[]{#l00372}[ 372]{.lineno} 
:::

::: {.line}
[]{#l00373}[ 373]{.lineno}  [// If we\'ve exactly reached the target
size, we can close this batch now.]{.comment}
:::

::: {.line}
[]{#l00374}[ 374]{.lineno}  [if]{.keywordflow} (open\_batch\_-\>size()
== options\_.max\_batch\_size) {
:::

::: {.line}
[]{#l00375}[ 375]{.lineno}  StartNewBatch();
:::

::: {.line}
[]{#l00376}[ 376]{.lineno}  }
:::

::: {.line}
[]{#l00377}[ 377]{.lineno}  }
:::

::: {.line}
[]{#l00378}[ 378]{.lineno} 
:::

::: {.line}
[]{#l00379}[ 379]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00380}[ 380]{.lineno} }
:::

::: {.line}
[]{#l00381}[ 381]{.lineno} 
:::

::: {.line}
[]{#l00382}[ 382]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00383}[ 383]{.lineno} [size\_t]{.keywordtype}
StreamingBatchScheduler\<TaskType\>::SchedulingCapacity()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00384}[ 384]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00385}[ 385]{.lineno}  [if]{.keywordflow}
(num\_batches\_in\_progress\_ \> options\_.num\_batch\_threads) {
:::

::: {.line}
[]{#l00386}[ 386]{.lineno}  [return]{.keywordflow} 0;
:::

::: {.line}
[]{#l00387}[ 387]{.lineno}  }
:::

::: {.line}
[]{#l00388}[ 388]{.lineno}  [const]{.keyword} [int]{.keywordtype}
num\_idle\_threads =
:::

::: {.line}
[]{#l00389}[ 389]{.lineno}  options\_.num\_batch\_threads -
num\_batches\_in\_progress\_;
:::

::: {.line}
[]{#l00390}[ 390]{.lineno}  [const]{.keyword} [int]{.keywordtype}
open\_batch\_capacity =
:::

::: {.line}
[]{#l00391}[ 391]{.lineno}  open\_batch\_ == [nullptr]{.keyword} ? 0
:::

::: {.line}
[]{#l00392}[ 392]{.lineno}  : options\_.max\_batch\_size -
open\_batch\_-\>size();
:::

::: {.line}
[]{#l00393}[ 393]{.lineno}  [return]{.keywordflow} (num\_idle\_threads
\* options\_.max\_batch\_size) + open\_batch\_capacity;
:::

::: {.line}
[]{#l00394}[ 394]{.lineno} }
:::

::: {.line}
[]{#l00395}[ 395]{.lineno} 
:::

::: {.line}
[]{#l00396}[ 396]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00397}[
397]{.lineno} StreamingBatchScheduler\<TaskType\>::StreamingBatchScheduler(
:::

::: {.line}
[]{#l00398}[ 398]{.lineno}  [const]{.keyword} Options& options,
:::

::: {.line}
[]{#l00399}[ 399]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00400}[ 400]{.lineno}  process\_batch\_callback)
:::

::: {.line}
[]{#l00401}[ 401]{.lineno}  : options\_(options),
:::

::: {.line}
[]{#l00402}[ 402]{.lineno} 
process\_batch\_callback\_(process\_batch\_callback),
:::

::: {.line}
[]{#l00403}[ 403]{.lineno}  batch\_threads\_(new
thread::ThreadPool(options\_.env,
:::

::: {.line}
[]{#l00404}[ 404]{.lineno}  options\_.thread\_pool\_name,
:::

::: {.line}
[]{#l00405}[ 405]{.lineno}  options\_.num\_batch\_threads)) {}
:::

::: {.line}
[]{#l00406}[ 406]{.lineno} 
:::

::: {.line}
[]{#l00407}[ 407]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00408}[ 408]{.lineno} [bool]{.keywordtype}
StreamingBatchScheduler\<TaskType\>::TaskFitsInBatch(
:::

::: {.line}
[]{#l00409}[ 409]{.lineno}  [const]{.keyword} TaskType\* task,
[const]{.keyword} Batch\<TaskType\>\* batch)[ const ]{.keyword}{
:::

::: {.line}
[]{#l00410}[ 410]{.lineno}  [return]{.keywordflow} batch-\>size() +
task-\>size() \<= options\_.max\_batch\_size;
:::

::: {.line}
[]{#l00411}[ 411]{.lineno} }
:::

::: {.line}
[]{#l00412}[ 412]{.lineno} 
:::

::: {.line}
[]{#l00413}[ 413]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00414}[ 414]{.lineno} [void]{.keywordtype}
StreamingBatchScheduler\<TaskType\>::StartNewBatch() {
:::

::: {.line}
[]{#l00415}[ 415]{.lineno}  [if]{.keywordflow} (open\_batch\_ !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00416}[ 416]{.lineno}  open\_batch\_-\>Close();
:::

::: {.line}
[]{#l00417}[ 417]{.lineno}  open\_batch\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00418}[ 418]{.lineno}  }
:::

::: {.line}
[]{#l00419}[ 419]{.lineno} 
:::

::: {.line}
[]{#l00420}[ 420]{.lineno}  Batch\<TaskType\>\* new\_open\_batch =
[new]{.keyword} Batch\<TaskType\>;
:::

::: {.line}
[]{#l00421}[ 421]{.lineno}  ++num\_batches\_in\_progress\_; [//
Critically, increment \*outside\* the callback.]{.comment}
:::

::: {.line}
[]{#l00422}[ 422]{.lineno} 
batch\_threads\_-\>Schedule(\[[this]{.keyword}, new\_open\_batch\] {
:::

::: {.line}
[]{#l00423}[ 423]{.lineno}  this-\>process\_batch\_callback\_(
:::

::: {.line}
[]{#l00424}[ 424]{.lineno} 
std::unique\_ptr\<Batch\<TaskType\>\>(new\_open\_batch));
:::

::: {.line}
[]{#l00425}[ 425]{.lineno}  {
:::

::: {.line}
[]{#l00426}[ 426]{.lineno}  mutex\_lock l(this-\>mu\_);
:::

::: {.line}
[]{#l00427}[ 427]{.lineno}  \--this-\>num\_batches\_in\_progress\_;
:::

::: {.line}
[]{#l00428}[ 428]{.lineno}  }
:::

::: {.line}
[]{#l00429}[ 429]{.lineno}  });
:::

::: {.line}
[]{#l00430}[ 430]{.lineno}  open\_batch\_ = new\_open\_batch;
:::

::: {.line}
[]{#l00431}[ 431]{.lineno}  ++open\_batch\_num\_;
:::

::: {.line}
[]{#l00432}[ 432]{.lineno} }
:::

::: {.line}
[]{#l00433}[ 433]{.lineno} 
:::

::: {.line}
[]{#l00434}[ 434]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00435}[ 435]{.lineno} [void]{.keywordtype}
StreamingBatchScheduler\<TaskType\>::ScheduleCloseOfCurrentOpenBatch(
:::

::: {.line}
[]{#l00436}[ 436]{.lineno}  uint64\_t close\_time\_micros) {
:::

::: {.line}
[]{#l00437}[ 437]{.lineno}  [if]{.keywordflow} (batch\_closer\_ ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00438}[ 438]{.lineno}  batch\_closer\_.reset([new]{.keyword}
internal::SingleTaskScheduler(
:::

::: {.line}
[]{#l00439}[ 439]{.lineno}  options\_.env,
[\"batch\_closer\"]{.stringliteral},
options\_.no\_tasks\_wait\_time\_micros));
:::

::: {.line}
[]{#l00440}[ 440]{.lineno}  }
:::

::: {.line}
[]{#l00441}[ 441]{.lineno} 
:::

::: {.line}
[]{#l00442}[ 442]{.lineno}  [const]{.keyword} int64\_t
batch\_num\_to\_close = open\_batch\_num\_;
:::

::: {.line}
[]{#l00443}[ 443]{.lineno} 
batch\_closer\_-\>Schedule(close\_time\_micros, \[[this]{.keyword},
batch\_num\_to\_close\] {
:::

::: {.line}
[]{#l00444}[ 444]{.lineno}  {
:::

::: {.line}
[]{#l00445}[ 445]{.lineno}  mutex\_lock l(this-\>mu\_);
:::

::: {.line}
[]{#l00446}[ 446]{.lineno}  [if]{.keywordflow} (open\_batch\_num\_ ==
batch\_num\_to\_close) {
:::

::: {.line}
[]{#l00447}[ 447]{.lineno}  StartNewBatch();
:::

::: {.line}
[]{#l00448}[ 448]{.lineno}  }
:::

::: {.line}
[]{#l00449}[ 449]{.lineno}  }
:::

::: {.line}
[]{#l00450}[ 450]{.lineno}  });
:::

::: {.line}
[]{#l00451}[ 451]{.lineno} }
:::

::: {.line}
[]{#l00452}[ 452]{.lineno} 
:::

::: {.line}
[]{#l00453}[ 453]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00454}[ 454]{.lineno} Status CreateRetryingStreamingBatchScheduler(
:::

::: {.line}
[]{#l00455}[ 455]{.lineno}  [const]{.keyword} [typename]{.keyword}
StreamingBatchScheduler\<TaskType\>::Options& schedule\_options,
:::

::: {.line}
[]{#l00456}[ 456]{.lineno}  [const]{.keyword} [typename]{.keyword}
BatchSchedulerRetrier\<TaskType\>::Options& retry\_options,
:::

::: {.line}
[]{#l00457}[ 457]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TaskType\>\>)\>
:::

::: {.line}
[]{#l00458}[ 458]{.lineno}  process\_batch\_callback,
:::

::: {.line}
[]{#l00459}[ 459]{.lineno} 
std::unique\_ptr\<BatchScheduler\<TaskType\>\>\* scheduler) {
:::

::: {.line}
[]{#l00460}[ 460]{.lineno} 
std::unique\_ptr\<StreamingBatchScheduler\<TaskType\>\>
streaming\_scheduler;
:::

::: {.line}
[]{#l00461}[ 461]{.lineno} 
TF\_RETURN\_IF\_ERROR(StreamingBatchScheduler\<TaskType\>::Create(
:::

::: {.line}
[]{#l00462}[ 462]{.lineno}  schedule\_options, process\_batch\_callback,
&streaming\_scheduler));
:::

::: {.line}
[]{#l00463}[ 463]{.lineno} 
std::unique\_ptr\<BatchSchedulerRetrier\<TaskType\>\> retrier;
:::

::: {.line}
[]{#l00464}[ 464]{.lineno} 
TF\_RETURN\_IF\_ERROR(BatchSchedulerRetrier\<TaskType\>::Create(
:::

::: {.line}
[]{#l00465}[ 465]{.lineno}  retry\_options,
std::move(streaming\_scheduler), &retrier));
:::

::: {.line}
[]{#l00466}[ 466]{.lineno}  \*scheduler = std::move(retrier);
:::

::: {.line}
[]{#l00467}[ 467]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00468}[ 468]{.lineno} }
:::

::: {.line}
[]{#l00469}[ 469]{.lineno} 
:::

::: {.line}
[]{#l00470}[ 470]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00471}[ 471]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00472}[ 472]{.lineno} 
:::

::: {.line}
[]{#l00473}[ 473]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_STREAMING\_BATCH\_SCHEDULER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1StreamingBatchScheduler_html .ttc}
::: {.ttname}
[tensorflow::serving::StreamingBatchScheduler](classtensorflow_1_1serving_1_1StreamingBatchScheduler.html)
:::

::: {.ttdef}
**Definition:** streaming\_batch\_scheduler.h:113
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::SingleTaskScheduler](classtensorflow_1_1serving_1_1internal_1_1SingleTaskScheduler.html)
:::

::: {.ttdef}
**Definition:** streaming\_batch\_scheduler.h:246
:::
:::

::: {#astructtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::StreamingBatchScheduler::Options](structtensorflow_1_1serving_1_1StreamingBatchScheduler_1_1Options.html)
:::

::: {.ttdef}
**Definition:** streaming\_batch\_scheduler.h:116
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
