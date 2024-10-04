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
-   [util](dir_1303efdc8de326749a332c6a57186055.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
class\_registration.h
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
[]{#l00016}[ 16]{.lineno} [// A way to register subclasses of an
abstract base class, and associate a]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// config proto message type. Instances can
be instantiated from an Any proto]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [// field that contains a config proto, based
on the type and content of the]{.comment}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [// config proto.]{.comment}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [// IMPORTANT: Config protos used in
registries must be compiled into the binary.]{.comment}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [// Each registry has a name. Registry names
in each namespace must be distinct.]{.comment}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [// A registry is tied to a specific base
class and factory signature. It is fine]{.comment}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [// to have multiple registries for a given
base class, whether having the same]{.comment}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// factory signature or multiple distinct
signatures.]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Usage:]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// // Define a base class.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// class MyBaseClass {]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// // Define a registry that maps from proto
message types to subclasses of]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// // MyBaseClass.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [//
DEFINE\_CLASS\_REGISTRY(MyBaseClassRegistry, MyBaseClass);]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// // Define a macro used create a specific
entry in MyBaseClassRegistry that]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// // maps from ConfigProto to
ClassCreator::Create().]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// \#define
REGISTER\_MY\_BASE\_CLASS(ClassCreator, ConfigProto)]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// REGISTER\_CLASS(MyBaseClassRegistry,
MyBaseClass, ClassCreator,]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// ConfigProto);]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// // Declare a subclass of MyBaseClass to be
created when a OneConfigProto]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// // is passed to the Create\*() factory
methods.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// class OneClass : public MyBaseClass
{]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// public:]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// static Status Create(const OneConfigProto&
config,]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// std::unique\_ptr\<BaseClass\>\* result)
{]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// OneClass\* raw\_result = new
OneClass();]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// raw\_result-\>config\_ =
config;]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// Status status =
raw\_result-\>Init();]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// if (status.ok()) {]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// result-\>reset(raw\_result);]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// return status;]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// private:]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// Status Init() {]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// \... initialize the object based on
\'config\_\']{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// OneConfigProto config\_;]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// REGISTER\_MY\_BASE\_CLASS(OneClass,
OneConfigProto);]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// // Create an object of type OneClass using
the registry to switch on]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// // the type OneConfigProto.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// OneConfigProto config = \...]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// std::unique\_ptr\<BaseClass\>
loaded\_subclass;]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [//
CHECK\_OK(MyBaseClassRegistry::Create(config,
&loaded\_subclass));]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// // Same, but starting from an Any message
that wraps a OneConfigProto.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// protobuf::Any any\_config = \... // wraps
a OneConfigProto]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// std::unique\_ptr\<BaseClass\>
loaded\_subclass;]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [//
CHECK\_OK(MyBaseClassRegistry::CreateFromAny(any\_config,
&loaded\_subclass));]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// Note that the subclass creator need not be
the subclass itself. For example:]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [// class AnotherClass : public MyBaseClass
{]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [// public:]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [// AnotherClass(int a, int b);]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// class CreatorForAnotherClass {]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [// public:]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [// static Status Create(const OneConfigProto&
config,]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [// std::unique\_ptr\<BaseClass\>\* result)
{]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [// result-\>reset(new
AnotherClass(config.a(), config.b()));]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// return Status::OK;]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [//
REGISTER\_MY\_BASE\_CLASS(CreatorForAnotherClass,
OneConfigProto);]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// This mechanism also allows additional
parameter passing into the Create()]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [// factory method. Consider the following
example in which Create() takes an]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [// int, a string and an int-\>string map, in
addition to the config proto:]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// class MyParameterizedBaseClass
{]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [//
DEFINE\_CLASS\_REGISTRY(MyParameterizedBaseClassRegistry,]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} [// MyParameterizedBaseClass, int, const
string&]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [// const std::map\<int TFS\_COMMA
string\>&);]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// \#define
REGISTER\_MY\_BASE\_CLASS(ClassCreator, ConfigProto)]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [// REGISTER\_CLASS(MyBaseClassRegistry,
MyBaseClass, ClassCreator,]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// ConfigProto, int, const
string&,]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [// const std::map\<int TFS\_COMMA
string\>&);]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [// class OneClass : public
MyParameterizedBaseClass {]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [// public:]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [// static Status Create(const
OneConfigProto& config,]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [// int param1, const string&
param2,]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [// const std::map\<int, string\>&
param3,]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [// std::unique\_ptr\<BaseClass\>\* result)
{]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [// OneConfigProto config = \...]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [// int int\_param = \...]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [// string string\_param = \...]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} [// std::map\<int, string\> map\_param =
\...]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [// std::unique\_ptr\<BaseClass\>
loaded\_subclass;]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [//
CHECK\_OK(MyParameterizedBaseClassRegistry::Create(config,]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [// int\_param,]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} [// string\_param,]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} [// map\_param,]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [// &loaded\_subclass));]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [// The registry name can be anything you
choose, and it\'s fine to have multiple]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} [// registries for the same base class,
potentially with different factory]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} [// signatures.]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [// Note that types containing a comma, e.g.
std::map\<string, int\> must use]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} [// TFS\_COMMA in place of \',\'.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [// TODO(b/24472377): Eliminate the
requirement to use TFS\_COMMA.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_CLASS\_REGISTRATION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_CLASS\_REGISTRATION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} [\#include
\"google/protobuf/any.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} [\#include
\"google/protobuf/descriptor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} [\#include
\"google/protobuf/message.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} [\#include
\"tensorflow/core/lib/core/stringpiece.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} [\#include
\"tensorflow/core/platform/protobuf.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} [\#include
\"tensorflow\_serving/util/class\_registration\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} 
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} [// The interface for a factory method that
takes a protobuf::Message as]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} [// input to construct an object of type
BaseClass.]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [template]{.keyword} \<[typename]{.keyword}
BaseClass, [typename]{.keyword}\... AdditionalFactoryArgs\>
:::

::: {.line}
[]{#l00173}[
[173](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.line}]{.lineno} [class
]{.keyword}[AbstractClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}
{
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [virtual]{.keyword}
\~[AbstractClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} 
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// Creates an object using this factory.
Fails if \'config\' is not of the]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [// expected type.]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [virtual]{.keyword} Status
Create([const]{.keyword} protobuf::Message& config,
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  AdditionalFactoryArgs\... args,
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  std::unique\_ptr\<BaseClass\>\* result)
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} };
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} [// The interface for a factory method that
takes a protobuf::Message as]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} [// input to construct an object of type
BaseClass.]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} [template]{.keyword} \<[typename]{.keyword}
BaseClass, [typename]{.keyword} Class, [typename]{.keyword} Config,
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [typename]{.keyword}\...
AdditionalFactoryArgs\>
:::

