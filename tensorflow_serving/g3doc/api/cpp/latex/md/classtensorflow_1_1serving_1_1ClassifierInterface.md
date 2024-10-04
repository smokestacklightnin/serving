::: {#classtensorflow_1_1serving_1_1ClassifierInterface}
:::

[\[classtensorflow\_1\_1serving\_1\_1ClassifierInterface\]]{#classtensorflow_1_1serving_1_1ClassifierInterface
label="classtensorflow_1_1serving_1_1ClassifierInterface"}

\#include $<$classifier.h$>$

virtual Status
[Classify](#classtensorflow_1_1serving_1_1ClassifierInterface_a2823879e328bc9e6f99dd91942b203cb)
(const ClassificationRequest &request, ClassificationResult
$\ast$result)=0

Model-type agnostic interface for performing classification.

Specific implementations will exist for different model types (e.g.
TensorFlow SavedModel) that can convert the request into a model
specific input and know how to convert the output into a generic
ClassificationResult.

[\[classtensorflow\_1\_1serving\_1\_1ClassifierInterface\_a2823879e328bc9e6f99dd91942b203cb\]]{#classtensorflow_1_1serving_1_1ClassifierInterface_a2823879e328bc9e6f99dd91942b203cb
label="classtensorflow_1_1serving_1_1ClassifierInterface_a2823879e328bc9e6f99dd91942b203cb"}

virtual Status tensorflow::serving::ClassifierInterface::Classify (

request,

result

)

Given a ClassificationRequest, populates the ClassificationResult with
the result.

Parameters *request* & Input request specifying the model/signature to
query along with the data payload.\
*result* & The output classifications that will get populated.\

Returns A status object indicating success or failure.

The documentation for this class was generated from the following file:

tensorflow\_serving/apis/classifier.h
