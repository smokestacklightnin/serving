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
-   [core](dir_517df0ab1daf8f221f60ae5135602a49.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
source\_adapter.h
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
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/core/stringpiece.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/lib/io/path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
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
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/core/target.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/util/class\_registration.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00059}[
[59](classtensorflow_1_1serving_1_1SourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}
: [public]{.keyword}
[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}\<InputType\>,
[public]{.keyword}
[Source](classtensorflow_1_1serving_1_1Source.html){.code}\<OutputType\>
{
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
\~[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}()
[override]{.keyword} = 0;
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00065}[
[65](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.line}]{.lineno} 
[void]{.keywordtype}
[SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.code}([const]{.keyword}
StringPiece servable\_name,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
std::vector\<[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) [final]{.keyword};
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [void]{.keywordtype}
SetAspiredVersionsCallback(
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [typename]{.keyword}
[Source\<OutputType\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html){.code}
callback) [final]{.keyword};
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00073}[
[73](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.line}]{.lineno} 
[virtual]{.keyword} std::vector\<ServableData\<OutputType\>\>
[Adapt](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.code}(
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [const]{.keyword} StringPiece servable\_name,
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
std::vector\<[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) = 0;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00078}[
[78](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.line}]{.lineno} 
[ServableData\<OutputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}
[AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.code}([ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}
input);
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// This is an abstract class.]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// The callback for emitting
OutputType-based aspired-version lists.]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [typename]{.keyword}
[Source\<OutputType\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html){.code}
outgoing\_callback\_;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [// Has \'outgoing\_callback\_\' been set
yet, so that the SourceAdapter is ready]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// to propagate aspired versions?]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  Notification outgoing\_callback\_set\_;
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} };
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// START\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// Define a SourceAdapter registry for the
common case of adapting from a]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// storage path to a loader.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [using]{.keyword}
[StoragePathSourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}
=
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [SourceAdapter\<StoragePath,
std::unique\_ptr\<Loader\>](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}\>;
:::

