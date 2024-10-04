::: {#classtensorflow_1_1serving_1_1DynamicSourceRouter}
:::

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter
label="classtensorflow_1_1serving_1_1DynamicSourceRouter"}

Inheritance diagram for tensorflow::serving::DynamicSourceRouter$<$ T
$>$:

![image](classtensorflow_1_1serving_1_1DynamicSourceRouter__inherit__graph.pdf){width="240pt"}

Collaboration diagram for tensorflow::serving::DynamicSourceRouter$<$ T
$>$:

![image](classtensorflow_1_1serving_1_1DynamicSourceRouter__coll__graph.pdf){width="240pt"}

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_a09a1533f019646303c61650826a75957\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_a09a1533f019646303c61650826a75957
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_a09a1533f019646303c61650826a75957"}
using **Routes** = std::map$<$ string, int $>$

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_ab2fa48b3ba7a45169e85cd5c56db0226\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_ab2fa48b3ba7a45169e85cd5c56db0226
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_ab2fa48b3ba7a45169e85cd5c56db0226"}
Routes **GetRoutes** () const

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_aad9d55b3b718b2c605c1871b3f68f3cc\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_aad9d55b3b718b2c605c1871b3f68f3cc
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_aad9d55b3b718b2c605c1871b3f68f3cc"}
Status **UpdateRoutes** (const Routes &routes)

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_a737dc26711a2edfd31874be8b0db123e\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_a737dc26711a2edfd31874be8b0db123e
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_a737dc26711a2edfd31874be8b0db123e"}
static Status **Create** (int num\_output\_ports, const Routes &routes,
std::unique\_ptr$<$
[DynamicSourceRouter](#classtensorflow_1_1serving_1_1DynamicSourceRouter)$<$
T $>$$>$ $\ast$result)

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_ae94ae903fe62e69312afcd232dee1c37\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_ae94ae903fe62e69312afcd232dee1c37
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_ae94ae903fe62e69312afcd232dee1c37"}
int **num\_output\_ports** () const override

[\[classtensorflow\_1\_1serving\_1\_1DynamicSourceRouter\_acaca1e8c4bfdaa92797d9b272f19736c\]]{#classtensorflow_1_1serving_1_1DynamicSourceRouter_acaca1e8c4bfdaa92797d9b272f19736c
label="classtensorflow_1_1serving_1_1DynamicSourceRouter_acaca1e8c4bfdaa92797d9b272f19736c"}
int **Route** (const StringPiece servable\_name, const std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ T $>$$>$
&versions) override

The documentation for this class was generated from the following file:

tensorflow\_serving/core/dynamic\_source\_router.h
