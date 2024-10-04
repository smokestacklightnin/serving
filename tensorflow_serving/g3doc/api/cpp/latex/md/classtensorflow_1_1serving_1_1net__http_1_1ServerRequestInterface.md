::: {#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface"}

Inheritance diagram for
tensorflow::serving::net\_http::ServerRequestInterface:

![image](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface__inherit__graph.pdf){width="264pt"}

struct
[BlockDeleter](#structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a99e6341cf57a054cb8b938b0ca744f95\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a99e6341cf57a054cb8b938b0ca744f95
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a99e6341cf57a054cb8b938b0ca744f95"}
enum class **BodyStatus** { **PENDING** = 0 , **COMPLETE** = 1 ,
**FAILED** = 2 }

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_ad3b9246024c81fc53df8f03c3f42ada3\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ad3b9246024c81fc53df8f03c3f42ada3
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ad3b9246024c81fc53df8f03c3f42ada3"}
enum class **CallbackStatus** { **NOT\_SCHEDULED** = 0 , **SCHEDULED** =
1 }

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a3a5ad543b7d882b97e28c7e151de0bbb\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a3a5ad543b7d882b97e28c7e151de0bbb
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a3a5ad543b7d882b97e28c7e151de0bbb"}
**ServerRequestInterface** (const
[ServerRequestInterface](#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a6f512b015cc9668b9c1836fb6c992e68\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a6f512b015cc9668b9c1836fb6c992e68
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a6f512b015cc9668b9c1836fb6c992e68"}
[ServerRequestInterface](#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface)
& **operator=** (const
[ServerRequestInterface](#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_afe73612de6dad7898c068141af590720\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_afe73612de6dad7898c068141af590720
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_afe73612de6dad7898c068141af590720"}
virtual absl::string\_view **uri\_path** () const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_ab28896c0defe813c8dbbdb1115aa6e52\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ab28896c0defe813c8dbbdb1115aa6e52
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ab28896c0defe813c8dbbdb1115aa6e52"}
virtual absl::string\_view **http\_method** () const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a7386e69b3f3afe5314eb67217c2fc991\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a7386e69b3f3afe5314eb67217c2fc991
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a7386e69b3f3afe5314eb67217c2fc991"}
virtual void **WriteResponseBytes** (const char $\ast$data, int64\_t
size)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a7c5430f25c8027aa4addf9b2ad1ff30e\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a7c5430f25c8027aa4addf9b2ad1ff30e
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a7c5430f25c8027aa4addf9b2ad1ff30e"}
virtual void **WriteResponseString** (absl::string\_view data)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a963c74640d07cb5392eef91368813cdb\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a963c74640d07cb5392eef91368813cdb
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a963c74640d07cb5392eef91368813cdb"}
virtual std::unique\_ptr$<$ char\[$\,$\],
[ServerRequestInterface::BlockDeleter](#structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter)
$>$ **ReadRequestBytes** (int64\_t $\ast$size)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_ae3a98d79089c651a03da6289e134890f\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ae3a98d79089c651a03da6289e134890f
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ae3a98d79089c651a03da6289e134890f"}
virtual absl::string\_view **GetRequestHeader** (absl::string\_view
header) const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a89f7e11f96c388a02fd087ac130844ce\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a89f7e11f96c388a02fd087ac130844ce
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a89f7e11f96c388a02fd087ac130844ce"}
virtual std::vector$<$ absl::string\_view $>$ **request\_headers** ()
const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a996fa082fe1ea76d81ad935d90994f47\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a996fa082fe1ea76d81ad935d90994f47
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a996fa082fe1ea76d81ad935d90994f47"}
virtual void **OverwriteResponseHeader** (absl::string\_view header,
absl::string\_view value)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a71f7e44d9a9db13d1cf6be9eaf5aefd6\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a71f7e44d9a9db13d1cf6be9eaf5aefd6
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a71f7e44d9a9db13d1cf6be9eaf5aefd6"}
virtual void **AppendResponseHeader** (absl::string\_view header,
absl::string\_view value)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a8160444169240317224840eccacfac37\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a8160444169240317224840eccacfac37
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a8160444169240317224840eccacfac37"}
virtual void **PartialReplyWithStatus** (HTTPStatusCode status)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a1b73a93234a38221484b9d293bd24b48\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a1b73a93234a38221484b9d293bd24b48
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a1b73a93234a38221484b9d293bd24b48"}
virtual void **PartialReply** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_aadf9595b07c1c102225d67f1cf152a5d\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_aadf9595b07c1c102225d67f1cf152a5d
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_aadf9595b07c1c102225d67f1cf152a5d"}
virtual CallbackStatus **PartialReplyWithFlushCallback**
(std::function$<$ void()$>$ callback)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_abd9dea278abdd8c9e4942469f8173275\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_abd9dea278abdd8c9e4942469f8173275
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_abd9dea278abdd8c9e4942469f8173275"}
virtual BodyStatus **response\_body\_status** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_ae19225bd125fe4f04966b1b7ef3d6160\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ae19225bd125fe4f04966b1b7ef3d6160
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_ae19225bd125fe4f04966b1b7ef3d6160"}
virtual BodyStatus **request\_body\_status** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a38679ff777daa9c8815bc580c2fd8ce5\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a38679ff777daa9c8815bc580c2fd8ce5
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a38679ff777daa9c8815bc580c2fd8ce5"}
virtual void **ReplyWithStatus** (HTTPStatusCode status)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_a8b4554fa0e0e6633f92943abe2d82bff\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a8b4554fa0e0e6633f92943abe2d82bff
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_a8b4554fa0e0e6633f92943abe2d82bff"}
virtual void **Reply** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerRequestInterface\_aa429da9ec48052ab8f3bc3b286951e4e\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_aa429da9ec48052ab8f3bc3b286951e4e
label="classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_aa429da9ec48052ab8f3bc3b286951e4e"}
virtual void **Abort** ()=0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/net\_http/server/public/server\_request\_interface.h
