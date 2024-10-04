::: {#classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler}
:::

[\[classtensorflow\_1\_1serving\_1\_1TFRTHttpRestApiHandler\]]{#classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler
label="classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler"}

Inheritance diagram for tensorflow::serving::TFRTHttpRestApiHandler:

![image](classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler__inherit__graph.pdf){width="223pt"}

Collaboration diagram for tensorflow::serving::TFRTHttpRestApiHandler:

![image](classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler__coll__graph.pdf){width="223pt"}

[\[classtensorflow\_1\_1serving\_1\_1TFRTHttpRestApiHandler\_a5fc3a8da6bc2a54a45945d6254d5a676\]]{#classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_a5fc3a8da6bc2a54a45945d6254d5a676
label="classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_a5fc3a8da6bc2a54a45945d6254d5a676"}
**TFRTHttpRestApiHandler** (int timeout\_in\_ms,
[ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core)

[\[classtensorflow\_1\_1serving\_1\_1TFRTHttpRestApiHandler\_ac9172debfd995858f1713a42a8ffb670\]]{#classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_ac9172debfd995858f1713a42a8ffb670
label="classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_ac9172debfd995858f1713a42a8ffb670"}
Status **ProcessRequest** (const absl::string\_view http\_method, const
absl::string\_view request\_path, const absl::string\_view
request\_body, std::vector$<$ std::pair$<$ string, string $>$$>$
$\ast$headers, string $\ast$model\_name, string $\ast$method, string
$\ast$output) override

static const char $\ast$const **kPathRegex**

[\[classtensorflow\_1\_1serving\_1\_1TFRTHttpRestApiHandler\_a082c34fec314537ccedaa9e2cf9db157\]]{#classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_a082c34fec314537ccedaa9e2cf9db157
label="classtensorflow_1_1serving_1_1TFRTHttpRestApiHandler_a082c34fec314537ccedaa9e2cf9db157"}
const char $\ast$const
tensorflow::serving::TFRTHttpRestApiHandler::kPathRegex

**Initial value:**

0

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/tfrt\_http\_rest\_api\_handler.h

tensorflow\_serving/model\_servers/tfrt\_http\_rest\_api\_handler.cc
