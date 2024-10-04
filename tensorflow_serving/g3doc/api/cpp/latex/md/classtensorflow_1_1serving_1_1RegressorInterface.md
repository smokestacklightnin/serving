::: {#classtensorflow_1_1serving_1_1RegressorInterface}
:::

[\[classtensorflow\_1\_1serving\_1\_1RegressorInterface\]]{#classtensorflow_1_1serving_1_1RegressorInterface
label="classtensorflow_1_1serving_1_1RegressorInterface"}

\#include $<$regressor.h$>$

virtual Status
[Regress](#classtensorflow_1_1serving_1_1RegressorInterface_aef7f5c7d1d322f05a0821f20c0164203)
(const RegressionRequest &request, RegressionResult $\ast$result)=0

Model agnostic interface for performing regression.

Specific implementations will exist for different model types (e.g.
TensorFlow SavedModel) that can convert the request into a model
specific input and know how to convert the output into a generic
RegressionResult.

[\[classtensorflow\_1\_1serving\_1\_1RegressorInterface\_aef7f5c7d1d322f05a0821f20c0164203\]]{#classtensorflow_1_1serving_1_1RegressorInterface_aef7f5c7d1d322f05a0821f20c0164203
label="classtensorflow_1_1serving_1_1RegressorInterface_aef7f5c7d1d322f05a0821f20c0164203"}

virtual Status tensorflow::serving::RegressorInterface::Regress (

request,

result

)

Given a RegressionRequest, populates the RegressionResult with the
result.

Parameters *request* & Input request specifying the model/signature to
query along with the data payload.\
*result* & The output regression results that will get populated.\

Returns A status object indicating success or failure.

The documentation for this class was generated from the following file:

tensorflow\_serving/apis/regressor.h
