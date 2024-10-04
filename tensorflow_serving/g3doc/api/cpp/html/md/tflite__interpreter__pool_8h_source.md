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
tflite\_interpreter\_pool.h
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
[]{#l00016}[ 16]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_INTERPRETER\_POOL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_INTERPRETER\_POOL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/framework/tensor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/gtl/array\_slice.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/tstring.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/public/session\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/lite/c/common.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/lite/model.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#ifdef TFLITE\_PROFILE]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#ifndef
TFLITE\_PROFILE\_EVENTS]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#define TFLITE\_PROFILE\_EVENTS
2000]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow/lite/profiling/buffered\_profiler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow/lite/profiling/profile\_summarizer.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow/lite/profiling/profile\_summary\_formatter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow/lite/string\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} constexpr [int]{.keywordtype}
kInitialBatchSize = 500;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[
[47](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.line}]{.lineno} [class
]{.keyword}[TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.code}
{
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Wrapper class for a single TfLite
Interpreter for use in an interpreter]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// pool.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// Create an interpreter and external
context and wrap it in the class]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// for use with an
InterpreterPool.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [static]{.keyword} Status
CreateTfLiteInterpreterWrapper(
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [const]{.keyword} tflite::FlatBufferModel&
model,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword} tensorflow::SessionOptions&
options,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  std::unique\_ptr\<TfLiteInterpreterWrapper\>&
wrapper);
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Constructor for wrapper takes only an
initialized interpreter.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
[TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.code}(
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
std::unique\_ptr\<tflite::ExternalCpuBackendContext\> external\_context,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  std::unique\_ptr\<tflite::Interpreter\>
interpreter);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
[TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.code}(std::unique\_ptr\<tflite::Interpreter\>
interpreter)
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  :
[TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html){.code}([nullptr]{.keyword},
std::move(interpreter)) {}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Returns the underlying
interpreter.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  tflite::Interpreter\* Get() {
[return]{.keywordflow} interpreter\_.get(); }
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// Get the allocated batch size of the
interpreter.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [int]{.keywordtype} GetBatchSize() {
[return]{.keywordflow} batch\_size\_; }
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Set the batch size.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [void]{.keywordtype}
SetBatchSize([int]{.keywordtype} batch\_size) { batch\_size\_ =
batch\_size; }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// Invokes the interpreter.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  TfLiteStatus Invoke();
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [\#ifdef TFLITE\_PROFILE]{.preprocessor}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [void]{.keywordtype}
WriteOutput([const]{.keyword} std::string& header, [const]{.keyword}
[string]{.keywordtype}& data,
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  std::ostream\* stream) {
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  (\*stream) \<\< header \<\< std::endl;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  (\*stream) \<\< data \<\< std::endl;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  }
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [void]{.keywordtype} WriteProfileData() {
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [if]{.keywordflow}
(run\_summarizer\_.HasProfiles()) {
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  WriteOutput([\"Operator-wise Profiling Info
for Regular Benchmark Runs:\"]{.stringliteral},
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  run\_summarizer\_.GetOutputString(),
&std::cout);
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// Sets the contents of the internal buffer
\_tensor\_buffer\_ to the tflite]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// formatted string buffer equivalent stored
in \`batch\` and sets]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [// raw pointer of \`tflite\_tensor\` to the
internal buffer. If the required]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// size is larger than the current size,
will allocate new memory and]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// free the existing buffer.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  tensorflow::Status
SetStringData([const]{.keyword} std::vector\<const Tensor\*\>& tensors,
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  TfLiteTensor\* tflite\_tensor,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [int]{.keywordtype} tensor\_index,
[int]{.keywordtype} batch\_size);
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// External cpu context to enable
caching.]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
std::unique\_ptr\<tflite::ExternalCpuBackendContext\>
external\_context\_;
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  std::unique\_ptr\<tflite::Interpreter\>
interpreter\_;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [int]{.keywordtype} batch\_size\_ = 1;
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  std::map\<int, std::unique\_ptr\<char\>\>
tensor\_buffer\_;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  std::map\<int, size\_t\>
tensor\_buffer\_max\_bytes\_;
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  std::vector\<int32\_t\> offset\_;
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [\#ifdef TFLITE\_PROFILE]{.preprocessor}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [int]{.keywordtype} max\_num\_entries\_;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  tflite::profiling::ProfileSummarizer
run\_summarizer\_;
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  tflite::profiling::BufferedProfiler
profiler\_;
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [int]{.keywordtype} invocation\_count\_ = 0;
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} };
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [// Contains a vector of
TfLiteInterpreterWrapper, which are protected by mutex.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [// When GetInterpreter is called, will
either release a unique ptr to the]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [// caller or block if the vector is
empty.]{.comment}
:::

::: {.line}
[]{#l00120}[
[120](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool.html){.line}]{.lineno} [class
]{.keyword}[TfLiteInterpreterPool](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool.html){.code}
{
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// Creates a TfLiteSessionPool with model,
session options,]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [// pool\_size number of
interpreters.]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [static]{.keyword} tensorflow::Status
CreateTfLiteInterpreterPool(
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [const]{.keyword} tflite::FlatBufferModel\*
model,
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [const]{.keyword}
tensorflow::SessionOptions& options, [int]{.keywordtype} pool\_size,
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  std::unique\_ptr\<TfLiteInterpreterPool\>&
interpreter\_pool);
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// Returns a TFLite interpreter wrapper
object. Caller may \*block\* waiting for]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [// a free interpreter pool to be
available.]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  std::unique\_ptr\<TfLiteInterpreterWrapper\>
GetInterpreter() {
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [auto]{.keyword} interpreter\_available =
\[[this]{.keyword}\]() ABSL\_SHARED\_LOCKS\_REQUIRED(mutex\_) {
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [return]{.keywordflow}
!this-\>available\_.empty();
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  };
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
mutex\_.LockWhen(absl::Condition(&interpreter\_available));
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [auto]{.keyword} pool =
std::move(available\_.back());
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  available\_.pop\_back();
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  mutex\_.Unlock();
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [return]{.keywordflow} pool;
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  }
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// Returns an interpreter wrapper to the
available pool.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [void]{.keywordtype} ReturnInterpreter(
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  std::unique\_ptr\<TfLiteInterpreterWrapper\>
interpreter) {
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  absl::MutexLock l(&mutex\_);
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
available\_.emplace\_back(std::move(interpreter));
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  }
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} 
[TfLiteInterpreterPool](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool.html){.code}(
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
std::vector\<std::unique\_ptr\<TfLiteInterpreterWrapper\>\>
interpreters)
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  : available\_(std::move(interpreters)) {}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [mutable]{.keyword} absl::Mutex mutex\_;
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
std::vector\<std::unique\_ptr\<TfLiteInterpreterWrapper\>\> available\_
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  ABSL\_GUARDED\_BY(mutex\_);
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} };
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFLITE\_INTERPRETER\_POOL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::TfLiteInterpreterPool](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterPool.html)
:::

::: {.ttdef}
**Definition:** tflite\_interpreter\_pool.h:120
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::TfLiteInterpreterWrapper](classtensorflow_1_1serving_1_1internal_1_1TfLiteInterpreterWrapper.html)
:::

::: {.ttdef}
**Definition:** tflite\_interpreter\_pool.h:47
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
