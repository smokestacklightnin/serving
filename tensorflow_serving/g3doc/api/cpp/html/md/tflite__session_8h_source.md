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
-   [servables](dir_e240d895a087fc4ce46e8f4c52318018.html){.el}
-   [tensorflow](dir_143c99ffaf6c8b3b63b06c22e49d7998.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tflite\_session.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2019 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/framework/tensor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/basic\_batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/file\_system.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/lite/external\_cpu\_backend\_context.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow/lite/interpreter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow/lite/kernels/cpu\_backend\_context.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow/lite/model.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/batching/threadsafe\_status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/serving\_session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tflite\_interpreter\_pool.h\"]{.preprocessor}
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
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [using]{.keyword} TensorInfoMap =
std::map\<string, std::pair\<TensorInfo, int\>\>;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// Encapsulates a unit of work for
BatchScheduler.]{.comment}
:::

::: {.line}
[]{#l00046}[
[46](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.line}]{.lineno} [class
]{.keyword}[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}
: [public]{.keyword} BatchTask {
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Creates a batch task.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [static]{.keyword} [void]{.keywordtype}
CreateTfLiteBatchTask(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword} std::vector\<string\>\*
output\_tensor\_names,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  std::vector\<Tensor\>\* outputs,
Notification\* done, Status\* status,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  std::unique\_ptr\<TfLiteBatchTask\>\*
batch\_task) {
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}\*
task = [new]{.keyword}
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}();
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  task-\>is\_partial = [false]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  task-\>output\_tensor\_names =
output\_tensor\_names;
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  task-\>outputs = outputs;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  task-\>done = done;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  task-\>status = status;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  batch\_task-\>reset(task);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  }
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Create partial batch task.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [static]{.keyword} [void]{.keywordtype}
CreatePartialTfLiteBatchTask(
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  std::vector\<int\> input\_indices,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [const]{.keyword} std::vector\<string\>\*
output\_tensor\_names,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  std::vector\<Tensor\>\* outputs,
std::function\<[void]{.keywordtype}()\> done\_callback,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.code}\*
partial\_status,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  std::unique\_ptr\<TfLiteBatchTask\>\*
batch\_task) {
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}\*
task = [new]{.keyword}
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}();
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  task-\>is\_partial = [true]{.keyword};
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  task-\>input\_indices = input\_indices;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  task-\>output\_tensor\_names =
output\_tensor\_names;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  task-\>outputs = outputs;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  task-\>done\_callback = done\_callback;
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  task-\>partial\_status = partial\_status;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  batch\_task-\>reset(task);
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  }
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}()
: enqueue\_time\_micros(Env::Default()-\>NowMicros()) {}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}([const]{.keyword}
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}&)
= [delete]{.keyword};
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}&
operator=([const]{.keyword}
[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}&)
= [delete]{.keyword};
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
\~[TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// Returns the batch size.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [size\_t]{.keywordtype} size()[ const
override ]{.keyword}{ [return]{.keywordflow} inputs\[0\].dim\_size(0); }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  uint64\_t start\_time\_micros()[ const
]{.keyword}{ [return]{.keywordflow} enqueue\_time\_micros; }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  Notification\* done;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  Status\* status;
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// Input indices for the tflite tensors,
aligned with inputs.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  std::vector\<int\> input\_indices;
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// Vector of input tensors.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::vector\<Tensor\> inputs;
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// Pointer to tensor of outputs.]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  std::vector\<Tensor\>\* outputs;
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [void]{.keywordtype} set\_output(Tensor t) {
outputs-\>push\_back(t); }
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [const]{.keyword} std::vector\<string\>\*
output\_tensor\_names;
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  RunOptions run\_options;
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [const]{.keyword} uint64\_t
enqueue\_time\_micros;
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// Required for partial execution using
split batches.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [bool]{.keywordtype} is\_partial =
[false]{.keyword};
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// A callback for when the partial task is
completed.]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  std::function\<void()\> done\_callback;
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.code}\*
partial\_status;
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} };
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [using]{.keyword} SchedulerCreator =
std::function\<Status(
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [const]{.keyword}
BasicBatchScheduler\<TfLiteBatchTask\>::Options& options,
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TfLiteBatchTask\>\>)\>,
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
std::unique\_ptr\<BasicBatchScheduler\<TfLiteBatchTask\>\>\*)\>;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [// A session to run inference on a
TensorFlow Lite model.]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00129}[
[129](classtensorflow_1_1serving_1_1TfLiteSession.html){.line}]{.lineno} [class
]{.keyword}[TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.code}
: [public]{.keyword}
[ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.code}
{
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// Creates a TfLiteSession object from
\`buffer\` representing serialized]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// TFLite flatbuffer model. Also returns
the SignatureDef map based on]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [// input/outputs to the model.]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// run in caller thread allows a worker to
run on the parent thread,]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// which may be desired to increase
concurrency at the cost of additional]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// thread context overhead. Defaults to
false.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [static]{.keyword} Status
Create([string]{.keywordtype}&& buffer, [const]{.keyword}
SessionOptions& options,
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [int]{.keywordtype} num\_pools,
[int]{.keywordtype} num\_interpreters\_per\_pool,
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  std::unique\_ptr\<TfLiteSession\>\*
tflite\_session,
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  ::google::protobuf::Map\<string,
SignatureDef\>\* signatures);
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [static]{.keyword} Status
CreateDefaultBasicBatchScheduler(
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [const]{.keyword}
BasicBatchScheduler\<TfLiteBatchTask\>::Options& options,
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
std::function\<[void]{.keywordtype}(std::unique\_ptr\<Batch\<TfLiteBatchTask\>\>)\>
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  process\_batch\_callback,
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
std::unique\_ptr\<BasicBatchScheduler\<TfLiteBatchTask\>\>\*
batch\_scheduler);
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [static]{.keyword} Status
SplitTfLiteInputTask(
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  std::unique\_ptr\<TfLiteBatchTask\>\*
input\_task\_ptr,
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [int]{.keywordtype}
open\_batch\_remaining\_slot, [int]{.keywordtype} max\_batch\_size,
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
std::vector\<std::unique\_ptr\<TfLiteBatchTask\>\>\* output\_tasks);
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
\~[TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} 
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  Status Run([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  std::vector\<Tensor\>\* outputs)
[override]{.keyword};
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  Status Run([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata) [override]{.keyword};
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  Status Run([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata,
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options) [override]{.keyword};
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  Status
ListDevices(std::vector\<DeviceAttributes\>\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  Status SetScheduler(
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [const]{.keyword} SchedulerCreator&
scheduler\_creator,
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [const]{.keyword}
BasicBatchScheduler\<TfLiteBatchTask\>::Options& options);
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} 
BasicBatchScheduler\<TfLiteBatchTask\>::Options GetSchedulerOptions() {
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [return]{.keywordflow} scheduler\_options\_;
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  }
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} 
[TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.code}(
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  std::map\<string, int\>&&
input\_tensor\_to\_index,
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  std::map\<string, int\>&&
output\_tensor\_to\_index, [string]{.keywordtype}&& buffer,
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  std::unique\_ptr\<tflite::FlatBufferModel\>
model,
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
std::unique\_ptr\<internal::TfLiteInterpreterPool\> interpreter\_pool);
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  Status RunInternal(
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [const]{.keyword} std::vector\<int\>&
tflite\_input\_indices,
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [const]{.keyword}
std::vector\<std::vector\<const Tensor\*\>\>& merged\_inputs,
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  std::vector\<Tensor\>\* combined\_outputs,
[int]{.keywordtype} batch\_size,
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [int]{.keywordtype}\* fixed\_batch\_size =
[nullptr]{.keyword});
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [const]{.keyword} std::map\<string, int\>
input\_tensor\_to\_index\_;
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [const]{.keyword} std::map\<string, int\>
output\_tensor\_to\_index\_;
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [const]{.keyword} [string]{.keywordtype}
model\_serialized\_bytes\_;
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [const]{.keyword}
std::unique\_ptr\<tflite::FlatBufferModel\> model\_;
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [const]{.keyword}
std::unique\_ptr\<internal::TfLiteInterpreterPool\> interpreter\_pool\_;
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [bool]{.keywordtype}
use\_fixed\_batch\_size\_;
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} 
std::unique\_ptr\<BasicBatchScheduler\<TfLiteBatchTask\>\> scheduler\_;
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} 
BasicBatchScheduler\<TfLiteBatchTask\>::Options scheduler\_options\_;
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [void]{.keywordtype}
ProcessBatch(std::unique\_ptr\<Batch\<TfLiteBatchTask\>\> batch);
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html){.code});
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} };
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} 
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} 
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_SESSION\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServingSession_html .ttc}
::: {.ttname}
[tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html)
:::

::: {.ttdef}
**Definition:** serving\_session.h:34
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfLiteBatchTask_html .ttc}
::: {.ttname}
[tensorflow::serving::TfLiteBatchTask](classtensorflow_1_1serving_1_1TfLiteBatchTask.html)
:::

::: {.ttdef}
**Definition:** tflite\_session.h:46
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfLiteSession_html .ttc}
::: {.ttname}
[tensorflow::serving::TfLiteSession](classtensorflow_1_1serving_1_1TfLiteSession.html)
:::

::: {.ttdef}
**Definition:** tflite\_session.h:129
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadSafeStatus_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html)
:::

::: {.ttdef}
**Definition:** threadsafe\_status.h:45
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
