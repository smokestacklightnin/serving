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
regressor.h
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
[]{#l00016}[ 16]{.lineno} [// TensorFlow implementation of the
RegressorInterface.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_REGRESSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_REGRESSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/cc/saved\_model/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/regressor.h\"]{.preprocessor}
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
[]{#l00032}[ 32]{.lineno} [// Create a new RegressorInterface backed by
a TensorFlow SavedModel.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Requires that the default SignatureDef be
compatible with Regression.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} Status CreateRegressorFromSavedModelBundle(
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [const]{.keyword} RunOptions& run\_options,
std::unique\_ptr\<SavedModelBundle\> bundle,
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  std::unique\_ptr\<RegressorInterface\>\*
service);
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// Create a new RegressorInterface backed by
a TensorFlow Session using the]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// specified SignatureDef. Does not take
ownership of the Session.]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// Useful in contexts where we need to avoid
copying, e.g. if created per]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// request. The caller must ensure that the
session and signature live at least]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// as long as the service.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} Status CreateFlyweightTensorFlowRegressor(
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [const]{.keyword} RunOptions& run\_options,
Session\* session,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [const]{.keyword} SignatureDef\* signature,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  std::unique\_ptr\<RegressorInterface\>\*
service);
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// Similar to the above function, but with
additional \'thread\_pool\_options\'.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} Status CreateFlyweightTensorFlowRegressor(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword} RunOptions& run\_options,
Session\* session,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [const]{.keyword} SignatureDef\* signature,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options,
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  std::unique\_ptr\<RegressorInterface\>\*
service);
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// Get a regression signature from the
meta\_graph\_def that\'s either:]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// 1) The signature that model\_spec
explicitly specifies to use.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// 2) The default serving
signature.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// If neither exist, or there were other
issues, an error status is returned.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} Status
GetRegressionSignatureDef([const]{.keyword} ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [const]{.keyword} MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  SignatureDef\* signature);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// Validate a SignatureDef to make sure it\'s
compatible with Regression.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// Populate the input and output tensor
names, if the args are not nullptr.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// NOTE: output\_tensor\_names may already
have elements in it (e.g. when building]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// a full list of outputs from multiple
signatures), and this function will just]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// append to the vector.]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} Status PreProcessRegression([const]{.keyword}
SignatureDef& signature,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [string]{.keywordtype}\* input\_tensor\_name,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  std::vector\<string\>\*
output\_tensor\_names);
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// Validate all results and populate a
RegressionResult.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} Status PostProcessRegressionResult(
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [const]{.keyword} SignatureDef& signature,
[int]{.keywordtype} num\_examples,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword} std::vector\<Tensor\>&
output\_tensors, RegressionResult\* result);
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// Creates SavedModelTensorflowRegressor and
runs Regression on it.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} Status RunRegress([const]{.keyword}
RunOptions& run\_options,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [const]{.keyword} MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
servable\_version,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  Session\* session, [const]{.keyword}
RegressionRequest& request,
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  RegressionResponse\* response,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  thread::ThreadPoolOptions());
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_REGRESSOR\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
