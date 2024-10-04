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
-   [model\_servers](dir_5bce3ff2a459f05fa975e832b2676e62.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
server\_init.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2022 Google Inc. All Rights
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
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_INIT\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_INIT\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"google/protobuf/any.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/apis/prediction\_service.grpc.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/http\_rest\_api\_handler\_base.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/prediction\_service\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}init {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [using]{.keyword}
SetupPlatformConfigMapForTensorFlowFnType =
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  Status (\*)([const]{.keyword}
SessionBundleConfig&, PlatformConfigMap&);
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [using]{.keyword}
UpdatePlatformConfigMapForTensorFlowFnType =
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  Status (\*)(PlatformConfigMap&);
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [using]{.keyword}
CreateHttpRestApiHandlerFnType =
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  std::unique\_ptr\<HttpRestApiHandlerBase\>
(\*)(int, ServerCore\*);
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [using]{.keyword}
CreatePredictionServiceFnType =
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
std::unique\_ptr\<PredictionService::Service\> (\*)(
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [const]{.keyword} PredictionServiceOptions&);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} Status
SetupPlatformConfigMapForTensorFlowImpl([const]{.keyword}
SessionBundleConfig&,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  PlatformConfigMap&);
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} Status
UpdatePlatformConfigMapForTensorFlowImpl(PlatformConfigMap&);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} std::unique\_ptr\<HttpRestApiHandlerBase\>
CreateHttpRestApiHandlerImpl(
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [int]{.keywordtype}, ServerCore\*);
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} std::unique\_ptr\<PredictionService::Service\>
CreatePredictionServiceImpl(
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [const]{.keyword} PredictionServiceOptions&);
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// Register the tensorflow serving
functions.]{.comment}
:::

::: {.line}
[]{#l00052}[
[52](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.line}]{.lineno} [class
]{.keyword}[TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.code}
{
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [virtual]{.keyword}
\~[TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// Get the registry singleton.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [static]{.keyword}
[TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.code}\*
GetRegistry() {
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [static]{.keyword} [auto]{.keyword}\*
registration = [new]{.keyword}
[TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.code}();
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [return]{.keywordflow} registration;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  }
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// The tensorflow serving function
registration. For TFRT, the TFRT]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// registration will overwrite the
Tensorflow registration.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [void]{.keywordtype} Register(
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  absl::string\_view type,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  SetupPlatformConfigMapForTensorFlowFnType
setup\_platform\_config\_map\_func,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  UpdatePlatformConfigMapForTensorFlowFnType
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  update\_platform\_config\_map\_func,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  CreateHttpRestApiHandlerFnType
create\_http\_rest\_api\_handler\_func,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  CreatePredictionServiceFnType
create\_prediction\_service\_func);
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [bool]{.keywordtype} IsRegistered()[ const
]{.keyword}{ [return]{.keywordflow} !registration\_type\_.empty(); }
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  SetupPlatformConfigMapForTensorFlowFnType
GetSetupPlatformConfigMap()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [return]{.keywordflow}
setup\_platform\_config\_map\_;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  }
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  UpdatePlatformConfigMapForTensorFlowFnType
GetUpdatePlatformConfigMap()[]{.keyword}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [ const ]{.keyword}{
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [return]{.keywordflow}
update\_platform\_config\_map\_;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  }
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  CreateHttpRestApiHandlerFnType
GetCreateHttpRestApiHandler()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [return]{.keywordflow}
create\_http\_rest\_api\_handler\_;
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  }
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  CreatePredictionServiceFnType
GetCreatePredictionService()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [return]{.keywordflow}
create\_prediction\_service\_;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
[TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html){.code}()
{
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  Register([\"tensorflow\"]{.stringliteral},
init::SetupPlatformConfigMapForTensorFlowImpl,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
init::UpdatePlatformConfigMapForTensorFlowImpl,
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  init::CreateHttpRestApiHandlerImpl,
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  init::CreatePredictionServiceImpl);
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  }
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// The registration type, indicating the
platform, e.g. tensorflow, tfrt.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::string registration\_type\_ =
[\"\"]{.stringliteral};
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// Setup the \'TensorFlow\'
PlatformConfigMap from the specified]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// SessionBundleConfig.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  SetupPlatformConfigMapForTensorFlowFnType
setup\_platform\_config\_map\_;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// If the PlatformConfigMap contains the
config for the \'TensorFlow\']{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// platform, update the PlatformConfigMap
when necessary.]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  UpdatePlatformConfigMapForTensorFlowFnType
update\_platform\_config\_map\_;
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// Create an HttpRestApiHandler object that
handles HTTP/REST request APIs]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [// for serving.]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  CreateHttpRestApiHandlerFnType
create\_http\_rest\_api\_handler\_;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// Create a PredictionService object that
handles gRPC request APIs for]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// serving.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  CreatePredictionServiceFnType
create\_prediction\_service\_;
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} };
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} } [// namespace init]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_INIT\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration_html .ttc}
::: {.ttname}
[tensorflow::serving::init::TensorflowServingFunctionRegistration](classtensorflow_1_1serving_1_1init_1_1TensorflowServingFunctionRegistration.html)
:::

::: {.ttdef}
**Definition:** server\_init.h:52
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
