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
-   [experimental](dir_f3a7702a88a35f439eefb104a4dcf36a.html){.el}
-   [tensorflow](dir_bd7602075eb888604dc304949f6ac883.html){.el}
-   [ops](dir_b76c9497d88760821fddd9a3e2873138.html){.el}
-   [remote\_predict](dir_736b8517fd0d65079ceb0428758bba10.html){.el}
-   [kernels](dir_7024a4e6070c565eef9bd1cc6d151481.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
remote\_predict\_op\_kernel.h
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
[]{#l00015}[ 15]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_REMOTE\_PREDICT\_OP\_KERNEL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#define
TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_REMOTE\_PREDICT\_OP\_KERNEL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#include
\"google/protobuf/wrappers.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"google/protobuf/map.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/framework/common\_shape\_fns.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/framework/op\_kernel.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/framework/register\_types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/framework/resource\_mgr.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/framework/shape\_inference.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/framework/tensor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/framework/tensor.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/kernels/ops\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/lib/core/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/lib/gtl/cleanup.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/core/platform/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow/core/protobuf/named\_tensor.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [typedef]{.keyword}
google::protobuf::Map\<tensorflow::string, tensorflow::TensorProto\>
AliasTensorMap;
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// Remote Predict Op kernel implementation
class templated on different]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// PredictionServiceStubTypes.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [template]{.keyword} \<[typename]{.keyword}
PredictionServiceStubType\>
:::

::: {.line}
[]{#l00045}[
[45](classtensorflow_1_1serving_1_1RemotePredictOp.html){.line}]{.lineno} [class
]{.keyword}[RemotePredictOp](classtensorflow_1_1serving_1_1RemotePredictOp.html){.code}
: [public]{.keyword} AsyncOpKernel {
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [explicit]{.keyword}
[RemotePredictOp](classtensorflow_1_1serving_1_1RemotePredictOp.html){.code}(OpKernelConstruction\*
context)
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  : AsyncOpKernel(context) {
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [string]{.keywordtype} target\_address;
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  OP\_REQUIRES\_OK(context,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
context-\>GetAttr([\"target\_address\"]{.stringliteral},
&target\_address));
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  OP\_REQUIRES\_OK(context,
context-\>GetAttr([\"model\_name\"]{.stringliteral}, &model\_name\_));
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  OP\_REQUIRES\_OK(context,
context-\>GetAttr([\"model\_version\"]{.stringliteral},
&model\_version\_));
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  OP\_REQUIRES\_OK(context,
context-\>GetAttr([\"max\_rpc\_deadline\_millis\"]{.stringliteral},
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  &max\_rpc\_deadline\_millis\_));
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  OP\_REQUIRES\_OK(context,
context-\>GetAttr([\"fail\_op\_on\_rpc\_error\"]{.stringliteral},
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  &fail\_op\_on\_rpc\_error\_));
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  OP\_REQUIRES\_OK(context,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
context-\>GetAttr([\"signature\_name\"]{.stringliteral},
&signature\_name\_));
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  absl::Status prediction\_service\_status =
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
PredictionServiceStubType::Create(target\_address,
&prediction\_service\_);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  OP\_REQUIRES(context,
prediction\_service\_status.ok(),
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
tensorflow::Status([static\_cast\<]{.keyword}tensorflow::errors::Code[\>]{.keyword}(
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  prediction\_service\_status.code()),
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  prediction\_service\_status.message()));
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  }
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [void]{.keywordtype}
ComputeAsync(OpKernelContext\* context, DoneCallback done)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// Get the input tensor alias
names.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword} [auto]{.keyword}&
input\_tensor\_aliases = context-\>input(0).flat\<tstring\>();
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Get the input tensors.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  OpInputList input\_tensors;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  context,
context-\>input\_list([\"input\_tensors\"]{.stringliteral},
&input\_tensors), done);
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// Get the output tensor alias
names.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// Directly index to output\_tensor\_aliases
by moving past all the input]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// before it, including the
input\_tensor\_aliases and input\_tensors.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [auto]{.keyword} output\_tensor\_aliases =
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  context-\>input(1 +
input\_tensors.size()).flat\<tstring\>();
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [// Build the PredictRequest.]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  PredictRequest\* request = [new]{.keyword}
PredictRequest();
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
request-\>mutable\_model\_spec()-\>set\_name(model\_name\_);
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
request-\>mutable\_model\_spec()-\>set\_signature\_name(signature\_name\_);
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [if]{.keywordflow} (model\_version\_ \>= 0) {
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
request-\>mutable\_model\_spec()-\>mutable\_version()-\>set\_value(
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  model\_version\_);
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  }
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  AliasTensorMap& inputs =
\*request-\>mutable\_inputs();
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< input\_tensor\_aliases.size(); ++i) {
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  tensorflow::TensorProto proto;
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  input\_tensors\[i\].AsProtoField(&proto);
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  inputs\[input\_tensor\_aliases(i)\] = proto;
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  }
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< output\_tensor\_aliases.size(); ++i) {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
request-\>add\_output\_filter(tensorflow::string(output\_tensor\_aliases(i)));
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  }
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  PredictResponse\* response = [new]{.keyword}
PredictResponse();
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [auto]{.keyword} rpc\_or =
prediction\_service\_-\>CreateRpc(
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
absl::Milliseconds(max\_rpc\_deadline\_millis\_));
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  OP\_REQUIRES\_ASYNC(context, rpc\_or.ok(),
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
tensorflow::Status([static\_cast\<]{.keyword}tensorflow::errors::Code[\>]{.keyword}(
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  rpc\_or.status().code()),
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  rpc\_or.status().message()),
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  \[&\]() {
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  delete request;
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  delete response;
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  done();
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  });
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [auto]{.keyword} rpc = rpc\_or.value();
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [auto]{.keyword} callback =
\[[this]{.keyword}, context, rpc, request, response,
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  output\_tensor\_aliases,
done\]([const]{.keyword} absl::Status& status) {
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  PostProcessResponse(context, response,
status, fail\_op\_on\_rpc\_error\_,
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  output\_tensor\_aliases, \[&\]() {
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [delete]{.keyword} rpc;
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [delete]{.keyword} request;
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [delete]{.keyword} response;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  done();
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  });
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  };
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// Make the RPC call.]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  prediction\_service\_-\>Predict(rpc,
request, response, callback);
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  }
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [void]{.keywordtype}
PostProcessResponse(OpKernelContext\* context, PredictResponse\*
response,
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [const]{.keyword} absl::Status& rpc\_status,
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [bool]{.keywordtype}
fail\_op\_on\_rpc\_error,
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  TTypes\<const tstring\>::Flat
output\_tensor\_aliases,
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  DoneCallback rpc\_done) {
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [auto]{.keyword} rpc\_cleaner =
gtl::MakeCleanup(\[&\] { rpc\_done(); });
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  Tensor\* status\_code;
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  context, context-\>allocate\_output(0,
TensorShape({}), &status\_code),
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} 
status\_code-\>scalar\<[int]{.keywordtype}\>()() =
[static\_cast\<]{.keyword}[int]{.keywordtype}[\>]{.keyword}(rpc\_status.code());
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  Tensor\* status\_error\_message;
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  context,
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  context-\>allocate\_output(1,
TensorShape({}), &status\_error\_message),
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
status\_error\_message-\>scalar\<tstring\>()() = rpc\_status.message();
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  OpOutputList output\_tensors\_list;
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  context,
context-\>output\_list([\"output\_tensors\"]{.stringliteral},
&output\_tensors\_list),
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// Process the response.]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [if]{.keywordflow} (!rpc\_status.ok()) {
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [if]{.keywordflow}
(fail\_op\_on\_rpc\_error) {
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  context,
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  tensorflow::Status(
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
[static\_cast\<]{.keyword}tensorflow::errors::Code[\>]{.keyword}(rpc\_status.code()),
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  rpc\_status.message()),
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [// Allocate some empty output for the
output\_tensors.]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< output\_tensors\_list.size(); ++i) {
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  Tensor\* unused;
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  OP\_REQUIRES\_OK\_ASYNC(
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  context,
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  output\_tensors\_list.allocate(i,
TensorShape({}), &unused),
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  }
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  }
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  }
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  OP\_REQUIRES\_ASYNC(
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  context, output\_tensors\_list.size() ==
output\_tensor\_aliases.size(),
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  errors::Internal(
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [\"Response doesn\'t have the right number
of outputs; actual: \"]{.stringliteral},
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  output\_tensors\_list.size(),
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [\" expected: \"]{.stringliteral},
output\_tensor\_aliases.size()),
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  AliasTensorMap& outputs =
\*response-\>mutable\_outputs();
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< output\_tensor\_aliases.size(); i++) {
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  Tensor output\_tensor;
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  OP\_REQUIRES\_ASYNC(
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  context,
output\_tensor.FromProto(outputs\[output\_tensor\_aliases(i)\]),
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  errors::Internal([\"Response tensor proto:
\"]{.stringliteral},
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
tensorflow::string(output\_tensor\_aliases(i)),
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [\" cannot be converted back to a
tensor.\"]{.stringliteral}),
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  rpc\_cleaner.release());
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  output\_tensors\_list.set(i,
output\_tensor);
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  }
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  }
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} 
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [string]{.keywordtype} model\_name\_;
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  int64\_t model\_version\_;
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [bool]{.keywordtype}
fail\_op\_on\_rpc\_error\_;
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  int64\_t max\_rpc\_deadline\_millis\_;
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [string]{.keywordtype} signature\_name\_;
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} 
std::unique\_ptr\<PredictionServiceStubType\> prediction\_service\_;
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} };
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} 
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_REMOTE\_PREDICT\_OP\_KERNEL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1RemotePredictOp_html .ttc}
::: {.ttname}
[tensorflow::serving::RemotePredictOp](classtensorflow_1_1serving_1_1RemotePredictOp.html)
:::

::: {.ttdef}
**Definition:** remote\_predict\_op\_kernel.h:45
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
