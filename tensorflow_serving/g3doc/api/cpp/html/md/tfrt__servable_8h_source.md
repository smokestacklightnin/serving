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
tfrt\_servable.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2023 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SERVABLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SERVABLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/container/flat\_hash\_set.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"absl/functional/any\_invocable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"absl/status/statusor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/tfrt/saved\_model/saved\_model.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_metadata.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/apis/inference.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/predict\_response\_tensor\_serialization\_option.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/saved\_model\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_source\_adapter.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// The RequestRecorder interface for
implementations to inject custom metric and]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// cost reporting.]{.comment}
:::

::: {.line}
[]{#l00048}[
[48](classtensorflow_1_1serving_1_1RequestRecorder.html){.line}]{.lineno} [class
]{.keyword}[RequestRecorder](classtensorflow_1_1serving_1_1RequestRecorder.html){.code}
{
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [virtual]{.keyword}
\~[RequestRecorder](classtensorflow_1_1serving_1_1RequestRecorder.html){.code}();
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} };
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// Implements PredictionService\`-like
interface for a single SavedModel based on]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// \`tensorflow::tfrt\_stub::SavedModel\`.
Executables are lazily compiled on its]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// first use and cached. This class is
thread-safe.]{.comment}
:::

::: {.line}
[]{#l00056}[
[56](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.line}]{.lineno} [class
]{.keyword}[TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}
: [public]{.keyword}
[Servable](classtensorflow_1_1serving_1_1Servable.html){.code} {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
[TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}(absl::string\_view
name, int64\_t version,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [const]{.keyword} TfrtSavedModelConfig&
config,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [const]{.keyword} SavedModelConfig&
model\_config,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  std::unique\_ptr\<tfrt\_stub::SavedModel\>
saved\_model,
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory)
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  :
[TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}(
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  name, version, config, model\_config,
std::move(saved\_model),
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  thread\_pool\_factory,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
\[\]([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)
{ [return]{.keywordflow} [nullptr]{.keyword}; }) {}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
[TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}(
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  absl::string\_view name, int64\_t version,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword} TfrtSavedModelConfig&
config, [const]{.keyword} SavedModelConfig& model\_config,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  std::unique\_ptr\<tfrt\_stub::SavedModel\>
saved\_model,
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory,
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
std::function\<std::unique\_ptr\<RequestRecorder\>([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)\>
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  recorder\_creator);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  absl::Status Classify([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword} ClassificationRequest&
request,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  ClassificationResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  absl::Status Regress([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [const]{.keyword} RegressionRequest& request,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  RegressionResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  absl::Status Predict([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [const]{.keyword} PredictRequest& request,
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  PredictResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
absl::StatusOr\<std::unique\_ptr\<PredictStreamedContext\>\>
PredictStreamed(
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
absl::AnyInvocable\<[void]{.keywordtype}(absl::StatusOr\<PredictResponse\>)\>
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  response\_callback) [override]{.keyword};
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  absl::Status MultiInference([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [const]{.keyword} MultiInferenceRequest&
request,
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  MultiInferenceResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  absl::Status
GetModelMetadata([const]{.keyword} GetModelMetadataRequest& request,
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  GetModelMetadataResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [bool]{.keywordtype} SupportsPaging()[ const
override ]{.keyword}{ [return]{.keywordflow} [true]{.keyword}; }
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  absl::Status Suspend() [override]{.keyword};
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  absl::Status Resume() [override]{.keyword};
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  tfrt\_stub::SavedModel& saved\_model()[
const ]{.keyword}{ [return]{.keywordflow} \*saved\_model\_; }
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [void]{.keywordtype} set\_resume\_fn(
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
absl::AnyInvocable\<absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}\*)\>
resume\_fn) {
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  absl::MutexLock lock(&paging\_mu\_);
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  resume\_fn\_ = std::move(resume\_fn);
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  }
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [void]{.keywordtype} set\_suspend\_fn(
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
absl::AnyInvocable\<absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}\*)\>
suspend\_fn) {
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  absl::MutexLock lock(&paging\_mu\_);
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  suspend\_fn\_ = std::move(suspend\_fn);
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  tfrt\_stub::SavedModel::RunOptions
GetTFRTSavedModelRunOptions(
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [const]{.keyword}
[Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options) [const]{.keyword};
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  std::unique\_ptr\<RequestRecorder\>
CreateRecorder() {
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [return]{.keywordflow}
recorder\_creator\_(\*[this]{.keyword});
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  }
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  std::unique\_ptr\<tfrt\_stub::SavedModel\>
saved\_model\_;
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [// \`config\_\` is the adapter config, and
it is the same for all]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// TfrtSavedModelServables within a model
server.]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  TfrtSavedModelConfig config\_;
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
internal::PredictResponseTensorSerializationOption
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
predict\_response\_tensor\_serialization\_option\_ =
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
internal::PredictResponseTensorSerializationOption::kAsProtoField;
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// \`thread\_pool\_factory\_\` is not owned
by Servables. In a typical]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// implementation, the factory will own the
\`thread\_pool\_factory\_\` and it will]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// be shared across different
Servables.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} 
std::function\<std::unique\_ptr\<RequestRecorder\>([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)\>
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  recorder\_creator\_ =
\[\]([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)
{ [return]{.keywordflow} [nullptr]{.keyword}; };
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
absl::AnyInvocable\<absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}\*)\>
suspend\_fn\_
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  ABSL\_GUARDED\_BY(paging\_mu\_);
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
absl::AnyInvocable\<absl::Status([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}\*)\>
resume\_fn\_
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  ABSL\_GUARDED\_BY(paging\_mu\_);
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [bool]{.keywordtype} suspended\_
ABSL\_GUARDED\_BY(paging\_mu\_) = [false]{.keyword};
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  absl::Mutex paging\_mu\_;
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} };
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} 
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} [// Creates a TfrtSavedModelServable from
\`saved\_model\_dir\`.]{.comment}
:::

::: {.line}
[]{#l00158}[
158]{.lineno} absl::StatusOr\<std::unique\_ptr\<TfrtSavedModelServable\>\>
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} CreateTfrtSavedModelServable(
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [const]{.keyword}
tensorflow::tfrt\_stub::SavedModel::Options& options,
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  absl::string\_view name, int64\_t version,
absl::string\_view saved\_model\_dir,
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  absl::flat\_hash\_set\<std::string\> tags);
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SERVABLE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1RequestRecorder_html .ttc}
::: {.ttname}
[tensorflow::serving::RequestRecorder](classtensorflow_1_1serving_1_1RequestRecorder.html)
:::

::: {.ttdef}
**Definition:** tfrt\_servable.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Servable_html .ttc}
::: {.ttname}
[tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html)
:::

::: {.ttdef}
**Definition:** servable.h:80
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelServable_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html)
:::

::: {.ttdef}
**Definition:** tfrt\_servable.h:56
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadPoolFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html)
:::

::: {.ttdef}
**Definition:** thread\_pool\_factory.h:48
:::
:::

::: {#astructtensorflow_1_1serving_1_1servables_1_1RunOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::servables::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html)
:::

::: {.ttdef}
**Definition:** run\_options.h:27
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
