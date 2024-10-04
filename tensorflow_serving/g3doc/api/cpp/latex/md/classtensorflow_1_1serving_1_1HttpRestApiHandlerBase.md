::: {#classtensorflow_1_1serving_1_1HttpRestApiHandlerBase}
:::

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandlerBase\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandlerBase
label="classtensorflow_1_1serving_1_1HttpRestApiHandlerBase"}

Inheritance diagram for tensorflow::serving::HttpRestApiHandlerBase:

![image](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase__inherit__graph.pdf){width="350pt"}

[\[classtensorflow\_1\_1serving\_1\_1HttpRestApiHandlerBase\_aace3e535f01e93f3fefde857e33e8d22\]]{#classtensorflow_1_1serving_1_1HttpRestApiHandlerBase_aace3e535f01e93f3fefde857e33e8d22
label="classtensorflow_1_1serving_1_1HttpRestApiHandlerBase_aace3e535f01e93f3fefde857e33e8d22"}
virtual Status **ProcessRequest** (const absl::string\_view
http\_method, const absl::string\_view request\_path, const
absl::string\_view request\_body, std::vector$<$ std::pair$<$ string,
string $>$$>$ $\ast$headers, string $\ast$model\_name, string
$\ast$method, string $\ast$output)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/model\_servers/http\_rest\_api\_handler\_base.h
