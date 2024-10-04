::: {#classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1TFRTClassificationServiceImpl\]]{#classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl
label="classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl"}

[\[classtensorflow\_1\_1serving\_1\_1TFRTClassificationServiceImpl\_ab9bf3742e8d34a7fb64eb429ae4bb01e\]]{#classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl_ab9bf3742e8d34a7fb64eb429ae4bb01e
label="classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl_ab9bf3742e8d34a7fb64eb429ae4bb01e"}
static Status **Classify** (const
[Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
$\ast$core, const ClassificationRequest &request, ClassificationResponse
$\ast$response)

[\[classtensorflow\_1\_1serving\_1\_1TFRTClassificationServiceImpl\_a64b07608e6352661a316873bc8f1b2ab\]]{#classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl_a64b07608e6352661a316873bc8f1b2ab
label="classtensorflow_1_1serving_1_1TFRTClassificationServiceImpl_a64b07608e6352661a316873bc8f1b2ab"}
static Status **ClassifyWithModelSpec** (const
[Servable::RunOptions](#structtensorflow_1_1serving_1_1servables_1_1RunOptions)
&run\_options, [ServerCore](#classtensorflow_1_1serving_1_1ServerCore)
$\ast$core, const ModelSpec &model\_spec, const ClassificationRequest
&request, ClassificationResponse $\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tfrt\_classification\_service.h

tensorflow\_serving/servables/tensorflow/tfrt\_classification\_service.cc
