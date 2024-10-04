::: {#classServingClient}
:::

[\[classServingClient\]]{#classServingClient label="classServingClient"}

[\[classServingClient\_a07b7c728e7127f408a6ba35cd790ce7a\]]{#classServingClient_a07b7c728e7127f408a6ba35cd790ce7a
label="classServingClient_a07b7c728e7127f408a6ba35cd790ce7a"} int
**readJPEG** (const char $\ast$file\_name, tensorflow::TensorProto
$\ast$proto)

[\[classServingClient\_a0c0d36974854d43c938cf6a065aac766\]]{#classServingClient_a0c0d36974854d43c938cf6a065aac766
label="classServingClient_a0c0d36974854d43c938cf6a065aac766"}
**ServingClient** (std::shared\_ptr$<$ Channel $>$ channel)

[\[classServingClient\_a17d210d72dc1f9ce60159eb6ddfafaa0\]]{#classServingClient_a17d210d72dc1f9ce60159eb6ddfafaa0
label="classServingClient_a17d210d72dc1f9ce60159eb6ddfafaa0"}
tensorflow::string **callPredict** (const tensorflow::string
&model\_name, const tensorflow::string &model\_signature\_name, const
tensorflow::string &input\_name, const tensorflow::string &file\_path)

[\[classServingClient\_a77a3cf7aa58652fc9b2112c8857b5d95\]]{#classServingClient_a77a3cf7aa58652fc9b2112c8857b5d95
label="classServingClient_a77a3cf7aa58652fc9b2112c8857b5d95"}
**ServingClient** (const std::string &server\_port)

[\[classServingClient\_a05229c8830fddcd0907cd4874b27eb84\]]{#classServingClient_a05229c8830fddcd0907cd4874b27eb84
label="classServingClient_a05229c8830fddcd0907cd4874b27eb84"} void
**IssuePredict** (const PredictRequest &req)

[\[classServingClient\_a5ba3cc4d4e088e57de222c748d5e5e6d\]]{#classServingClient_a5ba3cc4d4e088e57de222c748d5e5e6d
label="classServingClient_a5ba3cc4d4e088e57de222c748d5e5e6d"} void
**ReapCompletions** ()

[\[classServingClient\_af27f29be8420f76e52afbc0ab6ab8acc\]]{#classServingClient_af27f29be8420f76e52afbc0ab6ab8acc
label="classServingClient_af27f29be8420f76e52afbc0ab6ab8acc"} void
**WaitForCompletion** (int total\_rpcs)

[\[classServingClient\_ae6fc2482a93e4f8fa5a0fdc3116a118a\]]{#classServingClient_ae6fc2482a93e4f8fa5a0fdc3116a118a
label="classServingClient_ae6fc2482a93e4f8fa5a0fdc3116a118a"} void
**DumpStats** ()

The documentation for this class was generated from the following files:

tensorflow\_serving/example/resnet\_client.cc

tensorflow\_serving/test\_util/grpc\_client.cc
