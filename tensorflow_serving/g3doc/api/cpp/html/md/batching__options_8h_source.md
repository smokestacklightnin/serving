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
batching\_options.h
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
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_OPTIONS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_OPTIONS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [// Batching options.]{.comment}
:::

::: {.line}
[]{#l00025}[
[25](structtensorflow_1_1serving_1_1BatchingOptions.html){.line}]{.lineno} [struct
]{.keyword}[BatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html){.code}
{
:::

::: {.line}
[]{#l00026}[ 26]{.lineno}  [// If set, restricts the allowed tensor
batch sizes.]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [// When the batch scheduler forms a batch of
size N, the batch size is rounded]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [// up to the smallest value M in
\'allowed\_batch\_sizes\' s.t. M \>= N. The]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [// tensors submitted to the \"Run()\" call
are padded with M-N repeats of one of]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [// the first N entries (i.e. a guaranteed
valid entry). The last M-N entries]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [// of the output tensors are
ignored.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// This option is useful when the underlying
platform has some per-batch-size]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [// overhead, to limit the number of distinct
batch sizes that can occur. It]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [// may be sensible to use an exponential
sequence e.g. \[8, 16, 32, \...,]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// max\_batch\_size\], a linear one e.g.
\[100, 200, 300, \..., max\_batch\_size\], or]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// perhaps a hybrid e.g. \[8, 16, 32, 64,
100, 200, 300, \..., max\_batch\_size\].]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// IMPORTANT: The entries must be in
increasing order.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// IMPORTANT: The final entry in
\'allowed\_batch\_sizes\' must equal the maximum]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// batch size parameter supplied to the
batch scheduler.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// If left empty, no rounding/padding is
performed.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  std::vector\<int\> allowed\_batch\_sizes;
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// If set to true, padding is performed for
tensors of the same name]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// but with unequal dimensions (modulo
zeroth dimension), so that]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// all tensors of the same name have equal
dim sizes.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// For each tensor its first element is used
as padding value.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// For example:]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// given input tensors of shapes \[1, 500,
101\], \[2, 300, 101\], \[1, 400, 101\]]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// they will be padded to shapes \[1, 500,
101\], \[2, 500, 101\], \[1, 500, 101\].]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// Padding is not performed in zeroth
dimension.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Supported tensor datatypes:]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// DT\_FLOAT, DT\_DOUBLE, DT\_INT8,
DT\_UINT8, DT\_INT16,]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// DT\_UINT16, DT\_INT32, DT\_INT64,
DT\_COMPLEX64, DT\_COMPLEX128,]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// DT\_STRING, DT\_BOOL, DT\_QINT8,
DT\_QUINT8, DT\_QINT16,]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// DT\_QUINT16, DT\_QINT32, DT\_HALF,
DT\_RESOURCE.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// Supported ranks: from 1 to 6.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// This option is useful when using
recurrent models(like LSTMs) with serving.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [// These models typically accept
variable-length inputs and when]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// training them typical strategy is to save
sequence lengths for decoding]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// and pad those variable-length dims to
maximum in batch.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// So, this option is used to achieve
similar behavior]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// when serving with batching, it is assumed
that sequence lengths]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// have already been saved.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// If tensors with the same name have
different shapes]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// (modulo zeroth dimension) and this option
is set to false,]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// then error Status will be
returned.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [bool]{.keywordtype}
pad\_variable\_length\_inputs = [false]{.keyword};
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} };
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_BATCHING\_BATCHING\_OPTIONS\_H\_]{.comment}
:::

::: {#astructtensorflow_1_1serving_1_1BatchingOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::BatchingOptions](structtensorflow_1_1serving_1_1BatchingOptions.html)
:::

::: {.ttdef}
**Definition:** batching\_options.h:25
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
