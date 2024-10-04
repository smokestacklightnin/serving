::: {#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter}
:::

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter"}

Inheritance diagram for
tensorflow::serving::SimpleLoaderSourceAdapter$<$ DataType, ServableType
$>$:

![image](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter__inherit__graph.pdf){width="350pt"}

Collaboration diagram for
tensorflow::serving::SimpleLoaderSourceAdapter$<$ DataType, ServableType
$>$:

![image](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter__coll__graph.pdf){width="350pt"}

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\_a75b8da596c076be3427775b6e2ef8101\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a75b8da596c076be3427775b6e2ef8101
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a75b8da596c076be3427775b6e2ef8101"}
using **Creator** = std::function$<$ Status(const DataType &,
std::unique\_ptr$<$ ServableType $>$ $\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\_a7f8d82dfe30cae9364d9566c7e53c415\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a7f8d82dfe30cae9364d9566c7e53c415
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a7f8d82dfe30cae9364d9566c7e53c415"}
using **ResourceEstimator** = std::function$<$ Status(const DataType &,
ResourceAllocation $\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\_a591696188c5ad7f4bce43bf903571f02\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a591696188c5ad7f4bce43bf903571f02
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a591696188c5ad7f4bce43bf903571f02"}
static ResourceEstimator **EstimateNoResources** ()

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\_a4f9c20c8b345288f9cddd7717ece9c30\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a4f9c20c8b345288f9cddd7717ece9c30
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a4f9c20c8b345288f9cddd7717ece9c30"}
**SimpleLoaderSourceAdapter** (Creator creator, ResourceEstimator
resource\_estimator)

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoaderSourceAdapter\_a4fe28cadc8e8e794aaeeedd15ddef4ed\]]{#classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a4fe28cadc8e8e794aaeeedd15ddef4ed
label="classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_a4fe28cadc8e8e794aaeeedd15ddef4ed"}
Status **Convert** (const DataType &data, std::unique\_ptr$<$
[Loader](#classtensorflow_1_1serving_1_1Loader) $>$ $\ast$loader) final

The documentation for this class was generated from the following file:

tensorflow\_serving/core/simple\_loader.h