::: {.line}
[]{#l00099}[
99]{.lineno} DEFINE\_CLASS\_REGISTRY(StoragePathSourceAdapterRegistry,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
[StoragePathSourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code});
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [\#define
REGISTER\_STORAGE\_PATH\_SOURCE\_ADAPTER(ClassCreator, ConfigProto)
\\]{.preprocessor}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [
REGISTER\_CLASS(StoragePathSourceAdapterRegistry,
StoragePathSourceAdapter, \\]{.preprocessor}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [ ClassCreator, ConfigProto);]{.preprocessor}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// A source adapter that converts InputType
instances to OutputType instances]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// one at a time (i.e. there is no
interaction among members of a given aspired-]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [// version list). Most source adapters can
subclass UnarySourceAdapter, and do]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} [// not need the full generality of
SourceAdapter.]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// Requires OutputType to be
default-constructable and updatable in-place.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// Implementing subclasses supply an
implementation of the Convert() virtual]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [// method, which converts a servable from
InputType to OutputType.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [// IMPORTANT: Every leaf derived class must
call Detach() at the top of its]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [// destructor. (See documentation on
TargetBase::Detach() in target.h.) Doing so]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [// ensures that no Convert() calls are in
flight during destruction of member]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [// variables.]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00120}[
[120](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}
: [public]{.keyword}
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}\<InputType,
OutputType\> {
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
\~[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}()
[override]{.keyword} = 0;
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// This is an abstract class.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// This method is implemented in terms of
Convert(), which the implementing]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [// subclass must supply.]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  std::vector\<ServableData\<OutputType\>\>
Adapt(
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
std::vector\<[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) [final]{.keyword};
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// Converts a single InputType instance
into a corresponding OutputType]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// instance.]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [virtual]{.keyword} Status
Convert([const]{.keyword} InputType& data, OutputType\* converted\_data)
= 0;
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} };
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} [// A source adapter that converts every
incoming ServableData\<InputType\> item]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [// into an error-containing
ServableData\<OutputType\>. If the incoming data item]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} [// was already an error, the existing error
is passed through; otherwise a new]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [// error Status given via this class\'s
constructor is added.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} [// This class is useful in conjunction with
a router, to handle servable data]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} [// items that do not conform to any
explicitly-programmed route. Specifically,]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} [// consider a fruit router configured route
apples to output port 0, oranges to]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} [// output port 1, and anything else to a
final port 2. If we only have proper]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} [// SourceAdapters to handle apples and
oranges, we might connect an]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} [// ErrorInjectingSourceAdapter to port 2, to
catch any unexpected fruits.]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00152}[
[152](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[ErrorInjectingSourceAdapter](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html){.code}
final
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  : [public]{.keyword}
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}\<InputType,
OutputType\> {
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [explicit]{.keyword}
[ErrorInjectingSourceAdapter](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html){.code}([const]{.keyword}
Status& error);
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} 
\~[ErrorInjectingSourceAdapter](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  std::vector\<ServableData\<OutputType\>\>
Adapt(
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
std::vector\<[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) [override]{.keyword};
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [// The error status to inject.]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [const]{.keyword} Status error\_;
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ErrorInjectingSourceAdapter](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html){.code});
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} };
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} 
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} [SourceAdapter\<InputType,
OutputType\>::\~SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}()
{}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} 
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00176}[
[176](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.line}]{.lineno} [void]{.keywordtype}
[SourceAdapter\<InputType,
OutputType\>::SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.code}(
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} 
std::vector\<[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) {
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
outgoing\_callback\_set\_.WaitForNotification();
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  outgoing\_callback\_(servable\_name,
Adapt(servable\_name, std::move(versions)));
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} }
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} 
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} [void]{.keywordtype}
[SourceAdapter\<InputType,
OutputType\>::SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}(
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [typename]{.keyword}
[Source\<OutputType\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html){.code}
callback) {
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  outgoing\_callback\_ = callback;
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  outgoing\_callback\_set\_.Notify();
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} }
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00191}[
[191](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.line}]{.lineno} [ServableData\<OutputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}
[SourceAdapter\<InputType,
OutputType\>::AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.code}(
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
[ServableData\<InputType\>](classtensorflow_1_1serving_1_1ServableData.html){.code}
input) {
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [const]{.keyword} StringPiece
servable\_name(input.id().name);
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  std::vector\<ServableData\<InputType\>\>
input\_versions = {input};
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  std::vector\<ServableData\<OutputType\>\>
output\_versions =
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  Adapt(servable\_name, input\_versions);
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  DCHECK\_EQ(1, output\_versions.size());
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [return]{.keywordflow}
std::move(output\_versions\[0\]);
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} }
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} 
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} [UnarySourceAdapter\<InputType,
OutputType\>::\~UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}()
{}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} 
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} std::vector\<ServableData\<OutputType\>\>
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} UnarySourceAdapter\<InputType,
OutputType\>::Adapt(
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  std::vector\<ServableData\<InputType\>\>
versions) {
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  std::vector\<ServableData\<OutputType\>\>
adapted\_versions;
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
ServableData\<InputType\>& version : versions) {
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [if]{.keywordflow} (version.status().ok()) {
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  OutputType adapted\_data;
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  Status adapt\_status =
Convert(version.DataOrDie(), &adapted\_data);
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [if]{.keywordflow} (adapt\_status.ok()) {
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  adapted\_versions.emplace\_back(
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  ServableData\<OutputType\>{version.id(),
std::move(adapted\_data)});
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  adapted\_versions.emplace\_back(
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  ServableData\<OutputType\>{version.id(),
adapt\_status});
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  }
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  adapted\_versions.emplace\_back(
:::

::: {.line}
[]{#l00223}[ 223]{.lineno}  ServableData\<OutputType\>{version.id(),
version.status()});
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  }
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  }
:::

::: {.line}
[]{#l00226}[ 226]{.lineno}  [return]{.keywordflow} adapted\_versions;
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} }
:::

