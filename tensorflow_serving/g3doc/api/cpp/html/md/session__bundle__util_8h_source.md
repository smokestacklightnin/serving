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
-   [session\_bundle](dir_545072a0b62e8d32e4be92843450628a.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
session\_bundle\_util.h
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
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_SESSION\_BUNDLE\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_SESSION\_BUNDLE\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/cc/saved\_model/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/session\_bundle/manifest\_proto.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/session\_bundle/session\_bundle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}session\_bundle {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Interface from bundle\_shim.h]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// Converts signatures in the MetaGraphDef
into a SignatureDefs in the]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// MetaGraphDef.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} Status
ConvertSignaturesToSignatureDefs(MetaGraphDef\* meta\_graph\_def);
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// Converts a SessionBundle to a
SavedModelBundle.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} Status ConvertSessionBundleToSavedModelBundle(
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  SessionBundle& session\_bundle,
SavedModelBundle\* saved\_model\_bundle);
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// Loads a SavedModel from either a
session-bundle path or a SavedModel bundle]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// path. If \`is\_session\_bundle\` is not a
nullptr, sets it to \`true\` iff]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// SavedModel was up-converted and loaded
from a SessionBundle.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// \`is\_session\_bundle\` value should not
be used if error is returned.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} Status LoadSessionBundleOrSavedModelBundle(
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const]{.keyword} SessionOptions&
session\_options, [const]{.keyword} RunOptions& run\_options,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
export\_dir, [const]{.keyword} std::unordered\_set\<string\>& tags,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  SavedModelBundle\* bundle,
[bool]{.keywordtype}\* is\_session\_bundle = [nullptr]{.keyword});
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// Loads a SavedModel from either a
session-bundle path or a SavedModel bundle]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// path. If \`is\_session\_bundle\` is not a
nullptr, sets it to \`true\` iff]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// SavedModel was up-converted and loaded
from a SessionBundle.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// \`is\_session\_bundle\` value should not
be used if error is returned. If]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// \`maybe\_load\_saved\_model\_config\` is
set and]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [//
{export\_dir}/assets.extra/saved\_model\_config.pb exists, the configs
defined]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// in saved\_model\_config.pb will override
associated values specified in]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// \`session\_options\`.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} Status LoadSessionBundleOrSavedModelBundle(
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword} SessionOptions&
session\_options, [const]{.keyword} RunOptions& run\_options,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
export\_dir, [const]{.keyword} std::unordered\_set\<string\>& tags,
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [bool]{.keywordtype}
maybe\_load\_saved\_model\_config, SavedModelBundle\* bundle,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [bool]{.keywordtype}\* is\_session\_bundle =
[nullptr]{.keyword});
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// Interface from
session\_bundle.h]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// Similar to the
LoadSessionBundleFromPath(), but also allows the session run]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// invocations for the restore and init ops
to be configured with]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// tensorflow::RunOptions.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// This method is EXPERIMENTAL and may change
or be removed.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} Status
LoadSessionBundleFromPathUsingRunOptions(
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} SessionOptions&
session\_options, [const]{.keyword} RunOptions& run\_options,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword} StringPiece export\_dir,
SessionBundle\* bundle);
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// Interface from signature.h]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// (Re)set Signatures in a
MetaGraphDef.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} Status SetSignatures([const]{.keyword}
Signatures& signatures,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  tensorflow::MetaGraphDef\* meta\_graph\_def);
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// Gets a ClassificationSignature from a
MetaGraphDef\'s default signature.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// Returns an error if the default signature
is not a ClassificationSignature,]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// or does not exist.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} Status GetClassificationSignature(
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [const]{.keyword} tensorflow::MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  ClassificationSignature\* signature);
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [// Gets a RegressionSignature from a
MetaGraphDef\'s default signature.]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [// Returns an error if the default signature
is not a RegressionSignature,]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [// or does not exist.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} Status
GetRegressionSignature([const]{.keyword} tensorflow::MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  RegressionSignature\* signature);
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [// Runs a classification using the provided
signature and initialized Session.]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [// input: input batch of items to
classify]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// classes: output batch of classes; may be
null if not needed]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} [// scores: output batch of scores; may be
null if not needed]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// Validates sizes of the inputs and outputs
are consistent (e.g., input]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// batch size equals output batch
sizes).]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// Does not do any type
validation.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} Status RunClassification([const]{.keyword}
ClassificationSignature& signature,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [const]{.keyword} Tensor& input, Session\*
session, Tensor\* classes,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  Tensor\* scores);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [// Runs regression using the provided
signature and initialized Session.]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [// input: input batch of items to run the
regression model against]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// output: output targets]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// Validates sizes of the inputs and outputs
are consistent (e.g., input]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// batch size equals output batch
sizes).]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [// Does not do any type
validation.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} Status RunRegression([const]{.keyword}
RegressionSignature& signature, [const]{.keyword} Tensor& input,
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  Session\* session, Tensor\* output);
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [// Gets a named Signature from a
MetaGraphDef.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// Returns an error if a Signature with the
given name does not exist.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} Status GetNamedSignature([const]{.keyword}
[string]{.keywordtype}& name,
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [const]{.keyword} tensorflow::MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  Signature\* default\_signature);
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} } [// namespace session\_bundle]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_SESSION\_BUNDLE\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
