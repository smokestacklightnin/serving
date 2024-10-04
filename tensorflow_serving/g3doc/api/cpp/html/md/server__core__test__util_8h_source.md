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
-   [test\_util](dir_36785626a2bf25c917a1b24ac423d44f.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
server\_core\_test\_util.h
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_SERVER\_CORE\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_SERVER\_CORE\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<array\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<gtest/gtest.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// A test utility that provides access to
private ServerCore members.]{.comment}
:::

::: {.line}
[]{#l00031}[
[31](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTestAccess.html){.line}]{.lineno} [class
]{.keyword}[ServerCoreTestAccess](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTestAccess.html){.code}
{
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [explicit]{.keyword}
[ServerCoreTestAccess](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTestAccess.html){.code}([ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core) : core\_(core) {}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
[ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}\*
mutable\_options() { [return]{.keywordflow} &core\_-\>options\_; }
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
[const]{.keyword} core\_;
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} };
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} constexpr [char]{.keywordtype}
kTestModelName\[\] = [\"test\_model\"]{.stringliteral};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} constexpr [int]{.keywordtype}
kTestModelVersion = 123;
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} constexpr [int]{.keywordtype}
kTestModelLargerVersion = 124;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} constexpr [int]{.keywordtype}
kTestModelBogusVersion = 777;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} constexpr std::array\<int64\_t, 2\>
kAspiredVersions = {kTestModelVersion,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  kTestModelLargerVersion};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// The name of the platform associated with
FakeLoaderSourceAdapter.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} constexpr [char]{.keywordtype}
kFakePlatform\[\] = [\"fake\_servable\"]{.stringliteral};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// ServerCoreTest is parameterized based on
the TestType enum defined below.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// TODO(b/32248363): remove the parameter and
TestType after we switch Model]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// Server to Saved Model.]{.comment}
:::

::: {.line}
[]{#l00053}[
[53](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest.html){.line}]{.lineno} [class
]{.keyword}[ServerCoreTest](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest.html){.code}
: [public]{.keyword} ::testing::TestWithParam\<std::tuple\<int, bool\>\>
{
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// The parameter of this test.]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [enum]{.keyword} TestType {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// SavedModelBundle is used on
export.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  SAVED\_MODEL\_BACKWARD\_COMPATIBILITY,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// SavedModelBundle is used on native Saved
Model.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  SAVED\_MODEL,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// This should always be the last
value.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  NUM\_TEST\_TYPES,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  };
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [static]{.keyword} [string]{.keywordtype}
GetNameOfTestType([int]{.keywordtype} test\_type) {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [switch]{.keywordflow}
([static\_cast\<]{.keyword}TestType[\>]{.keyword}(test\_type)) {
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [case]{.keywordflow}
SAVED\_MODEL\_BACKWARD\_COMPATIBILITY:
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [return]{.keywordflow}
[\"SAVED\_MODEL\_BACKWARD\_COMPATIBILITY\"]{.stringliteral};
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [case]{.keywordflow} SAVED\_MODEL:
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [return]{.keywordflow}
[\"SAVED\_MODEL\"]{.stringliteral};
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [default]{.keywordflow}:
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [return]{.keywordflow}
[\"unknown\"]{.stringliteral};
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  }
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// Creates some reasonable default
ServerCore options for tests.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [static]{.keyword}
[ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
GetDefaultOptions();
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// Returns ModelServerConfig that contains
test model for the fake platform.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  ModelServerConfig
GetTestModelServerConfigForFakePlatform();
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// Returns ModelServerConfig that contains
test model for the tensorflow]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// platform.]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  ModelServerConfig
GetTestModelServerConfigForTensorflowPlatform();
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// Mutates \'config\' by changing the
model\'s base path to point to a variant]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [// of half-plus-two that has two versions
instead of one.]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [void]{.keywordtype}
SwitchToHalfPlusTwoWith2Versions(ModelServerConfig\* config);
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// Creates a ServerCore object configured
with both a fake platform and the]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// tensorflow platform, using the supplied
options.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  Status CreateServerCore([const]{.keyword}
ModelServerConfig& config,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
[ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
options,
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  std::unique\_ptr\<ServerCore\>\*
server\_core);
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// Creates a ServerCore object configured
with both a fake platform and the]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [// tensorflow platform, using
GetDefaultOptions().]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  Status CreateServerCore([const]{.keyword}
ModelServerConfig& config,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::unique\_ptr\<ServerCore\>\*
server\_core) {
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [return]{.keywordflow}
CreateServerCore(config, GetDefaultOptions(), server\_core);
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  }
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// Returns test type.]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// This is the first parameter of this
test.]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  TestType GetTestType() {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [return]{.keywordflow}
[static\_cast\<]{.keyword}TestType[\>]{.keyword}(std::get\<0\>(GetParam()));
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// Returns whether to assume paths are
URIs.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// This is the second parameter of this
test.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [bool]{.keywordtype}
PrefixPathsWithURIScheme() { [return]{.keywordflow}
std::get\<1\>(GetParam()); }
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// Returns a string corresponding to the
parameterized test-case.]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [string]{.keywordtype} GetNameForTestCase()
{
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [return]{.keywordflow}
GetNameOfTestType(GetTestType()) + [\"\_\"]{.stringliteral} +
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  (PrefixPathsWithURIScheme() ?
[\"URI\"]{.stringliteral} : [\"Path\"]{.stringliteral});
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} };
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// Creates a ServerCore object with the
supplied options.]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} Status CreateServerCore([const]{.keyword}
ModelServerConfig& config,
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
[ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
options,
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  std::unique\_ptr\<ServerCore\>\*
server\_core);
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [// Creates a ServerCore object with sane
defaults.]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} Status CreateServerCore([const]{.keyword}
ModelServerConfig& config,
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  std::unique\_ptr\<ServerCore\>\*
server\_core);
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [// A helper class to avoid long lines
accessing mutable configuration.]{.comment}
:::

::: {.line}
[]{#l00131}[
[131](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.line}]{.lineno} [class
]{.keyword}[ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.code}
{
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [explicit]{.keyword}
[ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.code}(ModelConfig\*
[const]{.keyword} config) : config\_(config) {}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// Sets or updates label and its
version.]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
[ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.code}
SetLabelVersion([const]{.keyword} [string]{.keywordtype}& label,
[const]{.keyword} [int]{.keywordtype}& version) {
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
(\*config\_-\>mutable\_version\_labels())\[label\] = version;
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [return]{.keywordflow} \*[this]{.keyword};
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  }
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  ModelConfig\* config\_;
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} };
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} [inline]{.keyword}
[ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.code}
MutateModelConfig(ModelServerConfig\* [const]{.keyword} config) {
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [return]{.keywordflow}
[ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html){.code}(
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
config-\>mutable\_model\_config\_list()-\>mutable\_config(0));
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} }
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_SERVER\_CORE\_TEST\_UTIL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::ModelConfigMutator](classtensorflow_1_1serving_1_1test__util_1_1ModelConfigMutator.html)
:::

::: {.ttdef}
**Definition:** server\_core\_test\_util.h:131
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1ServerCoreTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::ServerCoreTestAccess](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTestAccess.html)
:::

::: {.ttdef}
**Definition:** server\_core\_test\_util.h:31
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1ServerCoreTest_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::ServerCoreTest](classtensorflow_1_1serving_1_1test__util_1_1ServerCoreTest.html)
:::

::: {.ttdef}
**Definition:** server\_core\_test\_util.h:53
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServerCore_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html)
:::

::: {.ttdoc}
Options for configuring a ServerCore object.
:::

::: {.ttdef}
**Definition:** server\_core.h:96
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
