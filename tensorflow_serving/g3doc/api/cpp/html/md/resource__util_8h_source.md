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
resource\_util.h
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
[]{#l00016}[ 16]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// Arithmetic and comparison operations on
resource allocations.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// The implementations assume that the number
of devices, and the number of]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// instances of each device, are both quite
small (fewer than, say, 10). Their]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// computational complexity in these
dimensions leaves room for improvement.]{.comment}
:::

::: {.line}
[]{#l00034}[
[34](classtensorflow_1_1serving_1_1ResourceUtil.html){.line}]{.lineno} [class
]{.keyword}[ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.code}
{
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00036}[
[36](structtensorflow_1_1serving_1_1ResourceUtil_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1ResourceUtil_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// The devices managed by the system, and
the number of instances of each.]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  std::map\<string, uint32\> devices;
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  };
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [explicit]{.keyword}
[ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.code}([const]{.keyword}
[Options](structtensorflow_1_1serving_1_1ResourceUtil_1_1Options.html){.code}&
options);
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [virtual]{.keyword}
\~[ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// Determines whether \'allocation\' is
valid, i.e.:]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// 1. It only refers to valid devices, i.e.
those supplied via Options.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// 2. Each entry is either unbound, or bound
to a valid device instance.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// 3. No distinct Resource entry occurs
twice, i.e. resource is a key.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// All other methods in this class assume
their inputs are valid (i.e. they]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// have undefined behavior otherwise), and
guarantee to produce valid outputs.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [virtual]{.keyword} Status
VerifyValidity([const]{.keyword} ResourceAllocation& allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// Determine if the override\_allocation\'s
device set is a subset of]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// base\_allocation. Only used by
controller]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  Status VerifyOverrideDeviceValidity(
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword} ResourceAllocation&
base\_allocation,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword} ResourceAllocation&
override\_allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Verifies whether \'resource\' is valid,
i.e. it only refers to valid devices,]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// i.e. those supplied via
Options.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  Status
VerifyResourceValidity([const]{.keyword} Resource& resource)
[const]{.keyword};
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Converts \'allocation\' to normal form,
meaning:]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// 1. It has no entries with quantity
0.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// 2. Resources of a device that has exactly
one instance are bound to that]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// instance.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [virtual]{.keyword} ResourceAllocation
Normalize(
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} ResourceAllocation&
allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// Determines whether \'allocation\' is in
normal form, as defined above.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
IsNormalized([const]{.keyword} ResourceAllocation& allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Determines whether \'allocation\' is
bound, defined as follows:]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// 1. An individual entry is bound iff a
device\_instance is supplied.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// 2. An allocation is bound iff every entry
is bound.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [bool]{.keywordtype}
IsBound([const]{.keyword} ResourceAllocation& allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// Creates a bound resource with the given
values. For single-instance]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// resources (which is a common case, e.g.
main memory) the \'instance\']{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// argument can be omitted.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  Resource
CreateBoundResource([const]{.keyword} [string]{.keywordtype}& device,
[const]{.keyword} [string]{.keywordtype}& kind,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  uint32 device\_instance = 0)
[const]{.keyword};
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// Gets the quantity of \'resource\' present
in \'allocation\'. Returns 0 if]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// \'resource\' is not mentioned in
\'allocation\', since unmentioned resources]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// are implicitly zero.]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  uint64\_t GetQuantity([const]{.keyword}
Resource& resource,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [const]{.keyword} ResourceAllocation&
allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Sets the quantity of \'resource\' to
\'quantity\' in \'allocation\', overwriting]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// any existing quantity.]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [void]{.keywordtype}
SetQuantity([const]{.keyword} Resource& resource, uint64\_t quantity,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  ResourceAllocation\* allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [// Adds \'to\_add\' to \'base\'.]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// Keeps bound and unbound entries separate.
For example, adding]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// {(GPU/\<no\_instance\>/RAM/8)} to
{(GPU/instance\_0/RAM/16),]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [// (GPU/\<no\_instance\>/RAM/4)} yields
{(GPU/instance\_0/RAM/16),]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [//
(GPU/\<no\_instance\>/RAM/12)}.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [void]{.keywordtype} Add([const]{.keyword}
ResourceAllocation& to\_add, ResourceAllocation\* base)
[const]{.keyword};
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// Attempts to subtract \'to\_subtract\'
from \'base\'. Like Add(), keeps bound and]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// unbound entries separate. Returns true
and mutates \'base\' iff the]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// subtraction is legal, i.e. no negative
quantities (which cannot be]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// represented) are produced.]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [bool]{.keywordtype}
Subtract([const]{.keyword} ResourceAllocation& to\_subtract,
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  ResourceAllocation\* base)
[const]{.keyword};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [// Multiplies every resource quantity in
\'base\' by \'multiplier\'. Keeps bound]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// and unbound entries separate.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [void]{.keywordtype} Multiply(uint64\_t
multiplier, ResourceAllocation\* base) [const]{.keyword};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// Determines whether two
ResourceAllocation objects are identical (modulo]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// normalization).]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [bool]{.keywordtype} Equal([const]{.keyword}
ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// Determines whether two Resource objects
are identical (modulo]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// normalization).]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [bool]{.keywordtype}
ResourcesEqual([const]{.keyword} Resource& lhs, [const]{.keyword}
Resource& rhs) [const]{.keyword};
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// Takes a (bound or unbound) allocation
\'lhs\' and a \*bound\* allocation \'rhs\'.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [// Returns true iff for each entry in
\'lhs\', either:]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// 1. The entry is bound and its quantity
is \<= the corresponding one in]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// \'rhs\'.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [// 2. The entry is unbound, and there
exists an instance I of the device s.t.]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// the unbound quantity in \'lhs\' is \<=
the quantity in \'rhs\' bound to I.]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// IMPORTANT: Assumes \'rhs\' is bound; has
undefined behavior otherwise.]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [bool]{.keywordtype}
LessThanOrEqual([const]{.keyword} ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [// Converts a (potentially) unbound
allocation into a bound one, by taking]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// each unbound quantity and binding it to
every instance of the device.]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// (Existing bound quantities are
preserved.)]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// For example, if there is one CPU and two
GPUs then overbinding]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// {(CPU/instance\_0/RAM/16),
(GPU/\<no\_instance\>/RAM/4)} yields]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// {(CPU/instance\_0/RAM/16),
(GPU/instance\_0/RAM/4), (GPU/instance\_1/RAM/4)}.]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [// This operation is useful for reasoning
about monotonicity and availability]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// of resources, not as a means to
permanently bind resources to devices]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// (because it binds resources redundantly
to all device instances).]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  ResourceAllocation
Overbind([const]{.keyword} ResourceAllocation& allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// Gets the max of the two
ResourceAllocations by taking the max of every]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// paired entry and keep all the unpaired
entries in the max. Like the Add()]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [// and Subtract() methods, this keeps the
bound and unbound resources]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// separate.]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// E.g.]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// Max({(GPU/instance\_0/RAM/8),]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [//
(CPU/instance\_0/processing\_in\_millicores/100)},]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// {(GPU/instance\_0/RAM/16),
(CPU/\<no\_instance\>/RAM/4)}) returns]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// {(GPU/instance\_0/RAM/16),
(CPU/instance\_0/processing\_in\_millicores/100),]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// (CPU/\<no\_instance\>/RAM/4)}]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  ResourceAllocation Max([const]{.keyword}
ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} 
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [// Gets the min of the two
ResourceAllocations by taking the min of every]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// paired entry and remove all the unpaired
entries in the result. Like the]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// Max() method, this keeps the bound and
unbound resources separate.]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [// E.g.]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [// Min(]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [// {(GPU/instance\_0/RAM/8),
(CPU/instance\_0/processing\_in\_millicores/100)},]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [// {(GPU/instance\_0/RAM/16),
(CPU/\<no\_instance\>/RAM/4)}]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [// )]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// returns]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [// {(GPU/instance\_0/RAM/8)}]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  ResourceAllocation Min([const]{.keyword}
ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// The implementation of
ResourceUtil::Normalize().]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [// Converts \'allocation\' to normal form,
meaning:]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [// 1. It has no entries with quantity
0.]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// 2. Resources of a device that has
exactly one instance are bound to that]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [// instance.]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  ResourceAllocation
NormalizeResourceAllocation(
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [const]{.keyword} ResourceAllocation&
allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} 
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [enum class]{.keyword} DCHECKFailOption {
kDoDCHECKFail, kDoNotDCHECKFail };
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} 
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [// Wraps fn() with the option to
DCHECK-fail.]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  Status
VerifyFunctionInternal(std::function\<Status()\> fn,
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  DCHECKFailOption dcheck\_fail\_option)
[const]{.keyword};
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// Converts \'resource\' to normal form,
i.e. ensures that if the device has]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// exactly one instance, the resource is
bound to that instance.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  Resource NormalizeResource([const]{.keyword}
Resource& resource) [const]{.keyword};
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [// Determines whether \'resource\' is
normalized. Assumes \'resource\' is valid.]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [bool]{.keywordtype}
IsResourceNormalized([const]{.keyword} Resource& resource)
[const]{.keyword};
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} 
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// Like IsBound(), but assumes the input is
normalized.]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [bool]{.keywordtype}
IsBoundNormalized([const]{.keyword} ResourceAllocation& allocation)
[const]{.keyword};
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} 
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [// Like Add(), but assumes the input is
normalized and produces normalized]{.comment}
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [// output.]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [void]{.keywordtype}
AddNormalized([const]{.keyword} ResourceAllocation& to\_add,
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  ResourceAllocation\* base)
[const]{.keyword};
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} 
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [// Like Subtract(), but assumes the input
is normalized and produces]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [// normalized output.]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [bool]{.keywordtype}
SubtractNormalized([const]{.keyword} ResourceAllocation& to\_subtract,
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  ResourceAllocation\* base)
[const]{.keyword};
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} 
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [// Like Multiply(), but assumes the input
is normalized and produces]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [// normalized output.]{.comment}
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [void]{.keywordtype}
MultiplyNormalized(uint64\_t multiplier, ResourceAllocation\* base)
[const]{.keyword};
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [// Like Equal(), but assumes the input is
normalized.]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [bool]{.keywordtype}
EqualNormalized([const]{.keyword} ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// Like ResourcesEqual(), but assumes the
input is normalized.]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [bool]{.keywordtype}
ResourcesEqualNormalized([const]{.keyword} Resource& lhs,
[const]{.keyword} Resource& rhs) [const]{.keyword};
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} 
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  [// Like LessThanOrEqual(), but assumes the
input is normalized.]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  [bool]{.keywordtype}
LessThanOrEqualNormalized([const]{.keyword} ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} 
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  [// Like Overbind(), but assumes the input
is normalized and produces]{.comment}
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  [// normalized output.]{.comment}
:::

::: {.line}
[]{#l00226}[ 226]{.lineno}  ResourceAllocation OverbindNormalized(
:::

::: {.line}
[]{#l00227}[ 227]{.lineno}  [const]{.keyword} ResourceAllocation&
allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00228}[ 228]{.lineno} 
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  [// Like Max(), but assumes the input are
normalized and produces a normalized]{.comment}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  [// result.]{.comment}
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  ResourceAllocation
MaxNormalized([const]{.keyword} ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [// Like Min(), but assumes the input are
normalized and produces a normalized]{.comment}
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [// result.]{.comment}
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  ResourceAllocation
MinNormalized([const]{.keyword} ResourceAllocation& lhs,
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  [const]{.keyword} ResourceAllocation& rhs)
[const]{.keyword};
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} 
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  [// The implementation of
ResourceUtil::IsNormalized().]{.comment}
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  [bool]{.keywordtype}
IsResourceAllocationNormalized(
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  [const]{.keyword} ResourceAllocation&
allocation) [const]{.keyword};
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} 
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  [const]{.keyword} std::map\<string, uint32\>
devices\_;
:::

::: {.line}
[]{#l00244}[ 244]{.lineno} 
:::

::: {.line}
[]{#l00245}[ 245]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.code});
:::

::: {.line}
[]{#l00246}[ 246]{.lineno} };
:::

::: {.line}
[]{#l00247}[ 247]{.lineno} 
:::

::: {.line}
[]{#l00248}[ 248]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00249}[ 249]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00250}[ 250]{.lineno} 
:::

::: {.line}
[]{#l00251}[ 251]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_UTIL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ResourceUtil_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html)
:::

::: {.ttdef}
**Definition:** resource\_util.h:34
:::
:::

::: {#astructtensorflow_1_1serving_1_1ResourceUtil_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourceUtil::Options](structtensorflow_1_1serving_1_1ResourceUtil_1_1Options.html)
:::

::: {.ttdef}
**Definition:** resource\_util.h:36
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
