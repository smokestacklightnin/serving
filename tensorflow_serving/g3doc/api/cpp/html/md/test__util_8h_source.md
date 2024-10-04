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
-   [test\_util](dir_c175379b7650f00978e0d110b2392832.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
test\_util.h
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
TENSORFLOW\_SERVING\_TEST\_UTIL\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_TEST\_UTIL\_TEST\_UTIL\_H\_]{.preprocessor}
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
\"google/protobuf/message.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"google/protobuf/text\_format.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/protobuf.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/public/session\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// Creates a proto message of type T from a
textual representation.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} T CreateProto([const]{.keyword}
[string]{.keywordtype}& textual\_proto);
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// Return an absolute runfiles srcdir given a
path relative to]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// tensorflow.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [string]{.keywordtype}
TensorflowTestSrcDirPath([const]{.keyword} [string]{.keywordtype}&
relative\_path);
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// Return an absolute runfiles srcdir given a
path relative to]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// tensorflow/contrib.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [string]{.keywordtype}
ContribTestSrcDirPath([const]{.keyword} [string]{.keywordtype}&
relative\_path);
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// Return an absolute runfiles srcdir given a
path relative to]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// tensorflow\_serving.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [string]{.keywordtype}
TestSrcDirPath([const]{.keyword} [string]{.keywordtype}&
relative\_path);
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// Simple implementation of a proto matcher
comparing string representations.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// IMPORTANT: Only use this for protos whose
textual representation is]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// deterministic (that may not be the case
for the map collection type).]{.comment}
:::

::: {.line}
[]{#l00056}[
[56](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html){.line}]{.lineno} [class
]{.keyword}[ProtoStringMatcher](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html){.code}
{
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [explicit]{.keyword}
[ProtoStringMatcher](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html){.code}([const]{.keyword}
[string]{.keywordtype}& expected);
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [explicit]{.keyword}
[ProtoStringMatcher](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html){.code}([const]{.keyword}
google::protobuf::Message& expected);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Message\>
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [bool]{.keywordtype}
MatchAndExplain([const]{.keyword} Message& p,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  ::testing::MatchResultListener\* [/\*
listener \*/]{.comment}) [const]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [void]{.keywordtype}
DescribeTo(::std::ostream\* os)[ const ]{.keyword}{ \*os \<\<
expected\_; }
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [void]{.keywordtype}
DescribeNegationTo(::std::ostream\* os)[ const ]{.keyword}{
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  \*os \<\< [\"not equal to expected message:
\"]{.stringliteral} \<\< expected\_;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  }
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [const]{.keyword} [string]{.keywordtype}
expected\_;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} };
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// Polymorphic matcher to compare any two
protos.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} inline
::testing::PolymorphicMatcher\<ProtoStringMatcher\> EqualsProto(
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [const]{.keyword} [string]{.keywordtype}& x)
{
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  return
::testing::MakePolymorphicMatcher([ProtoStringMatcher](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html){.code}(x));
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} }
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// Polymorphic matcher to compare any two
protos.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} inline
::testing::PolymorphicMatcher\<ProtoStringMatcher\> EqualsProto(
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [const]{.keyword} google::protobuf::Message&
x) {
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  return
::testing::MakePolymorphicMatcher(ProtoStringMatcher(x));
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} }
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [// Implementation details. API readers need
not read.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} T CreateProto([const]{.keyword}
[string]{.keywordtype}& textual\_proto) {
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  T proto;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
CHECK(protobuf::TextFormat::ParseFromString(textual\_proto, &proto));
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [return]{.keywordflow} proto;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Message\>
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [bool]{.keywordtype}
ProtoStringMatcher::MatchAndExplain(
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [const]{.keyword} Message& p,
::testing::MatchResultListener\* [/\* listener \*/]{.comment})[ const
]{.keyword}{
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// Need to CreateProto and then print as
string so that the formatting]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [// matches exactly.]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [return]{.keywordflow} p.SerializeAsString()
==
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
CreateProto\<Message\>(expected\_).SerializeAsString();
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} }
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// An implementation of
thread::ThreadPoolInterface that delegates calls to]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// thread::ThreadPool but]{.comment}
:::

::: {.line}
[]{#l00107}[
[107](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool.html){.line}]{.lineno} [class
]{.keyword}[CountingThreadPool](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool.html){.code}
: [public]{.keyword} thread::ThreadPoolInterface {
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
[CountingThreadPool](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool.html){.code}(Env\*
env, [const]{.keyword} [string]{.keywordtype}& name, [int]{.keywordtype}
num\_threads)
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  : thread\_pool\_(env, name, num\_threads),
num\_scheduled\_(0) {}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
\~[CountingThreadPool](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [void]{.keywordtype}
Schedule(std::function\<[void]{.keywordtype}()\> fn)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  {
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  num\_scheduled\_++;
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  }
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  thread\_pool\_.Schedule(fn);
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  }
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [int]{.keywordtype} NumThreads()[ const
override ]{.keyword}{ [return]{.keywordflow}
thread\_pool\_.NumThreads(); }
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [int]{.keywordtype} CurrentThreadId()[ const
override ]{.keyword}{
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [return]{.keywordflow}
thread\_pool\_.CurrentThreadId();
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  }
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [int]{.keywordtype} NumScheduled()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  {
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [return]{.keywordflow} num\_scheduled\_;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  }
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  }
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  thread::ThreadPool thread\_pool\_;
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [mutable]{.keyword} mutex mu\_;
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  int32 num\_scheduled\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} };
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} } [// namespace test\_util]{.comment}
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
TENSORFLOW\_SERVING\_TEST\_UTIL\_TEST\_UTIL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1CountingThreadPool_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::CountingThreadPool](classtensorflow_1_1serving_1_1test__util_1_1CountingThreadPool.html)
:::

::: {.ttdef}
**Definition:** test\_util.h:107
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::ProtoStringMatcher](classtensorflow_1_1serving_1_1test__util_1_1ProtoStringMatcher.html)
:::

::: {.ttdef}
**Definition:** test\_util.h:56
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
