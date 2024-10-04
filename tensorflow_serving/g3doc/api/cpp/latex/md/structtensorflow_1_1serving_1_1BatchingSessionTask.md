::: {#structtensorflow_1_1serving_1_1BatchingSessionTask}
:::

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask
label="structtensorflow_1_1serving_1_1BatchingSessionTask"}

Inheritance diagram for tensorflow::serving::BatchingSessionTask:

![image](structtensorflow_1_1serving_1_1BatchingSessionTask__inherit__graph.pdf){width="227pt"}

Collaboration diagram for tensorflow::serving::BatchingSessionTask:

![image](structtensorflow_1_1serving_1_1BatchingSessionTask__coll__graph.pdf){width="213pt"}

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a6fdbc9ffcee7d8e5b006b69caa9cf8a5\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a6fdbc9ffcee7d8e5b006b69caa9cf8a5
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a6fdbc9ffcee7d8e5b006b69caa9cf8a5"}
typedef std::vector$<$ std::vector$<$ Tensor $>$ $>$ **TensorMatrix**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a91ff8e877221b79a13755b4566e6dd3d\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a91ff8e877221b79a13755b4566e6dd3d
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a91ff8e877221b79a13755b4566e6dd3d"}
size\_t **size** () const override

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a373a9cb0a3901cda84d8c9c4d894ecad\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a373a9cb0a3901cda84d8c9c4d894ecad
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a373a9cb0a3901cda84d8c9c4d894ecad"}
static std::string **Name** ()

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a414c3a8ae8a5a7c38b6aac190361e7dd\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a414c3a8ae8a5a7c38b6aac190361e7dd
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a414c3a8ae8a5a7c38b6aac190361e7dd"}
uint64\_t **enqueue\_time\_micros**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a37211125ccaca7d7d8c1f5a7f78ee956\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a37211125ccaca7d7d8c1f5a7f78ee956
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a37211125ccaca7d7d8c1f5a7f78ee956"}
RunOptions **run\_options**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a63740c858ebe283a81afa731b4d5a653\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a63740c858ebe283a81afa731b4d5a653
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a63740c858ebe283a81afa731b4d5a653"}
size\_t **zeroth\_dim\_size**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a9a3738dcbd22b3f6603d99b2a898cff3\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a9a3738dcbd22b3f6603d99b2a898cff3
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a9a3738dcbd22b3f6603d99b2a898cff3"}
const std::vector$<$ std::pair$<$ string, Tensor $>$ $>$ $\ast$
**inputs**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a91fb78909799f64d611280875f5f790d\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a91fb78909799f64d611280875f5f790d
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a91fb78909799f64d611280875f5f790d"}
const std::vector$<$ string $>$ $\ast$ **output\_tensor\_names**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a3227a00c9984efa3475709e11a303728\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a3227a00c9984efa3475709e11a303728
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a3227a00c9984efa3475709e11a303728"}
Notification $\ast$ **done**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a15a28436e5788a85fb5bbfef0355bf5c\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a15a28436e5788a85fb5bbfef0355bf5c
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a15a28436e5788a85fb5bbfef0355bf5c"}
Status $\ast$ **status**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a8860c4080caef1a3c410c9e13f711ebd\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a8860c4080caef1a3c410c9e13f711ebd
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a8860c4080caef1a3c410c9e13f711ebd"}
std::vector$<$ Tensor $>$ $\ast$ **outputs**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_aa3a07ee4d98dd35bb77a95dc46eee437\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_aa3a07ee4d98dd35bb77a95dc46eee437
label="structtensorflow_1_1serving_1_1BatchingSessionTask_aa3a07ee4d98dd35bb77a95dc46eee437"}
RunMetadata $\ast$ **run\_metadata**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a8908744c1d1451787e9670d50d825bc7\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a8908744c1d1451787e9670d50d825bc7
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a8908744c1d1451787e9670d50d825bc7"}
absl::optional$<$ thread::ThreadPoolOptions $>$
**thread\_pool\_options**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_abfc7a564550dc4698b81bf3fe69483b0\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_abfc7a564550dc4698b81bf3fe69483b0
label="structtensorflow_1_1serving_1_1BatchingSessionTask_abfc7a564550dc4698b81bf3fe69483b0"}
bool **is\_partial** = false

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_ad3eabcdb4217501db137dad2c76359b8\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_ad3eabcdb4217501db137dad2c76359b8
label="structtensorflow_1_1serving_1_1BatchingSessionTask_ad3eabcdb4217501db137dad2c76359b8"}
std::unique\_ptr$<$ std::vector$<$ std::pair$<$ string, Tensor $>$ $>$
$>$ **owned\_split\_inputs**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a9cdcfd844f18c87833ea44b302f3c685\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a9cdcfd844f18c87833ea44b302f3c685
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a9cdcfd844f18c87833ea44b302f3c685"}
int **split\_index** = 0

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_abf4760aaa56b44d57686a696634860bf\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_abf4760aaa56b44d57686a696634860bf
label="structtensorflow_1_1serving_1_1BatchingSessionTask_abf4760aaa56b44d57686a696634860bf"}
std::function$<$ void()$>$ **done\_callback**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_abe23aaf6416ae82426ed5358c0b1f460\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_abe23aaf6416ae82426ed5358c0b1f460
label="structtensorflow_1_1serving_1_1BatchingSessionTask_abe23aaf6416ae82426ed5358c0b1f460"}
std::shared\_ptr$<$ TensorMatrix $>$ **shared\_outputs**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_a5322dc380b7173f4424f3802e8a4f09f\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_a5322dc380b7173f4424f3802e8a4f09f
label="structtensorflow_1_1serving_1_1BatchingSessionTask_a5322dc380b7173f4424f3802e8a4f09f"}
std::shared\_ptr$<$
[ThreadSafeStatus](#classtensorflow_1_1serving_1_1ThreadSafeStatus) $>$
**thread\_safe\_status**

[\[structtensorflow\_1\_1serving\_1\_1BatchingSessionTask\_adffabec37d4b342ecce98c6d71513c6f\]]{#structtensorflow_1_1serving_1_1BatchingSessionTask_adffabec37d4b342ecce98c6d71513c6f
label="structtensorflow_1_1serving_1_1BatchingSessionTask_adffabec37d4b342ecce98c6d71513c6f"}
std::shared\_ptr$<$ std::vector$<$ RunMetadata $>$ $>$
**split\_run\_metadatas**

The documentation for this struct was generated from the following file:

tensorflow\_serving/batching/batching\_session.h
