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
batching\_session.h
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
[]{#l00016}[ 16]{.lineno} [// A library for wrapping a tensorflow
session such that Run() calls get]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// scheduled in batches, using a batch
scheduler of your choice.]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<cstddef\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/basic\_batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/batching/batching\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/batching/threadsafe\_status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// The batch scheduler task type used for
batching sessions, for use in batch]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// scheduler template parameters, e.g.
BasicBatchScheduler\<BatchingSessionTask\>.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [struct ]{.keyword}BatchingSessionTask;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// A function to construct a batch scheduler
for BatchingSessionTasks from a]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// process-batch callback.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [using]{.keyword}
BatchingSessionSchedulerCreator = std::function\<Status(
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<BatchingSessionTask\>\>)\>,
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
std::unique\_ptr\<BatchScheduler\<BatchingSessionTask\>\>\*)\>;
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// The signature associated with a
Session::Run() call, in terms of input and]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// output tensor names (with the order in
which the tensors are listed factored]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// out). (Note that \'target\_node\_names\'
are not supported in batching sessions.)]{.comment}
:::

::: {.line}
[]{#l00055}[
[55](structtensorflow_1_1serving_1_1TensorSignature.html){.line}]{.lineno} [struct
]{.keyword}[TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html){.code}
{
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  std::set\<string\> input\_tensors;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  std::set\<string\> output\_tensors;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} };
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// Constructs a TensorSignature for a given
SignatureDef.]{.comment}
:::

::: {.line}
[]{#l00061}[
61]{.lineno} [TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html){.code}
TensorSignatureFromSignatureDef(
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [const]{.keyword} SignatureDef&
signature\_def);
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// Constructs a TensorSignature for a given
set of SignatureDefs. The resulting]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// TensorSignature represents the
Session::Run() arguments that would be used]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// when issuing a single Run() call that
exercises the signature defs jointly.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// For example, say there\'s a graph that
takes \'input\' and transforms it into]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// \'predicted\_label\' and
\'confidence\_score\'. Suppose SignatureDef 1 requests]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// only \'predicted\_label\' as output, and
SignatureDef 2 requests only]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// \'confidence\_score\'. A joint
TensorSignature would feed \'input\' and receive]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// both \'predicted\_label\' and
\'confidence\_score\' as output, in a single Run()]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// invocation.]{.comment}
:::

::: {.line}
[]{#l00074}[
74]{.lineno} [TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html){.code}
TensorSignatureFromSignatureDefs(
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [const]{.keyword}
std::vector\<SignatureDef\>& signature\_defs);
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// A signature paired with a lambda to create
a batch scheduler for Run() calls]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// matching the signature.]{.comment}
:::

