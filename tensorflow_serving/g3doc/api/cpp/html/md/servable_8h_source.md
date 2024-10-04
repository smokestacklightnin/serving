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
servable.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVABLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVABLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<stdint.h\>]{.preprocessor}
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
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/functional/any\_invocable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"absl/status/statusor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_metadata.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/apis/inference.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/run\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [inline]{.keyword} constexpr
absl::string\_view kSignatureDef = [\"signature\_def\"]{.stringliteral};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// Context of a \`PredictStreamed\` session.
The caller of \`PredictStreamed\` calls]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// \`ProcessRequest\` every time a request
becomes available. The caller must call]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// \`Close()\` at the end of the session
before deleting the context object.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// The implementation can be
thread-compatible. The caller is responsible for]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// synchronizing all method
invocations.]{.comment}
:::

::: {.line}
[]{#l00047}[
[47](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.line}]{.lineno} [class
]{.keyword}[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.code}
{
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [virtual]{.keyword}
\~[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// Consumes one incoming request. Blocking
here may delay the consumption of]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// subsequent requests.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [virtual]{.keyword} absl::Status
ProcessRequest([const]{.keyword} PredictRequest& request) = 0;
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// Closes the \`PredictStreamed\`
session.]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [virtual]{.keyword} absl::Status Close() = 0;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} };
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// A convenience wrapper for cases where the
implementation allows exactly one]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// request. \`f\` takes this single request
and produces responses by calling the]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// \`response\_callback\` passed to
\`Servable::PredictStreamed\`.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// This implementation is thread compatible
but not thread safe.]{.comment}
:::

::: {.line}
[]{#l00064}[
[64](classtensorflow_1_1serving_1_1SingleRequestPredictStreamedContext.html){.line}]{.lineno} [class
]{.keyword}[SingleRequestPredictStreamedContext](classtensorflow_1_1serving_1_1SingleRequestPredictStreamedContext.html){.code}
final
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  : [public]{.keyword}
[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.code}
{
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [explicit]{.keyword}
[SingleRequestPredictStreamedContext](classtensorflow_1_1serving_1_1SingleRequestPredictStreamedContext.html){.code}(
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
absl::AnyInvocable\<absl::Status([const]{.keyword} PredictRequest&)\>
f);
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  absl::Status ProcessRequest([const]{.keyword}
PredictRequest& request) [final]{.keyword};
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  absl::Status Close() [final]{.keyword};
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
absl::AnyInvocable\<absl::Status([const]{.keyword} PredictRequest&)\>
f\_;
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [bool]{.keywordtype} one\_request\_received\_
= [false]{.keyword};
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} };
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// Provides a \`PredictionService\`-like
interface. All concrete implementations]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// are expected to be thread-safe.]{.comment}
:::

::: {.line}
[]{#l00080}[
[80](classtensorflow_1_1serving_1_1Servable.html){.line}]{.lineno} [class
]{.keyword}[Servable](classtensorflow_1_1serving_1_1Servable.html){.code}
{
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
[Servable](classtensorflow_1_1serving_1_1Servable.html){.code}(absl::string\_view
name, int64\_t version, [bool]{.keywordtype} is\_critical =
[false]{.keyword})
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  : name\_(std::string(name)),
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  version\_(version),
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  is\_critical\_(is\_critical) {}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [virtual]{.keyword}
\~[Servable](classtensorflow_1_1serving_1_1Servable.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Returns the name associated with this
servable.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  absl::string\_view name()[ const ]{.keyword}{
[return]{.keywordflow} name\_; }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// Returns the version associated with this
servable.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  int64\_t version()[ const ]{.keyword}{
[return]{.keywordflow} version\_; }
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [bool]{.keywordtype} IsCritical()[ const
]{.keyword}{ [return]{.keywordflow} is\_critical\_; }
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [using]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}
=
[tensorflow::serving::servables::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code};
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [virtual]{.keyword} absl::Status
Classify([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [const]{.keyword} ClassificationRequest&
request,
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  ClassificationResponse\* response) = 0;
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [virtual]{.keyword} absl::Status
Regress([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [const]{.keyword} RegressionRequest&
request,
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  RegressionResponse\* response) = 0;
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [virtual]{.keyword} absl::Status
Predict([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [const]{.keyword} PredictRequest& request,
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  PredictResponse\* response) = 0;
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// Bidirectional streamed version of
\`Predict\`. Returns a \"context\" object]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// that allows the caller to pass requests
incrementally. The servable is kept]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// alive until the context object is
deleted.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// \`response\_callback\` is called for
each streamed output, zero or more times,]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// when the streamed output becomes
available. If an error is returned for any]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// response, subsequent responses and
requests will be ignored and the error]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// will be returned. The callback
invocation must be serialized by the]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// implementation, so that
\`response\_callback\` does not have to be]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// thread-safe, but blocking inside the
callback may cause the next callback]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// invocation to be delayed. The
implementation must guarantee that the]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// callback is never called after the
\`PredictStreamed\` method returns.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [virtual]{.keyword}
absl::StatusOr\<std::unique\_ptr\<PredictStreamedContext\>\>
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  PredictStreamed([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
absl::AnyInvocable\<[void]{.keywordtype}(absl::StatusOr\<PredictResponse\>)\>
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  response\_callback) = 0;
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [virtual]{.keyword} absl::Status
MultiInference([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [const]{.keyword} MultiInferenceRequest&
request,
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  MultiInferenceResponse\* response) = 0;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [virtual]{.keyword} absl::Status
GetModelMetadata([const]{.keyword} GetModelMetadataRequest& request,
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  GetModelMetadataResponse\* response) = 0;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// Returns true iff this servable supports
paging.]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// Paging is a process of moving model data
(i.e., variables and executables)]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// between devices\' HBM and host RAM.
Servables that support paging can]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// time-share the available HBM and be
paged in and out of the HBM according]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// to a paging policy.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// Note that even if a Servable supports
paging, it is up to a Server]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// implementation to make active (or any!)
use of the paging functionality.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
SupportsPaging() [const]{.keyword};
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// Pages out all variables and executables
owned by this servable from]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// devices\' HBM to host RAM.]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// After this method returns, all requests
return an error until \`Resume()\` is]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// called to bring the states back to
device memory.]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// If the suspension fails, the model is in
an unspecified state and must be]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [// unloaded and loaded again for it to be
useful.]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// This method may only be invoked if
SupportsPaging() returns true.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [virtual]{.keyword} absl::Status Suspend();
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [// Inverse of \`Suspend()\`. Synchronously
pages in all variables and]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [// executables owned by this servable back
to devices\' HBM.]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// Returns an error if the servable is not
in a suspended state or resumption]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// failed. If the resumption fails, the
model is in an unspecified state and]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [// must be unloaded and loaded again for it
to be useful.]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [// This method may only be invoked if
SupportsPaging() returns true.]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [virtual]{.keyword} absl::Status Resume();
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// Metadata of this servable. Currently
matches the fields in]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [// \`ServableId\`.]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [const]{.keyword} std::string name\_;
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [const]{.keyword} int64\_t version\_;
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [const]{.keyword} [bool]{.keywordtype}
is\_critical\_;
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} };
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} [// An \"empty\" servable where there\'s no
model associated with the servable. All]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} [// methods will return an error.]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} [// Empty servables can be used in places
where a servable is expected but we]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} [// don\'t need to load any models. For
example, Model Server currently expects]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} [// each task to have at least one servable
loaded, but Pathways Serving requires]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} [// only the controller task to initiate
loading servables. So we use empty]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} [// servables in non-zero tasks to make sure
non-zero tasks don\'t load anything.]{.comment}
:::

::: {.line}
[]{#l00184}[
[184](classtensorflow_1_1serving_1_1EmptyServable.html){.line}]{.lineno} [class
]{.keyword}[EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.code}
: [public]{.keyword}
[Servable](classtensorflow_1_1serving_1_1Servable.html){.code} {
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} 
[EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html){.code}();
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  absl::Status Classify([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [const]{.keyword} ClassificationRequest&
request,
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  ClassificationResponse\* response)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  }
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  absl::Status Regress([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [const]{.keyword} RegressionRequest&
request,
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  RegressionResponse\* response)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  }
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} 
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  absl::Status Predict([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [const]{.keyword} PredictRequest& request,
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  PredictResponse\* response)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  }
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} 
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} 
absl::StatusOr\<std::unique\_ptr\<PredictStreamedContext\>\>
PredictStreamed(
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} 
absl::AnyInvocable\<[void]{.keywordtype}(absl::StatusOr\<PredictResponse\>)\>
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  response\_callback) {
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  }
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  absl::Status
MultiInference([const]{.keyword}
[RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [const]{.keyword} MultiInferenceRequest&
request,
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  MultiInferenceResponse\* response)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  }
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} 
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  absl::Status
GetModelMetadata([const]{.keyword} GetModelMetadataRequest& request,
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  GetModelMetadataResponse\* response)[
override ]{.keyword}{
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  [return]{.keywordflow} error\_;
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  }
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} 
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  absl::Status error\_;
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} };
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} 
:::

::: {.line}
[]{#l00231}[ 231]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVABLE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1EmptyServable_html .ttc}
::: {.ttname}
[tensorflow::serving::EmptyServable](classtensorflow_1_1serving_1_1EmptyServable.html)
:::

::: {.ttdef}
**Definition:** servable.h:184
:::
:::

::: {#aclasstensorflow_1_1serving_1_1PredictStreamedContext_html .ttc}
::: {.ttname}
[tensorflow::serving::PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html)
:::

::: {.ttdef}
**Definition:** servable.h:47
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

::: {#aclasstensorflow_1_1serving_1_1SingleRequestPredictStreamedContext_html .ttc}
::: {.ttname}
[tensorflow::serving::SingleRequestPredictStreamedContext](classtensorflow_1_1serving_1_1SingleRequestPredictStreamedContext.html)
:::

::: {.ttdef}
**Definition:** servable.h:65
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
