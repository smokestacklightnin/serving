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
batch\_scheduler\_retrier.h
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
TENSORFLOW\_SERVING\_BATCHING\_BATCH\_SCHEDULER\_RETRIER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_BATCH\_SCHEDULER\_RETRIER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<stddef.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<cstddef\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
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
[]{#l00032}[ 32]{.lineno} [// A wrapper around another BatchScheduler
that automatically retries]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Schedule() requests. Returns an
UNAVAILABLE error only after retry attempts]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// have failed (based on parameters that
govern the maximum number of retries]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// and the retry time interval).]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00037}[
[37](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.line}]{.lineno} [class
]{.keyword}[BatchSchedulerRetrier](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.code}
: [public]{.keyword} BatchScheduler\<TaskType\> {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00039}[
[39](structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// The maximum amount of time to spend
retrying \'wrapped\_-\>Schedule()\']{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// calls, in microseconds.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  int64\_t max\_time\_micros = 10 \* 1000 [/\*
10 milliseconds \*/]{.comment};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// The amount of time to pause between retry
attempts, in microseconds.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  int64\_t retry\_delay\_micros = 100;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// The environment to use for time and
sleeping.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  Env\* env = Env::Default();
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  };
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [static]{.keyword} Status Create(
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options.html){.code}&
options, std::unique\_ptr\<BatchScheduler\<TaskType\>\> wrapped,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
std::unique\_ptr\<[BatchSchedulerRetrier\<TaskType\>](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.code}\>\*
result);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
\~[BatchSchedulerRetrier](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  Status
Schedule(std::unique\_ptr\<TaskType\>\* task) [override]{.keyword};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [size\_t]{.keywordtype} NumEnqueuedTasks()
[const override]{.keyword};
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [size\_t]{.keywordtype} SchedulingCapacity()
[const override]{.keyword};
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [size\_t]{.keywordtype} max\_task\_size()[
const override ]{.keyword}{ [return]{.keywordflow}
wrapped\_-\>max\_task\_size(); }
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
[BatchSchedulerRetrier](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.code}([const]{.keyword}
Options& options,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
std::unique\_ptr\<BatchScheduler\<TaskType\>\> wrapped);
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [const]{.keyword} Options options\_;
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
std::unique\_ptr\<BatchScheduler\<TaskType\>\> wrapped\_;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([BatchSchedulerRetrier](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html){.code});
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} };
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} Status
BatchSchedulerRetrier\<TaskType\>::Create(
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword} Options& options,
std::unique\_ptr\<BatchScheduler\<TaskType\>\> wrapped,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
std::unique\_ptr\<BatchSchedulerRetrier\<TaskType\>\>\* result) {
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [if]{.keywordflow} (options.max\_time\_micros
\< 0) {
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"max\_time\_micros must be non-negative; was
\"]{.stringliteral},
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  options.max\_time\_micros);
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  }
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [if]{.keywordflow}
(options.retry\_delay\_micros \< 0) {
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [\"retry\_delay\_micros must be non-negative;
was \"]{.stringliteral},
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  options.retry\_delay\_micros);
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  }
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  result-\>reset([new]{.keyword}
BatchSchedulerRetrier(options, std::move(wrapped)));
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} Status
BatchSchedulerRetrier\<TaskType\>::Schedule(
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  std::unique\_ptr\<TaskType\>\* task) {
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  Status status;
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [const]{.keyword} uint64\_t
start\_time\_micros = options\_.env-\>NowMicros();
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [for]{.keywordflow} (;;) {
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  status = wrapped\_-\>Schedule(task);
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [if]{.keywordflow} (status.code() !=
error::UNAVAILABLE) {
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [// We either succeeded, or got a permanent
(non-retriable) error.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [break]{.keywordflow};
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  }
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [if]{.keywordflow}
((options\_.env-\>NowMicros() + options\_.retry\_delay\_micros) -
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  start\_time\_micros \>=
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  options\_.max\_time\_micros) {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// We don\'t have time in our budget to
retry again.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [break]{.keywordflow};
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  }
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
options\_.env-\>SleepForMicroseconds(options\_.retry\_delay\_micros);
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  }
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [return]{.keywordflow} status;
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} }
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [size\_t]{.keywordtype}
BatchSchedulerRetrier\<TaskType\>::NumEnqueuedTasks()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [return]{.keywordflow}
wrapped\_-\>NumEnqueuedTasks();
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} }
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [size\_t]{.keywordtype}
BatchSchedulerRetrier\<TaskType\>::SchedulingCapacity()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [return]{.keywordflow}
wrapped\_-\>SchedulingCapacity();
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} }
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00128}[
128]{.lineno} BatchSchedulerRetrier\<TaskType\>::BatchSchedulerRetrier(
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [const]{.keyword} Options& options,
std::unique\_ptr\<BatchScheduler\<TaskType\>\> wrapped)
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  : options\_(options),
wrapped\_(std::move(wrapped)) {}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_BATCH\_SCHEDULER\_RETRIER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1BatchSchedulerRetrier_html .ttc}
::: {.ttname}
[tensorflow::serving::BatchSchedulerRetrier](classtensorflow_1_1serving_1_1BatchSchedulerRetrier.html)
:::

::: {.ttdef}
**Definition:** batch\_scheduler\_retrier.h:37
:::
:::

::: {#astructtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::BatchSchedulerRetrier::Options](structtensorflow_1_1serving_1_1BatchSchedulerRetrier_1_1Options.html)
:::

::: {.ttdef}
**Definition:** batch\_scheduler\_retrier.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