::: {.line}
[]{#l00188}[
[188](classtensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory.html){.line}]{.lineno} [class
]{.keyword}[ClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory.html){.code}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  : [public]{.keyword}
[AbstractClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}\<BaseClass,
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  AdditionalFactoryArgs\...\> {
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
[ClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory.html){.code}()
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  :
config\_descriptor\_(Config::default\_instance().GetDescriptor()) {}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} 
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [// Creates an object using this factory.
Fails if \'config\' is not of the]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// expected type.]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  Status Create([const]{.keyword}
protobuf::Message& config, AdditionalFactoryArgs\... args,
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  std::unique\_ptr\<BaseClass\>\* result)[
const override ]{.keyword}{
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [if]{.keywordflow}
(config.GetDescriptor()-\>full\_name() !=
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  config\_descriptor\_-\>full\_name()) {
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [\"Supplied config proto of type
\"]{.stringliteral}, config.GetDescriptor()-\>full\_name(),
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [\" does not match expected type
\"]{.stringliteral}, config\_descriptor\_-\>full\_name());
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  }
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [return]{.keywordflow}
Class::Create([static\_cast\<]{.keyword}[const
]{.keyword}Config&[\>]{.keyword}(config),
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} 
std::forward\<AdditionalFactoryArgs\>(args)\..., result);
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  }
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} 
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [const]{.keyword} protobuf::Descriptor\*
[const]{.keyword} config\_descriptor\_;
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} 
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory.html){.code});
:::

