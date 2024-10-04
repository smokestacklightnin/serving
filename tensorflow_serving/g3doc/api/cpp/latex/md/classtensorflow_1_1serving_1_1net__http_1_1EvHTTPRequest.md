::: {#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest"}

Inheritance diagram for tensorflow::serving::net\_http::EvHTTPRequest:

![image](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest__inherit__graph.pdf){width="264pt"}

Collaboration diagram for tensorflow::serving::net\_http::EvHTTPRequest:

![image](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest__coll__graph.pdf){width="264pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_adb8947627ca8dca836b736e45b7d009d\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_adb8947627ca8dca836b736e45b7d009d
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_adb8947627ca8dca836b736e45b7d009d"}
**EvHTTPRequest** (const
[EvHTTPRequest](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a405bc5482952d8ce4901b2d928259f91\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a405bc5482952d8ce4901b2d928259f91
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a405bc5482952d8ce4901b2d928259f91"}
[EvHTTPRequest](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest)
& **operator=** (const
[EvHTTPRequest](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_ac415abc071c4d01ac51bf3024aafbed2\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac415abc071c4d01ac51bf3024aafbed2
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac415abc071c4d01ac51bf3024aafbed2"}
**EvHTTPRequest** (std::unique\_ptr$<$
[ParsedEvRequest](#structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest)
$>$ request,
[ServerSupport](#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport)
$\ast$server)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a9cebd921f58f27e9b74a684e347a9049\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a9cebd921f58f27e9b74a684e347a9049
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a9cebd921f58f27e9b74a684e347a9049"}
absl::string\_view **uri\_path** () const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a2012dfc89986f7ec987489ceadf9f348\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2012dfc89986f7ec987489ceadf9f348
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2012dfc89986f7ec987489ceadf9f348"}
absl::string\_view **http\_method** () const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a7a428c079d77b5417d901b5764de7337\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a7a428c079d77b5417d901b5764de7337
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a7a428c079d77b5417d901b5764de7337"}
void **WriteResponseBytes** (const char $\ast$data, int64\_t size)
override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_ad6c8bd95d250a1ae8c13ecb6ee56522a\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ad6c8bd95d250a1ae8c13ecb6ee56522a
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ad6c8bd95d250a1ae8c13ecb6ee56522a"}
void **WriteResponseString** (absl::string\_view data) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_ac206741a825d105757bd02a30417c5e7\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac206741a825d105757bd02a30417c5e7
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac206741a825d105757bd02a30417c5e7"}
std::unique\_ptr$<$ char\[$\,$\],
[ServerRequestInterface::BlockDeleter](#structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter)
$>$ **ReadRequestBytes** (int64\_t $\ast$size) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a9b4837c2a7fdf61502747f4010990119\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a9b4837c2a7fdf61502747f4010990119
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a9b4837c2a7fdf61502747f4010990119"}
absl::string\_view **GetRequestHeader** (absl::string\_view header)
const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a7345deacbcb4d685dc6617e7f0d6d93f\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a7345deacbcb4d685dc6617e7f0d6d93f
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a7345deacbcb4d685dc6617e7f0d6d93f"}
std::vector$<$ absl::string\_view $>$ **request\_headers** () const
override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_af69857b53b2e17c8124ede8ee1255d71\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_af69857b53b2e17c8124ede8ee1255d71
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_af69857b53b2e17c8124ede8ee1255d71"}
void **OverwriteResponseHeader** (absl::string\_view header,
absl::string\_view value) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a6b6c1f21b8e466f336184f0a54d4a1c4\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a6b6c1f21b8e466f336184f0a54d4a1c4
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a6b6c1f21b8e466f336184f0a54d4a1c4"}
void **AppendResponseHeader** (absl::string\_view header,
absl::string\_view value) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a46a106a783fc5530b6dc23b4d166595a\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a46a106a783fc5530b6dc23b4d166595a
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a46a106a783fc5530b6dc23b4d166595a"}
void **PartialReplyWithStatus** (HTTPStatusCode status) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a5c822af861049d5c8c66723ea7e33cb0\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a5c822af861049d5c8c66723ea7e33cb0
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a5c822af861049d5c8c66723ea7e33cb0"}
void **PartialReply** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_ac8f335609b185cd064394074e04f6baf\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac8f335609b185cd064394074e04f6baf
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_ac8f335609b185cd064394074e04f6baf"}
CallbackStatus **PartialReplyWithFlushCallback** (std::function$<$
void()$>$ callback) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_aa525ec2cd5b25678f07bdc12a77a1440\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_aa525ec2cd5b25678f07bdc12a77a1440
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_aa525ec2cd5b25678f07bdc12a77a1440"}
void **ReplyWithStatus** (HTTPStatusCode status) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a2d16e56f7e4b49cbb915fcd1e2b68c09\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2d16e56f7e4b49cbb915fcd1e2b68c09
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2d16e56f7e4b49cbb915fcd1e2b68c09"}
void **Reply** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a2f42750b0a4062061b1c76dac164aa2a\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2f42750b0a4062061b1c76dac164aa2a
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a2f42750b0a4062061b1c76dac164aa2a"}
void **Abort** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_a027f3459fd1d3f5b935e7a211d0834e0\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a027f3459fd1d3f5b935e7a211d0834e0
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_a027f3459fd1d3f5b935e7a211d0834e0"}
bool **Initialize** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPRequest\_af75cbe925296ed9bbac4cb7f78fc6f1d\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_af75cbe925296ed9bbac4cb7f78fc6f1d
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_af75cbe925296ed9bbac4cb7f78fc6f1d"}
void **SetHandlerOptions** (const
[RequestHandlerOptions](#classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions)
&handler\_options)

The documentation for this class was generated from the following files:

tensorflow\_serving/util/net\_http/server/internal/evhttp\_request.h

tensorflow\_serving/util/net\_http/server/internal/evhttp\_request.cc
