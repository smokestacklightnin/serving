::: {#classtensorflow_1_1serving_1_1HttpRestApiHandler}
:::

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandler\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandler
label="classtensorflow_1_1serving_1_1HttpRestApiHandler"}

Inheritance diagram for tensorflow::serving::HttpRestApiHandler:

![image](classtensorflow_1_1serving_1_1HttpRestApiHandler__inherit__graph.pdf){width="223pt"}

Collaboration diagram for tensorflow::serving::HttpRestApiHandler:

![image](classtensorflow_1_1serving_1_1HttpRestApiHandler__coll__graph.pdf){width="223pt"}

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandler\_a9331b024677b4fab55079584aea72345\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandler_a9331b024677b4fab55079584aea72345
label="classtensorflow_1_1serving_1_1HttpRestApiHandler_a9331b024677b4fab55079584aea72345"}
**HttpRestApiHandler** (int timeout\_in\_ms,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core)

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandler\_ab96d5a96c01551f849da3e0e11df3974\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandler_ab96d5a96c01551f849da3e0e11df3974
label="classtensorflow_1_1serving_1_1HttpRestApiHandler_ab96d5a96c01551f849da3e0e11df3974"}
Status **ProcessRequest** (const absl::string\_view http\_method, const
absl::string\_view request\_path, const absl::string\_view
request\_body, std::vector$<$ std::pair$<$ string, string $>$$>$
$\ast$headers, string $\ast$model\_name, string $\ast$method, string
$\ast$output) override

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandler\_a2b290fc0d1382203d2bd0ededa43a4ef\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandler_a2b290fc0d1382203d2bd0ededa43a4ef
label="classtensorflow_1_1serving_1_1HttpRestApiHandler_a2b290fc0d1382203d2bd0ededa43a4ef"}
static const char $\ast$const **kPathRegex** =
kHTTPRestApiHandlerPathRegex

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/http\_rest\_api\_handler.h

tensorflow\_serving/model\_servers/http\_rest\_api\_handler.cc
