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
bundle\_factory\_test.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"google/protobuf/wrappers.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include \<gtest/gtest.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/core/status\_test\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/sampler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/bundle\_factory\_test\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/test\_util/test\_util.h\"]{.preprocessor}
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
[]{#l00038}[ 38]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [using]{.keyword} test\_util::EqualsProto;
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// The base class for
SessionBundleFactoryTest and SavedModelBundleFactoryTest.]{.comment}
:::

::: {.line}
[]{#l00043}[
[43](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest.html){.line}]{.lineno} [class
]{.keyword}[BundleFactoryTest](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest.html){.code}
: [public]{.keyword} ::testing::Test {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [explicit]{.keyword}
[BundleFactoryTest](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest.html){.code}([const]{.keyword}
[string]{.keywordtype} &export\_dir)
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  : export\_dir\_(export\_dir) {}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [virtual]{.keyword}
\~[BundleFactoryTest](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// Test functions to be used by
subclasses.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [void]{.keywordtype} TestBasic()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [const]{.keyword} SessionBundleConfig config
= GetSessionBundleConfig();
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  std::unique\_ptr\<Session\> session;
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [if]{.keywordflow}
(ExpectCreateBundleFailure()) {
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  EXPECT\_FALSE(CreateSession(config,
&session).ok());
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  }
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  TF\_ASSERT\_OK(CreateSession(config,
&session));
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  TestSingleRequest(session.get());
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  }
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [int]{.keywordtype}
GetTotalBatchesProcessed()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [const]{.keyword} [string]{.keywordtype}
label(
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
[\"/tensorflow/serving/batching\_session/wrapped\_run\_count\"]{.stringliteral});
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [auto]{.keyword}\* collection\_registry =
monitoring::CollectionRegistry::Default();
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
monitoring::CollectionRegistry::CollectMetricsOptions options;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [const]{.keyword}
std::unique\_ptr\<monitoring::CollectedMetrics\> collected\_metrics =
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
collection\_registry-\>CollectMetrics(options);
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [int]{.keywordtype} total\_count = 0;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [const]{.keyword} [auto]{.keyword}&
point\_set\_map = collected\_metrics-\>point\_set\_map;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [if]{.keywordflow}
(point\_set\_map.find(label) == point\_set\_map.end())
[return]{.keywordflow} 0;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [const]{.keyword} monitoring::PointSet& lps =
\*point\_set\_map.at(label);
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< lps.points.size(); ++i) {
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  total\_count +=
lps.points\[i\]-\>int64\_value;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  }
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [return]{.keywordflow}
[static\_cast\<]{.keyword}[int]{.keywordtype}[\>]{.keyword}(total\_count);
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  }
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [void]{.keywordtype}
TestBatching([const]{.keyword} BatchingParameters& params,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [bool]{.keywordtype}
enable\_per\_model\_batching\_params,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [int]{.keywordtype}
input\_request\_batch\_size, [int]{.keywordtype} batch\_size)[ const
]{.keyword}{
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  SessionBundleConfig config =
GetSessionBundleConfig();
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
config.set\_enable\_per\_model\_batching\_params(
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  enable\_per\_model\_batching\_params);
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  BatchingParameters\* batching\_params =
config.mutable\_batching\_parameters();
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  \*batching\_params = params;
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// Tweak batching params further for
testing.]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// Set high value of max enqueued batches to
prevent queue limits to be hit]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// during testing that involves lot of
requests.]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
batching\_params-\>mutable\_max\_enqueued\_batches()-\>set\_value(INT\_MAX);
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// Set very high value of timeout to force
full batches to be formed.]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// The default (zero) value of the timeout
causes batches to formed with]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [// \[1..max\_batch\_size\] size based on
relative ordering of Run() calls. A]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// large value causes deterministic fix
batch size to be formed.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
batching\_params-\>mutable\_batch\_timeout\_micros()-\>set\_value(INT\_MAX);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  std::unique\_ptr\<Session\> session;
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [if]{.keywordflow}
(ExpectCreateBundleFailure()) {
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  EXPECT\_FALSE(CreateSession(config,
&session).ok());
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  }
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  TF\_ASSERT\_OK(CreateSession(config,
&session));
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [const]{.keyword} [int]{.keywordtype}
num\_requests = 10;
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [const]{.keyword} [int]{.keywordtype}
expected\_batches =
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  (input\_request\_batch\_size \*
num\_requests) / batch\_size;
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [const]{.keyword} [int]{.keywordtype}
orig\_batches\_processed = GetTotalBatchesProcessed();
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  TestMultipleRequests(session.get(),
num\_requests, input\_request\_batch\_size);
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  EXPECT\_EQ(orig\_batches\_processed +
expected\_batches,
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  GetTotalBatchesProcessed());
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  }
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [template]{.keyword} \<[class]{.keyword}
FactoryType\>
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [void]{.keywordtype}
TestEstimateResourceRequirementWithGoodExport(
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [double]{.keywordtype} total\_file\_size)[
const ]{.keyword}{
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [const]{.keyword} SessionBundleConfig config
= GetSessionBundleConfig();
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  std::unique\_ptr\<FactoryType\> factory;
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  TF\_ASSERT\_OK(FactoryType::Create(config,
&factory));
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  ResourceAllocation actual;
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
TF\_ASSERT\_OK(factory-\>EstimateResourceRequirement(export\_dir\_,
&actual));
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  ResourceAllocation expected =
GetExpectedResourceEstimate(total\_file\_size);
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  EXPECT\_THAT(actual, EqualsProto(expected));
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  }
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [void]{.keywordtype} TestRunOptions()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [if]{.keywordflow}
(!IsRunOptionsSupported()) [return]{.keywordflow};
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  SessionBundleConfig config =
GetSessionBundleConfig();
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// Configure the session-config with two
threadpools. The first is setup]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// with default settings. The second is
explicitly setup with 1 thread.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
config.mutable\_session\_config()-\>add\_session\_inter\_op\_thread\_pool();
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  config.mutable\_session\_config()
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  -\>add\_session\_inter\_op\_thread\_pool()
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  -\>set\_num\_threads(1);
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// Set the threadpool index to use for
session-run calls to 1.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
config.mutable\_session\_run\_load\_threadpool\_index()-\>set\_value(1);
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// Since the
session\_run\_load\_threadpool\_index in the config is set,
the]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// session-bundle should be loaded
successfully from path with RunOptions.]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  std::unique\_ptr\<Session\> session;
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [if]{.keywordflow}
(ExpectCreateBundleFailure()) {
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  EXPECT\_FALSE(CreateSession(config,
&session).ok());
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  }
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  TF\_ASSERT\_OK(CreateSession(config,
&session));
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  TestSingleRequest(session.get());
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  }
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [void]{.keywordtype} TestRunOptionsError()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [if]{.keywordflow}
(!IsRunOptionsSupported()) [return]{.keywordflow};
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// Session bundle config with the default
global threadpool.]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  SessionBundleConfig config =
GetSessionBundleConfig();
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [// Invalid threadpool index to use for
session-run calls.]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
config.mutable\_session\_run\_load\_threadpool\_index()-\>set\_value(100);
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [// Since RunOptions used in the session run
calls refers to an invalid]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [// threadpool index, load session bundle
from path should fail.]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  std::unique\_ptr\<Session\> session;
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  EXPECT\_FALSE(CreateSession(config,
&session).ok());
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  }
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} 
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [// Test data path, to be initialized to
point at a SessionBundle export or]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// SavedModel of half-plus-two.]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [string]{.keywordtype} export\_dir\_;
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} 
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [// Creates a Session with the given
configuration and export path.]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [virtual]{.keyword} Status
CreateSession([const]{.keyword} SessionBundleConfig &config,
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  std::unique\_ptr\<Session\> \*session)
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} 
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [// Returns a
SessionBundleConfig.]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [virtual]{.keyword} SessionBundleConfig
GetSessionBundleConfig()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [return]{.keywordflow}
SessionBundleConfig();
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  }
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} 
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [// Returns true if RunOptions is supported
by underlying session.]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
IsRunOptionsSupported()[ const ]{.keyword}{ [return]{.keywordflow}
[true]{.keyword}; }
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// Returns true if CreateBundle is expected
to fail.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
ExpectCreateBundleFailure()[ const ]{.keyword}{ [return]{.keywordflow}
[false]{.keyword}; }
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} };
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} 
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::BundleFactoryTest](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest.html)
:::

::: {.ttdef}
**Definition:** bundle\_factory\_test.h:43
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