::: {.line}
[]{#l00228}[ 228]{.lineno} 
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} ErrorInjectingSourceAdapter\<InputType,
OutputType\>::ErrorInjectingSourceAdapter(
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  [const]{.keyword} Status& error)
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  : error\_(error) {
:::

::: {.line}
[]{#l00233}[ 233]{.lineno}  DCHECK(!error.ok());
:::

::: {.line}
[]{#l00234}[ 234]{.lineno} }
:::

::: {.line}
[]{#l00235}[ 235]{.lineno} 
:::

::: {.line}
[]{#l00236}[ 236]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00237}[ 237]{.lineno} ErrorInjectingSourceAdapter\<InputType,
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} 
OutputType\>::\~ErrorInjectingSourceAdapter() {
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  TargetBase\<InputType\>::Detach();
:::

::: {.line}
[]{#l00240}[ 240]{.lineno} }
:::

::: {.line}
[]{#l00241}[ 241]{.lineno} 
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} [template]{.keyword} \<[typename]{.keyword}
InputType, [typename]{.keyword} OutputType\>
:::

::: {.line}
[]{#l00243}[ 243]{.lineno} std::vector\<ServableData\<OutputType\>\>
:::

::: {.line}
[]{#l00244}[ 244]{.lineno} ErrorInjectingSourceAdapter\<InputType,
OutputType\>::Adapt(
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  std::vector\<ServableData\<InputType\>\>
versions) {
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  std::vector\<ServableData\<OutputType\>\>
adapted\_versions;
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
ServableData\<InputType\>& version : versions) {
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  [if]{.keywordflow} (version.status().ok()) {
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  LOG(INFO) \<\< [\"Injecting error for
servable \"]{.stringliteral} \<\< version.id() \<\< [\":
\"]{.stringliteral}
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  \<\< error\_.message();
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  adapted\_versions.emplace\_back(
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  ServableData\<OutputType\>{version.id(),
error\_});
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  adapted\_versions.emplace\_back(
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  ServableData\<OutputType\>{version.id(),
version.status()});
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  }
:::

::: {.line}
[]{#l00258}[ 258]{.lineno}  }
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [return]{.keywordflow} adapted\_versions;
:::

::: {.line}
[]{#l00260}[ 260]{.lineno} }
:::

::: {.line}
[]{#l00261}[ 261]{.lineno} 
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} [// END\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} 
:::

::: {.line}
[]{#l00264}[ 264]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00265}[ 265]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00266}[ 266]{.lineno} 
:::

::: {.line}
[]{#l00267}[ 267]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ADAPTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ErrorInjectingSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::ErrorInjectingSourceAdapter](classtensorflow_1_1serving_1_1ErrorInjectingSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:153
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:59
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceAdapter_html_a7c960f8493040fc8cb0766e4c2cebf60 .ttc}
::: {.ttname}
[tensorflow::serving::SourceAdapter::Adapt](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60)
:::

::: {.ttdeci}
virtual std::vector\< ServableData\< OutputType \> \> Adapt(const
StringPiece servable\_name, std::vector\< ServableData\< InputType \>\>
versions)=0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceAdapter_html_a9775d0a39269efb319a0dbd94862f183 .ttc}
::: {.ttname}
[tensorflow::serving::SourceAdapter::SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183)
:::

::: {.ttdeci}
void SetAspiredVersions(const StringPiece servable\_name, std::vector\<
ServableData\< InputType \>\> versions) final
:::

::: {.ttdef}
**Definition:** source\_adapter.h:176
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceAdapter_html_acb3ad719a856c7bb0085df33438c4986 .ttc}
::: {.ttname}
[tensorflow::serving::SourceAdapter::AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986)
:::

::: {.ttdeci}
ServableData\< OutputType \> AdaptOneVersion(ServableData\< InputType \>
input)
:::

::: {.ttdoc}
Adapts a single servable data item. (Implemented on top of Adapt().)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:191
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

::: {#aclasstensorflow_1_1serving_1_1TargetBase_html .ttc}
::: {.ttname}
[tensorflow::serving::TargetBase](classtensorflow_1_1serving_1_1TargetBase.html)
:::

::: {.ttdef}
**Definition:** target.h:61
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UnarySourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:120
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