::: {.line}
[]{#l00079}[
[79](structtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator.html){.line}]{.lineno} [struct
]{.keyword}[SignatureWithBatchingSessionSchedulerCreator](structtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator.html){.code}
{
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
[TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html){.code}
signature;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  BatchingSessionSchedulerCreator
scheduler\_creator;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} };
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [// Options for batching tensorflow Sessions;
see the Create\*() functions below.]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [using]{.keyword}
[BatchingSessionOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}
=
[BatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code};
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [// Wraps a session in a new session that
automatically batches Run() calls.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// Uses one batcher for each distinct Run()
signature supported. In addition to]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [// a session to wrap, takes a list of
signature/BatchingSessionSchedulerCreator]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [// pairs. (The number of supported signatures
is typically small, and often just]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [// a single one.)]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// The wrapped session only batches Run()
calls that conform to one of the]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} [// specified signatures and leave
\'target\_node\_names\' empty. Other Run() calls]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// are executed in-line without batching, and
may harm performance. (Extra-]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// signature Run() support is intended
primarily for debugging and diagnostics.)]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [// For batched calls, it is assumed that the
outermost (0th) dimension of each]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// input and output tensor is the batch-size
dimension. All input tensors must]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// have the same 0th-dimension size B; the
produced output tensors are also]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [// assumed to have 0th-dimension size
B.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [// IMPORTANT: Each call to Session::Run() is
synchronous, and blocks waiting for]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// other Run() calls with the same signature
to merge with to form a large]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// batch. Consequently, to achieve good
throughput we recommend setting the]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// number of client threads that call
Session::Run() equal to about twice the]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [// sum over all signatures of the maximum
batch size.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [// Example usage, for the common case of a
single signature:]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [// BatchingSessionOptions options =
\...;]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// auto scheduler\_creator =
\[schedule\_options, retry\_options\](]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [//
std::function\<void(std::unique\_ptr\<Batch\<BatchingSessionTask\>\>)\>]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [// process\_batch\_callback,]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [//
std::unique\_ptr\<BatchScheduler\<BatchingSessionTask\>\>\*
batch\_scheduler) {]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [//
std::unique\_ptr\<BasicBatchScheduler\<BatchingSessionTask\>\>
scheduler;]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [//
TF\_RETURN\_IF\_ERROR(BasicBatchScheduler\<BatchingSessionTask\>::Create(]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [// schedule\_options,
process\_batch\_callback, &scheduler));]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [//
std::unique\_ptr\<BatchSchedulerRetrier\<BatchingSessionTask\>\>
retrier;]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [//
TF\_RETURN\_IF\_ERROR(BatchSchedulerRetrier\<BatchingSessionTask\>::Create(]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// retry\_options, std::move(scheduler),
&retrier));]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [// \*batch\_scheduler =
std::move(retrier);]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [// return Status::OK();]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [// std::unique\_ptr\<Session\>
batching\_session;]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [//
TF\_CHECK\_OK(CreateBatchingSession(options, {{signature,
scheduler\_creator}},]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [// std::move(session),
&batching\_session));]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} Status CreateBatchingSession(
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [const]{.keyword}
[BatchingSessionOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}&
options,
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [const]{.keyword}
std::vector\<SignatureWithBatchingSessionSchedulerCreator\>&
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  signatures\_with\_scheduler\_creators,
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  std::unique\_ptr\<Session\> session,
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  std::unique\_ptr\<Session\>\*
batching\_session);
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} [// Same as above but allows for a default
scheduler creator for which signatures]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [// that don\'t match a supplied value during
run time can still use batching.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} Status CreateBatchingSession(
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [const]{.keyword}
[BatchingSessionOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}&
options,
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [const]{.keyword}
std::vector\<SignatureWithBatchingSessionSchedulerCreator\>&
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  signatures\_with\_scheduler\_creators,
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  BatchingSessionSchedulerCreator
default\_creator,
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  std::unique\_ptr\<Session\> session,
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  std::unique\_ptr\<Session\>\*
batching\_session);
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} [// A convenience for using
CreateBatchingSession() to create a]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} [// BasicBatchScheduler for a single
signature.]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} Status CreateBasicBatchingSession(
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [const]{.keyword} [typename]{.keyword}
BasicBatchScheduler\<BatchingSessionTask\>::Options&
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  schedule\_options,
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [const]{.keyword}
[BatchingSessionOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}&
batching\_session\_options,
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [const]{.keyword}
[TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html){.code}&
signature, std::unique\_ptr\<Session\> session,
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  std::unique\_ptr\<Session\>\*
batching\_session);
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} [// The default implementation of]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} [//
\`BasicBatchScheduler::Options.split\_input\_task\_func\` if
corresponding batch]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} [// scheduler for a batching session
sets]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} [//
\`BasicBatchScheduler::Options.enable\_large\_batch\_splitting\` to
true.]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} Status SplitInputTask(
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  std::unique\_ptr\<BatchingSessionTask\>\*
input\_task\_ptr,
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [int]{.keywordtype}
open\_batch\_remaining\_slot, [int]{.keywordtype} max\_batch\_size,
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
std::vector\<std::unique\_ptr\<BatchingSessionTask\>\>\* output\_tasks);
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
:::

::: {.line}
[]{#l00167}[
[167](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.line}]{.lineno} [struct
]{.keyword}[BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.code}
: [public]{.keyword} BatchTask {
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
\~[BatchingSessionTask](structtensorflow_1_1serving_1_1BatchingSessionTask.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [size\_t]{.keywordtype} size()[ const
override ]{.keyword}{ [return]{.keywordflow} zeroth\_dim\_size; }
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [// For monitoring purpose.]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [static]{.keyword} std::string Name() {
[return]{.keywordflow} [\"batching\_session\"]{.stringliteral}; }
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// Fields populated when a task is
received.]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  uint64\_t enqueue\_time\_micros;
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  RunOptions run\_options;
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [size\_t]{.keywordtype} zeroth\_dim\_size;
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>\* inputs;
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [const]{.keyword} std::vector\<string\>\*
output\_tensor\_names;
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} 
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [// Fields populated when a task is
processed (as part of a batch), and]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [// returned by BatchingSession when a task
is complete.]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  Notification\* done;
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  Status\* status;
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  std::vector\<Tensor\>\* outputs;
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  RunMetadata\* run\_metadata;
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  absl::optional\<thread::ThreadPoolOptions\>
thread\_pool\_options;
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// Fields populated when a task is
processed (as part of a batch), and]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// substantially used in the intermediate
stage if a task is a slice of]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [// input task (i.e.,
is\_partial=true).]{.comment}
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [bool]{.keywordtype} is\_partial =
[false]{.keyword};
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [// \'owned\_split\_inputs\' stores pairs of
tensor names and input tensors]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [// if \'is\_partial\' = true.]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} 
std::unique\_ptr\<std::vector\<std::pair\<string, Tensor\>\>\>
owned\_split\_inputs;
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// The index of this split, along the 0-th
dimension of input from op]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [// invocation.]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [int]{.keywordtype} split\_index = 0;
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  std::function\<void()\> done\_callback;
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [typedef]{.keyword}
std::vector\<std::vector\<Tensor\>\> TensorMatrix;
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// For shared\_ptr objects, ownership
shared by:]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [// 1) each split of task (to fill one row
in this matrix)]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// and]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [// 2) callback that runs to merge output of
individual splits for an op]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [// invocation, after all splits
complete.]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [// Two-dimensional tensor
matrix,]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  std::shared\_ptr\<TensorMatrix\>
shared\_outputs;
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [// \'status\' records error (could be from
any split) if at least one split]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [// returns error, OK otherwise.]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  std::shared\_ptr\<ThreadSafeStatus\>
thread\_safe\_status;
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [// \'split\_run\_metadatas\' records
\`run\_metadata\` of each split.]{.comment}
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
std::shared\_ptr\<std::vector\<RunMetadata\>\> split\_run\_metadatas;
:::

::: {.line}
[]{#l00213}[ 213]{.lineno} };
:::

::: {.line}
[]{#l00214}[ 214]{.lineno} 
:::

::: {.line}
[]{#l00215}[ 215]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00217}[ 217]{.lineno} 
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_SESSION\_H\_]{.comment}
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

::: {#astructtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator_html .ttc}
::: {.ttname}
[tensorflow::serving::SignatureWithBatchingSessionSchedulerCreator](structtensorflow_1_1serving_1_1SignatureWithBatchingSessionSchedulerCreator.html)
:::

::: {.ttdef}
**Definition:** batching\_session.h:79
:::
:::

::: {#astructtensorflow_1_1serving_1_1TensorSignature_html .ttc}
::: {.ttname}
[tensorflow::serving::TensorSignature](structtensorflow_1_1serving_1_1TensorSignature.html)
:::

::: {.ttdef}
**Definition:** batching\_session.h:55
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