::: {.line}
[]{#l00213}[ 213]{.lineno} };
:::

::: {.line}
[]{#l00214}[ 214]{.lineno} 
:::

::: {.line}
[]{#l00215}[ 215]{.lineno} constexpr [char]{.keywordtype}
kTypeGoogleApisComPrefix\[\] =
[\"type.googleapis.com/\"]{.stringliteral};
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno} [// A static map whose keys are proto message
names, and values are]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} [// ClassRegistrationFactories. Includes a
Create() factory method that]{.comment}
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} [// performs a lookup in the map and calls
Create() on the]{.comment}
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} [// ClassRegistrationFactory it
finds.]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno} [template]{.keyword} \<[typename]{.keyword}
RegistryName, [typename]{.keyword} BaseClass,
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  [typename]{.keyword}\...
AdditionalFactoryArgs\>
:::

::: {.line}
[]{#l00223}[
[223](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry.html){.line}]{.lineno} [class
]{.keyword}[ClassRegistry](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry.html){.code}
{
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  [using]{.keyword}
[FactoryType](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}
=
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} 
[AbstractClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}\<BaseClass,
AdditionalFactoryArgs\...\>;
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [// Creates an instance of BaseClass based
on a config proto.]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} protobuf::Message& config,
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  AdditionalFactoryArgs\... args,
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  std::unique\_ptr\<BaseClass\>\* result) {
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
config\_proto\_message\_type =
:::

::: {.line}
[]{#l00233}[ 233]{.lineno}  config.GetDescriptor()-\>full\_name();
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [auto]{.keyword}\* factory =
LookupFromMap(config\_proto\_message\_type);
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [if]{.keywordflow} (factory ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  [\"Couldn\'t find factory for config proto
message type \"]{.stringliteral},
:::

::: {.line}
[]{#l00238}[ 238]{.lineno}  config\_proto\_message\_type,
[\"\\nconfig=\"]{.stringliteral}, config.DebugString());
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  }
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  [return]{.keywordflow}
factory-\>Create(config,
std::forward\<AdditionalFactoryArgs\>(args)\...,
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  result);
:::

::: {.line}
[]{#l00242}[ 242]{.lineno}  }
:::

::: {.line}
[]{#l00243}[ 243]{.lineno} 
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [// Creates an instance of BaseClass based
on a config proto embedded in an Any]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  [// message.]{.comment}
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  [// Requires that the config proto in the
Any has a compiled-in descriptor.]{.comment}
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  [static]{.keyword} Status
CreateFromAny([const]{.keyword} google::protobuf::Any& any\_config,
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  AdditionalFactoryArgs\... args,
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  std::unique\_ptr\<BaseClass\>\* result) {
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  [// Copy the config to a proto message of
the indicated type.]{.comment}
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [string]{.keywordtype} full\_type\_name;
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  Status parse\_status =
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  ParseUrlForAnyType(any\_config.type\_url(),
&full\_type\_name);
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  [if]{.keywordflow} (!parse\_status.ok()) {
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  [return]{.keywordflow} parse\_status;
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  }
:::

::: {.line}
[]{#l00258}[ 258]{.lineno}  [const]{.keyword} protobuf::Descriptor\*
descriptor =
:::

::: {.line}
[]{#l00259}[ 259]{.lineno} 
protobuf::DescriptorPool::generated\_pool()-\>FindMessageTypeByName(
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  full\_type\_name);
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  [if]{.keywordflow} (descriptor ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00262}[ 262]{.lineno}  [return]{.keywordflow} errors::Internal(
:::

::: {.line}
[]{#l00263}[ 263]{.lineno}  [\"Unable to find compiled-in proto
descriptor of type \"]{.stringliteral},
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  full\_type\_name);
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  }
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  std::unique\_ptr\<protobuf::Message\>
config(
:::

::: {.line}
[]{#l00267}[ 267]{.lineno} 
protobuf::MessageFactory::generated\_factory()
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  -\>GetPrototype(descriptor)
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  -\>New());
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  [if]{.keywordflow}
(!any\_config.UnpackTo(config.get())) {
:::

::: {.line}
[]{#l00271}[ 271]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"Malformed content of Any:
\"]{.stringliteral},
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  any\_config.DebugString());
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  }
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  [return]{.keywordflow} Create(\*config,
std::forward\<AdditionalFactoryArgs\>(args)\...,
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  result);
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  }
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  [// Nested class whose instantiation inserts
a key/value pair into the factory]{.comment}
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  [// map.]{.comment}
:::

::: {.line}
[]{#l00280}[
[280](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry_1_1MapInserter.html){.line}]{.lineno} 
[class
]{.keyword}[MapInserter](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry_1_1MapInserter.html){.code}
{
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00282}[ 282]{.lineno} 
[MapInserter](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry_1_1MapInserter.html){.code}([const]{.keyword}
[string]{.keywordtype}& config\_proto\_message\_type,
[FactoryType](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}\*
factory) {
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  InsertIntoMap(config\_proto\_message\_type,
factory);
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  }
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  };
:::

::: {.line}
[]{#l00286}[ 286]{.lineno} 
:::

::: {.line}
[]{#l00287}[ 287]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [// Inserts a key/value pair into the
factory map.]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  [static]{.keyword} [void]{.keywordtype}
InsertIntoMap([const]{.keyword} [string]{.keywordtype}&
config\_proto\_message\_type,
:::

::: {.line}
[]{#l00290}[ 290]{.lineno} 
[FactoryType](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html){.code}\*
factory) {
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  LockableFactoryMap\* global\_map =
GlobalFactoryMap();
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  {
:::

::: {.line}
[]{#l00293}[ 293]{.lineno}  mutex\_lock lock(global\_map-\>mu);
:::

::: {.line}
[]{#l00294}[ 294]{.lineno} 
global\_map-\>factory\_map.insert({config\_proto\_message\_type,
factory});
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  }
:::

::: {.line}
[]{#l00296}[ 296]{.lineno}  }
:::

::: {.line}
[]{#l00297}[ 297]{.lineno} 
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  [// Retrieves a value from the factory map,
or returns nullptr if no value was]{.comment}
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  [// found.]{.comment}
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  [static]{.keyword} FactoryType\*
LookupFromMap([const]{.keyword} [string]{.keywordtype}&
config\_proto\_message\_type) {
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  LockableFactoryMap\* global\_map =
GlobalFactoryMap();
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  {
:::

::: {.line}
[]{#l00303}[ 303]{.lineno}  mutex\_lock lock(global\_map-\>mu);
:::

::: {.line}
[]{#l00304}[ 304]{.lineno}  [auto]{.keyword} it =
global\_map-\>factory\_map.find(config\_proto\_message\_type);
:::

::: {.line}
[]{#l00305}[ 305]{.lineno}  [if]{.keywordflow} (it ==
global\_map-\>factory\_map.end()) {
:::

::: {.line}
[]{#l00306}[ 306]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  }
:::

::: {.line}
[]{#l00308}[ 308]{.lineno}  [return]{.keywordflow} it-\>second;
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  }
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  }
:::

::: {.line}
[]{#l00311}[ 311]{.lineno} 
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [// A map from proto descriptor names to
factories, with a lock.]{.comment}
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  [struct ]{.keyword}LockableFactoryMap {
:::

::: {.line}
[]{#l00314}[ 314]{.lineno}  mutex mu;
:::

::: {.line}
[]{#l00315}[ 315]{.lineno}  std::unordered\_map\<string, FactoryType\*\>
factory\_map TF\_GUARDED\_BY(mu);
:::

::: {.line}
[]{#l00316}[ 316]{.lineno}  };
:::

::: {.line}
[]{#l00317}[ 317]{.lineno} 
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  [// Returns a pointer to the factory map.
There is one factory map per set of]{.comment}
:::

::: {.line}
[]{#l00319}[ 319]{.lineno}  [// template parameters of this
class.]{.comment}
:::

::: {.line}
[]{#l00320}[ 320]{.lineno}  [static]{.keyword} LockableFactoryMap\*
GlobalFactoryMap() {
:::

::: {.line}
[]{#l00321}[ 321]{.lineno}  [static]{.keyword} [auto]{.keyword}\*
global\_map = \[\]() -\> LockableFactoryMap\* {
:::

::: {.line}
[]{#l00322}[ 322]{.lineno}  [return]{.keywordflow} [new]{.keyword}
LockableFactoryMap;
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  }();
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  [return]{.keywordflow} global\_map;
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  }
:::

::: {.line}
[]{#l00326}[ 326]{.lineno} 
:::

::: {.line}
[]{#l00327}[ 327]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN(ClassRegistry);
:::

::: {.line}
[]{#l00328}[ 328]{.lineno} };
:::

::: {.line}
[]{#l00329}[ 329]{.lineno} 
:::

::: {.line}
[]{#l00330}[ 330]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00331}[ 331]{.lineno} 
:::

::: {.line}
[]{#l00332}[ 332]{.lineno} [// Used to enable the following macros to
work with types containing commas]{.comment}
:::

::: {.line}
[]{#l00333}[ 333]{.lineno} [// (e.g. map\<string, int\>).]{.comment}
:::

::: {.line}
[]{#l00334}[ 334]{.lineno} [// TODO(b/24472377): Eliminate the
requirement to use TFS\_COMMA, via some fancy]{.comment}
:::

::: {.line}
[]{#l00335}[ 335]{.lineno} [// macro gymnastics.]{.comment}
:::

::: {.line}
[]{#l00336}[ 336]{.lineno} [\#define TFS\_COMMA ,]{.preprocessor}
:::

::: {.line}
[]{#l00337}[ 337]{.lineno} 
:::

::: {.line}
[]{#l00338}[ 338]{.lineno} [// Given a base class BaseClass, creates a
registry named RegistryName.]{.comment}
:::

::: {.line}
[]{#l00339}[ 339]{.lineno} [\#define
DEFINE\_CLASS\_REGISTRY(RegistryName, BaseClass, \...)
\\]{.preprocessor}
:::

::: {.line}
[]{#l00340}[ 340]{.lineno} [ class RegistryName : public
::tensorflow::serving::internal::ClassRegistry\< \\]{.preprocessor}
:::

::: {.line}
[]{#l00341}[ 341]{.lineno} [ RegistryName, BaseClass,
\#\#\_\_VA\_ARGS\_\_\> {};]{.preprocessor}
:::

::: {.line}
[]{#l00342}[ 342]{.lineno} 
:::

::: {.line}
[]{#l00343}[ 343]{.lineno} [// Registers a factory that creates
subclasses of BaseClass by calling]{.comment}
:::

::: {.line}
[]{#l00344}[ 344]{.lineno} [// ClassCreator::Create().]{.comment}
:::

::: {.line}
[]{#l00345}[ 345]{.lineno} [\#define REGISTER\_CLASS(RegistryName,
BaseClass, ClassCreator, config\_proto, \\]{.preprocessor}
:::

::: {.line}
[]{#l00346}[ 346]{.lineno} [ \...) \\]{.preprocessor}
:::

::: {.line}
[]{#l00347}[ 347]{.lineno} [
REGISTER\_CLASS\_UNIQ\_HELPER(\_\_COUNTER\_\_, RegistryName, BaseClass,
\\]{.preprocessor}
:::

::: {.line}
[]{#l00348}[ 348]{.lineno} [ ClassCreator, config\_proto,
\#\#\_\_VA\_ARGS\_\_)]{.preprocessor}
:::

::: {.line}
[]{#l00349}[ 349]{.lineno} 
:::

::: {.line}
[]{#l00350}[ 350]{.lineno} [\#define REGISTER\_CLASS\_UNIQ\_HELPER(cnt,
RegistryName, BaseClass, ClassCreator, \\]{.preprocessor}
:::

::: {.line}
[]{#l00351}[ 351]{.lineno} [ config\_proto, \...) \\]{.preprocessor}
:::

::: {.line}
[]{#l00352}[ 352]{.lineno} [ REGISTER\_CLASS\_UNIQ(cnt, RegistryName,
BaseClass, ClassCreator, \\]{.preprocessor}
:::

::: {.line}
[]{#l00353}[ 353]{.lineno} [ config\_proto,
\#\#\_\_VA\_ARGS\_\_)]{.preprocessor}
:::

::: {.line}
[]{#l00354}[ 354]{.lineno} 
:::

::: {.line}
[]{#l00355}[ 355]{.lineno} [\#define REGISTER\_CLASS\_UNIQ(cnt,
RegistryName, BaseClass, ClassCreator, \\]{.preprocessor}
:::

::: {.line}
[]{#l00356}[ 356]{.lineno} [ config\_proto, \...) \\]{.preprocessor}
:::

::: {.line}
[]{#l00357}[ 357]{.lineno} [ static
::tensorflow::serving::internal::ClassRegistry\< \\]{.preprocessor}
:::

::: {.line}
[]{#l00358}[ 358]{.lineno} [ RegistryName, BaseClass,
\#\#\_\_VA\_ARGS\_\_\>::MapInserter \\]{.preprocessor}
:::

::: {.line}
[]{#l00359}[ 359]{.lineno} [ register\_class\_\#\#cnt(
\\]{.preprocessor}
:::

::: {.line}
[]{#l00360}[ 360]{.lineno} [
(config\_proto::default\_instance().GetDescriptor()-\>full\_name()),
\\]{.preprocessor}
:::

::: {.line}
[]{#l00361}[ 361]{.lineno} [ (new
::tensorflow::serving::internal::ClassRegistrationFactory\<
\\]{.preprocessor}
:::

::: {.line}
[]{#l00362}[ 362]{.lineno} [ BaseClass, ClassCreator, config\_proto,
\#\#\_\_VA\_ARGS\_\_\>));]{.preprocessor}
:::

::: {.line}
[]{#l00363}[ 363]{.lineno} 
:::

::: {.line}
[]{#l00364}[ 364]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00365}[ 365]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00366}[ 366]{.lineno} 
:::

::: {.line}
[]{#l00367}[ 367]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_CLASS\_REGISTRATION\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::AbstractClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1AbstractClassRegistrationFactory.html)
:::

::: {.ttdef}
**Definition:** class\_registration.h:173
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::ClassRegistrationFactory](classtensorflow_1_1serving_1_1internal_1_1ClassRegistrationFactory.html)
:::

::: {.ttdef}
**Definition:** class\_registration.h:190
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1ClassRegistry_1_1MapInserter_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::ClassRegistry::MapInserter](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry_1_1MapInserter.html)
:::

::: {.ttdef}
**Definition:** class\_registration.h:280
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1ClassRegistry_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::ClassRegistry](classtensorflow_1_1serving_1_1internal_1_1ClassRegistry.html)
:::

::: {.ttdef}
**Definition:** class\_registration.h:223
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
