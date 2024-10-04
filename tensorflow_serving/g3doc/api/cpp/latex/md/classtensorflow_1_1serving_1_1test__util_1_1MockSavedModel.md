::: {#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel"}

Inheritance diagram for tensorflow::serving::test\_util::MockSavedModel:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel__inherit__graph.pdf){width="235pt"}

Collaboration diagram for
tensorflow::serving::test\_util::MockSavedModel:

![image](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel__coll__graph.pdf){width="235pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_a3f1eb5884ffd156df5e6c18e0d37481f\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a3f1eb5884ffd156df5e6c18e0d37481f
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a3f1eb5884ffd156df5e6c18e0d37481f"}
**MOCK\_METHOD** (const tensorflow::MetaGraphDef &,
GetMetaGraphDef,(),(const, override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_ab482290c417d35716d16872cf9be7929\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_ab482290c417d35716d16872cf9be7929
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_ab482290c417d35716d16872cf9be7929"}
**MOCK\_METHOD** (absl::optional$<$ tfrt::FunctionMetadata $>$,
GetFunctionMetadata,(absl::string\_view func\_name),(const, override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_aeb309ecd14a686b84a035e873ebbfd43\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_aeb309ecd14a686b84a035e873ebbfd43
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_aeb309ecd14a686b84a035e873ebbfd43"}
**MOCK\_METHOD** (::tensorflow::Status, Run,(const
tfrt::SavedModel::RunOptions &run\_options, absl::string\_view
func\_name, absl::Span$<$ const Tensor $>$ inputs, std::vector$<$ Tensor
$>$ $\ast$outputs),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_ad31092a3c1c5c8b870b8df3c6aa24f4a\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_ad31092a3c1c5c8b870b8df3c6aa24f4a
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_ad31092a3c1c5c8b870b8df3c6aa24f4a"}
**MOCK\_METHOD** (std::vector$<$ std::string $>$,
GetFunctionNames,(),(const, override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_a7875c0297312d88dc068e7b7a7d8a5c7\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a7875c0297312d88dc068e7b7a7d8a5c7
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a7875c0297312d88dc068e7b7a7d8a5c7"}
**MOCK\_METHOD** (::tensorflow::Status, RunMultipleSignatures,(const
tfrt::SavedModel::RunOptions &run\_options, absl::Span$<$ const
std::string $>$ names, absl::Span$<$ const std::vector$<$
tensorflow::Tensor $>$$>$ multi\_inputs, std::vector$<$ std::vector$<$
tensorflow::Tensor $>$$>$ $\ast$multi\_outputs),(override))

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1MockSavedModel\_a38d6ec98d6d606089067e895facf95d7\]]{#classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a38d6ec98d6d606089067e895facf95d7
label="classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel_a38d6ec98d6d606089067e895facf95d7"}
**MOCK\_METHOD** (::tensorflow::Status, RunByTensorNames,(const
tfrt::SavedModel::RunOptions &run\_options,(absl::Span$<$ const
std::pair$<$ std::string, tensorflow::Tensor $>$$>$ inputs),
absl::Span$<$ const std::string $>$ output\_tensor\_names, absl::Span$<$
const std::string $>$ target\_node\_names, std::vector$<$
tensorflow::Tensor $>$ $\ast$outputs),(override))

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/test\_util/mock\_tfrt\_saved\_model.h
