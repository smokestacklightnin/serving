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
-   [sources](dir_08664dcc00c1eef0a53a2c7ac1bb1da0.html){.el}
-   [storage\_path](dir_d847b898c0628c9998724b5c11dae72c.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
file\_system\_storage\_path\_source.h
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
TENSORFLOW\_SERVING\_SOURCES\_STORAGE\_PATH\_FILE\_SYSTEM\_STORAGE\_PATH\_SOURCE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SOURCES\_STORAGE\_PATH\_FILE\_SYSTEM\_STORAGE\_PATH\_SOURCE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/types/variant.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/periodic\_function.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/config/file\_system\_storage\_path\_source.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [class
]{.keyword}FileSystemStoragePathSourceTestAccess;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00062}[
[62](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.line}]{.lineno} [class
]{.keyword}[FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.code}
: [public]{.keyword}
[Source](classtensorflow_1_1serving_1_1Source.html){.code}\<StoragePath\>
{
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} FileSystemStoragePathSourceConfig& config,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
std::unique\_ptr\<FileSystemStoragePathSource\>\* result);
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
\~[FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  Status
[UpdateConfig](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html#ad29df4b1d9628b03723474db5a0d6ad0){.code}([const]{.keyword}
FileSystemStoragePathSourceConfig& config);
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [void]{.keywordtype}
SetAspiredVersionsCallback([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
callback) [override]{.keyword};
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  FileSystemStoragePathSourceConfig config()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [return]{.keywordflow} config\_;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  }
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [friend]{.keyword} [class
]{.keyword}[internal::FileSystemStoragePathSourceTestAccess](classtensorflow_1_1serving_1_1internal_1_1FileSystemStoragePathSourceTestAccess.html){.code};
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
[FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [// Polls the file system and identify
numerical children of the base path.]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// If zero such children are found, invokes
\'aspired\_versions\_callback\_\' with]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [// an empty versions list. If one or more
such children are found, invokes]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// \'aspired\_versions\_callback\_\' with a
singleton list containing the largest]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// such child.]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  Status PollFileSystemAndInvokeCallback();
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// Sends empty aspired-versions lists for
each servable in \'servable\_names\'.]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  Status UnaspireServables([const]{.keyword}
std::set\<string\>& servable\_names)
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [template]{.keyword}
\<[typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [void]{.keywordtype}
CallAspiredVersionsCallback(Args&&\... args) {
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [if]{.keywordflow}
(aspired\_versions\_callback\_) {
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
aspired\_versions\_callback\_(std::forward\<Args\>(args)\...);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [if]{.keywordflow}
(aspired\_versions\_callback\_notifier\_) {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  aspired\_versions\_callback\_notifier\_();
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  }
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  }
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  }
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// For testing.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [void]{.keywordtype}
SetAspiredVersionsCallbackNotifier(std::function\<[void]{.keywordtype}()\>
fn) {
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  aspired\_versions\_callback\_notifier\_ =
fn;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  }
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [mutable]{.keyword} mutex mu\_;
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  FileSystemStoragePathSourceConfig config\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
aspired\_versions\_callback\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  std::function\<void()\>
aspired\_versions\_callback\_notifier\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// A thread that calls
PollFileSystemAndInvokeCallback() once or periodically.]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [using]{.keyword} ThreadType =
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  absl::variant\<absl::monostate,
PeriodicFunction, std::unique\_ptr\<Thread\>\>;
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  std::unique\_ptr\<ThreadType\>
fs\_polling\_thread\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html){.code});
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} };
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SOURCES\_STORAGE\_PATH\_FILE\_SYSTEM\_STORAGE\_PATH\_SOURCE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1FileSystemStoragePathSource_html .ttc}
::: {.ttname}
[tensorflow::serving::FileSystemStoragePathSource](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html)
:::

::: {.ttdef}
**Definition:** file\_system\_storage\_path\_source.h:62
:::
:::

::: {#aclasstensorflow_1_1serving_1_1FileSystemStoragePathSource_html_ad29df4b1d9628b03723474db5a0d6ad0 .ttc}
::: {.ttname}
[tensorflow::serving::FileSystemStoragePathSource::UpdateConfig](classtensorflow_1_1serving_1_1FileSystemStoragePathSource.html#ad29df4b1d9628b03723474db5a0d6ad0)
:::

::: {.ttdeci}
Status UpdateConfig(const FileSystemStoragePathSourceConfig &config)
:::

::: {.ttdef}
**Definition:** file\_system\_storage\_path\_source.cc:376
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html .ttc}
::: {.ttname}
[tensorflow::serving::Source](classtensorflow_1_1serving_1_1Source.html)
:::

::: {.ttdef}
**Definition:** source.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html_aeb281087e1478b0ff4a74e3f60496c6f .ttc}
::: {.ttname}
[tensorflow::serving::Source\< StoragePath
\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f)
:::

::: {.ttdeci}
std::function\< void(const StringPiece servable\_name, std::vector\<
ServableData\< StoragePath \> \> versions)\> AspiredVersionsCallback
:::

::: {.ttdef}
**Definition:** source.h:88
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1FileSystemStoragePathSourceTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::FileSystemStoragePathSourceTestAccess](classtensorflow_1_1serving_1_1internal_1_1FileSystemStoragePathSourceTestAccess.html)
:::

::: {.ttdef}
**Definition:** file\_system\_storage\_path\_source\_test.cc:50
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
