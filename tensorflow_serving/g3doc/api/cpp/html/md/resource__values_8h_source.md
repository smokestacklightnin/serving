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
-   [resources](dir_707e45924ba4592177e9789700f2f284.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
resource\_values.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2016 Google Inc. All Rights
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
[]{#l00016}[ 16]{.lineno} [// Standard values to describe resources, to
be used for the string types in]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// resources.proto. These values should be
used whenever applicable, to avoid]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [// vocabulary mismatches.]{.comment}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} 
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_VALUES\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#define
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_VALUES\_H\_]{.preprocessor}
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
[]{#l00026}[ 26]{.lineno} [// Standard device types.]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}device\_types {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// The primary devices such as CPU(s) and
main memory, as well as aspects of the]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// server as a whole.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kMain;
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Graphics processing unit(s).]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kGpu;
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// TPU(s).]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kTpu;
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} } [// namespace device\_types]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// Standard resource kinds.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [namespace ]{.keyword}resource\_kinds {
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// If a server can accommodate at most N
models, depicted as the server having N]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// \"model slots\", this is the number of
slots needed or allocated.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kNumModelSlots;
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// If a server can accommodate at most N LoRA
adapter models.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kNumLoraSlots;
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// RAM in bytes.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// NOTES:]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// - For TPU or GPU device, The kHeapRamBytes
and kStackRamBytes are aggregated]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// to this kind.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// - In GPU device, this only represents the
remaining RAM used for model]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// variables and inference requests. Total
GPU RAM includes remaining RAM and]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// reserved RAM below.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kRamBytes;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// Peak RAM in bytes, collected from Tcmalloc
peak metric.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kPeakRamBytes;
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// RAM allocated on the heap.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kHeapRamBytes;
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// RAM reserved on the stack.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kStackRamBytes;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// Only available for GPU device. Total
reserved RAM used for compilation]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// program and GPU system usage.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kReservedRamBytes;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// Only available for GPU device. RAM
reserved for GPU system usage.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kSystemRamBytes;
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// Only available for GPU device. The
compilation program ram usage.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kModelBinaryRamBytes;
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// Fraction of a processing unit\'s cycles,
in thousandths.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [extern]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kProcessingMillis;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} } [// namespace resource\_kinds]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_VALUES\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
