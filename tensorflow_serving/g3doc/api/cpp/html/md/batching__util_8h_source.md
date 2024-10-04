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
batching\_util.h
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
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/strings/str\_cat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/types/span.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/framework/tensor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/sampler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// For batch of inputs calculates maximum dim
sizes across all tensors]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// with the same name.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// These dim sizes are used later to
calculate padding amount for each tensor.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// For example, for batch containing three
tasks with the following inputs]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// (instead of tensors there are their
shapes):]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// task1: {\'tensor\_a\': \[100, 500, 300\],
\'tensor\_b\': \[100\]}]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// task2: {\'tensor\_a\': \[100, 200, 123\],
\'tensor\_b\': \[100\]}]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// task3: {\'tensor\_a\': \[200, 100, 400\],
\'tensor\_b\': \[200\]}]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// the following map will be
generated:]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// {\'tensor\_a\': \[200, 500, 400\],
\'tensor\_b\': \[200\]}]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} std::map\<string, std::vector\<int\>\>
CalculateMaxDimSizes(
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [const]{.keyword}
std::vector\<std::vector\<std::pair\<string, Tensor\>\>\>& batch);
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// Pads tensor so that its shape becomes as
specified in max\_dim\_sizes,]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// except for zeroth dimension, which is left
as is.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// First entry in max\_dim\_sizes is
ignored.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// First element of a tensor is used as
padding value.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// If tensor is empty, an error will be
returned.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// For example given input tensor with shape
\[1, 2, 3, 4\] and max\_dim\_sizes]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// \[1, 2, 5, 8\] function produces
padded\_tensor of shape]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// \[1, 2, 5, 8\], padded with
tensor\[0\]\[0\]\[0\]\[0\] element.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// Supported tensor datatypes:]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// DT\_FLOAT, DT\_DOUBLE, DT\_INT8,
DT\_UINT8, DT\_INT16,]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// DT\_UINT16, DT\_INT32, DT\_INT64,
DT\_COMPLEX64, DT\_COMPLEX128,]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// DT\_STRING, DT\_BOOL, DT\_QINT8,
DT\_QUINT8, DT\_QINT16,]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// DT\_QUINT16, DT\_QINT32, DT\_HALF,
DT\_RESOURCE.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// Supported tensor ranks: from 1 to
6.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} Status AddPadding([const]{.keyword} Tensor&
tensor, absl::Span\<const int\> max\_dim\_sizes,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  Tensor\* padded\_tensor);
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// Returns the smallest entry in
\`allowed\_batch\_sizes\` that is greater than or]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// equal to \`batch\_size\`. If
\`allowed\_batch\_sizes\` is empty, simply returns]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// \`batch\_size\`.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [int]{.keywordtype}
RoundToLowestAllowedBatchSize(absl::Span\<const int\>
allowed\_batch\_sizes,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [int]{.keywordtype} batch\_size);
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// Returns true iff all dims of shape1 are
equal to dims of shape2 starting with]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// the first (not zeroth)
dimension.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// For example, for shapes \[1, 2, 3\] and
\[4, 2, 3\] the result is true.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [bool]{.keywordtype}
AreShapesEqualExceptZeroDim([const]{.keyword} TensorShape& shape1,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword} TensorShape& shape2);
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// Returns the first dimension size (batching
dimension) of each tensor in]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// \`inputs\`. If their first dimension sizes
don\'t match, returns an error.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TensorList, [typename]{.keyword} DimFunc, [typename]{.keyword}
DimSizeFunc\>
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} Status ComputeTensorBatchSize(TensorList
inputs, [size\_t]{.keywordtype}\* size, DimFunc dim\_func,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  DimSizeFunc dim\_size\_func) {
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [if]{.keywordflow} (inputs.empty()) {
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [\"Batching Run() must have at least one
input tensor\"]{.stringliteral});
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  }
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [bool]{.keywordtype} first =
[true]{.keyword};
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
[auto]{.keyword}& tensor : inputs) {
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [if]{.keywordflow} (dim\_func(tensor) == 0) {
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [\"Batching Run() input tensors must have at
least one \"]{.stringliteral}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [\"dimension\"]{.stringliteral});
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  }
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [const]{.keyword} [size\_t]{.keywordtype}
this\_size = dim\_size\_func(tensor, 0);
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [if]{.keywordflow} (first) {
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  \*size = this\_size;
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  first = [false]{.keyword};
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [if]{.keywordflow} (this\_size != \*size) {
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [\"Batching Run() input tensors must have
equal \"]{.stringliteral}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [\"0th-dimension size\"]{.stringliteral});
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  }
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  }
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} }
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Below
utilities are for monitoring purpose
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [// For all metrics: consider adding
breakdowns based on model name or status if]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [// needed. Note that model name is not
available as a session property or on any]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [// of the inputs currently.]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [template]{.keyword} \<[typename]{.keyword}
BatchingTask\>
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [void]{.keywordtype} RecordPaddingSize(int32
padding\_size, int32 execution\_batch\_size) {
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [static]{.keyword} [const]{.keyword}
std::string batching\_task\_name = BatchingTask::Name();
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [static]{.keyword} [auto]{.keyword}\* cell =
tensorflow::monitoring::Sampler\<1\>::New(
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
{absl::StrCat([\"/tensorflow/serving/\"]{.stringliteral},
batching\_task\_name,
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [\"/padding\_size\"]{.stringliteral}),
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [\"Tracks the padding size distribution on
batches.\"]{.stringliteral},
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
[\"execution\_batch\_size\"]{.stringliteral}},
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// Exponential buckets \[1\*2\^0, \...,
1\*2\^13, DBL\_MAX\].]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  monitoring::Buckets::Exponential(1, 2, 14));
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
cell-\>GetCell(absl::StrCat(execution\_batch\_size))
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
-\>Add([static\_cast\<]{.keyword}[double]{.keywordtype}[\>]{.keyword}(padding\_size));
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} }
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [template]{.keyword} \<[typename]{.keyword}
BatchingTask\>
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [void]{.keywordtype}
RecordInputBatchSize(int32 batch\_size) {
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [static]{.keyword} [const]{.keyword}
std::string batching\_task\_name = BatchingTask::Name();
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [static]{.keyword} [auto]{.keyword}\* cell =
tensorflow::monitoring::Sampler\<0\>::New(
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
{absl::StrCat([\"/tensorflow/serving/\"]{.stringliteral},
batching\_task\_name,
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [\"/input\_batch\_size\"]{.stringliteral}),
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [\"Tracks the batch size distribution on the
inputs.\"]{.stringliteral}},
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// Exponential buckets \[1\*2\^0, \...,
1\*2\^13, DBL\_MAX\].]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  monitoring::Buckets::Exponential(1, 2, 14));
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
cell-\>GetCell()-\>Add([static\_cast\<]{.keyword}[double]{.keywordtype}[\>]{.keyword}(batch\_size));
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} }
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [template]{.keyword} \<[typename]{.keyword}
BatchingTask\>
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [void]{.keywordtype}
RecordProcessedBatchSize(int32 batch\_size) {
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [static]{.keyword} [const]{.keyword}
std::string batching\_task\_name = BatchingTask::Name();
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [static]{.keyword} [auto]{.keyword}\* cell =
tensorflow::monitoring::Sampler\<0\>::New(
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
{absl::StrCat([\"/tensorflow/serving/\"]{.stringliteral},
batching\_task\_name,
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
[\"/processed\_batch\_size\"]{.stringliteral}),
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [\"Tracks the batch size distribution on
processing.\"]{.stringliteral}},
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// Exponential buckets \[1\*2\^0, \...,
1\*2\^13, DBL\_MAX\].]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  monitoring::Buckets::Exponential(1, 2, 14));
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
cell-\>GetCell()-\>Add([static\_cast\<]{.keyword}[double]{.keywordtype}[\>]{.keyword}(batch\_size));
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} }
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
