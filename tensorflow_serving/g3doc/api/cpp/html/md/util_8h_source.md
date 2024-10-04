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
util.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2017 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/framework/tensor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/counter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/sampler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/input.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/util/file\_probing\_env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// Implementation details mainly used for
testing; please don\'t depend on it.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} monitoring::Sampler\<1\>\* GetExampleCounts();
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} monitoring::Counter\<1\>\*
GetExampleCountTotal();
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// Metrics by model]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [void]{.keywordtype}
RecordModelRequestCount([const]{.keyword} [string]{.keywordtype}&
model\_name, [const]{.keyword} Status& status);
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// Enable/disable \`method\_name\` checks on
\`SignatureDef\` for predict, classify,]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// regress APIs. Native TF2 models use fixed
\`method\_name\` for all APIs, and]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// the check needs to be disabled to support
both TF1 and (native) TF2 models.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// Disabling the check (typically done at
process startup) should be OK and]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// safe for most API users. By default the
checks are enabled.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [void]{.keywordtype}
SetSignatureMethodNameCheckFeature([bool]{.keywordtype} v);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// Get current state of \`method\_name\`
check (see above for details).]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [bool]{.keywordtype}
GetSignatureMethodNameCheckFeature();
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// Records the example count of this request
with the metric tracking the]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// histogram of number of examples per
request.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [void]{.keywordtype}
RecordRequestExampleCount([const]{.keyword} [string]{.keywordtype}&
model\_name, [size\_t]{.keywordtype} count);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// InputToSerializedExampleTensor populates a
string Tensor of serialized]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// Examples.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// If input has n Examples returns a string
Tensor with shape {n}.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// Cases:]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// - Input kind unset: Tensor of shape
{0}]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// - Input::example\_list: Serializes each
example.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// - Input::example\_list\_with\_context:
Serializes each example merged with the]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// context.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// - Other: non-OK Status.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// Note: does not perform any structural
validation (e.g., if an example list is]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// empty it will return a Tensor of shape
{0}).]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} Status
InputToSerializedExampleTensor([const]{.keyword} Input& input, Tensor\*
examples);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// Issues a single Session::Run() call with
\'input\' to produce \'outputs\'.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// Equivalent to
InputToSerializedExampleTensor() followed by Session::Run().]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} Status PerformOneShotTensorComputation(
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [const]{.keyword} RunOptions& run\_options,
[const]{.keyword} Input& input,
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
input\_tensor\_name,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names, Session\* session,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  std::vector\<Tensor\>\* outputs,
[int]{.keywordtype}\* num\_input\_examples,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  thread::ThreadPoolOptions(),
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  int64\_t\* runtime\_latency =
[nullptr]{.keyword});
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [// Same as PerformOneShotTensorComputation()
above, except allows for multiple]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// input tensor names (each tensor is fed the
\*same\* \`input\`).]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} Status PerformOneShotTensorComputation(
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [const]{.keyword} RunOptions& run\_options,
[const]{.keyword} Input& input,
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [const]{.keyword} std::set\<string\>&
input\_tensor\_names,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names, Session\* session,
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::vector\<Tensor\>\* outputs,
[int]{.keywordtype}\* num\_input\_examples,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  thread::ThreadPoolOptions());
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// Populates given model\_spec based on the
model name and optional]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [// signature/version information.]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// If signature\_name has a value and is
empty, model\_spec\'s signature\_name is]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// set to
tensorflow::kDefaultServingSignatureDefKey.]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [void]{.keywordtype}
MakeModelSpec([const]{.keyword} [string]{.keywordtype}& model\_name,
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [const]{.keyword} absl::optional\<string\>&
signature\_name,
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [const]{.keyword}
absl::optional\<int64\_t\>& version,
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  ModelSpec\* model\_spec);
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// Gets the disk size of the model in the
given path.]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} Status GetModelDiskSize([const]{.keyword}
[string]{.keywordtype}& path, FileProbingEnv\* env,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  uint64\_t\* total\_file\_size);
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// Estimates the resources a session bundle
or saved model bundle will use once]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [// loaded, from its export or saved model
path. Directly uses disk state for]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// estimation.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} Status
EstimateResourceFromPathUsingDiskState([const]{.keyword}
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  FileProbingEnv\* env,
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  ResourceAllocation\* estimate);
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [// Update metrics for runtime
latency.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [void]{.keywordtype}
RecordRuntimeLatency([const]{.keyword} [string]{.keywordtype}&
model\_name, [const]{.keyword} [string]{.keywordtype}& api,
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
runtime, int64\_t latency\_usec);
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// Update metrics for request
latency.]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [void]{.keywordtype}
RecordRequestLatency([const]{.keyword} [string]{.keywordtype}&
model\_name, [const]{.keyword} [string]{.keywordtype}& api,
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
entrypoint, int64\_t latency\_usec);
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [// Get string keys of a map.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} std::set\<string\>
GetMapKeys([const]{.keyword} T& map) {
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  std::set\<string\> keys;
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
[auto]{.keyword}& it : map) {
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  keys.insert(it.first);
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  }
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [return]{.keywordflow} keys;
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} }
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [// Returns a \\ b, i.e. all items that are
in \`set\_a\` but not in \`set\_b\`.]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} std::set\<string\>
SetDifference(std::set\<string\> set\_a, std::set\<string\> set\_b);
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} [// Returns true if errors should be exported
to logging service.]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} [bool]{.keywordtype}
IsTfrtErrorLoggingEnabled();
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} 
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
