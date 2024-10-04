::: {#classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactoryRegistry\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry"}

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactoryRegistry\_a1b9b4283044fb6442adb771eb264fe9a\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_a1b9b4283044fb6442adb771eb264fe9a
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_a1b9b4283044fb6442adb771eb264fe9a"}
using **CreateFn** = std::function$<$ absl::StatusOr$<$
std::unique\_ptr$<$
[TfrtSavedModelFactory](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory)
$>$ $>$(const TfrtSavedModelConfig &config)$>$

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactoryRegistry\_ae5a9dc2a9d422554dbde87da20413039\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_ae5a9dc2a9d422554dbde87da20413039
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_ae5a9dc2a9d422554dbde87da20413039"}
void **Register** (CreateFn fn)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactoryRegistry\_aca767cbaf26e0fa11d3ca5fed25f6974\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_aca767cbaf26e0fa11d3ca5fed25f6974
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_aca767cbaf26e0fa11d3ca5fed25f6974"}
CreateFn **Get** () const

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.h

tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.cc
